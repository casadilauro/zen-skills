# Install Zen Skills

These instructions use Git and a macOS or Linux shell. They install ordinary skill folders; no package manager, plugin server, or runtime dependency is needed.

## Get the repository

Clone into a location you will keep:

```sh
git clone https://github.com/casadilauro/zen-skills.git
cd zen-skills
```

If you already have the repository locally, change into that folder instead. For a private repository, Git must have access through your existing GitHub authentication.

## Choose where to install

Codex discovers user skills in `~/.agents/skills` and repository skills in `.agents/skills`. It supports symlinked skill folders. See the [official skill documentation](https://developers.openai.com/codex/skills/).

For skills available across your projects:

```sh
zen_skill_dir="$HOME/.agents/skills"
```

For skills available only in a particular project, use its absolute path instead:

```sh
zen_skill_dir="/absolute/path/to/your/project/.agents/skills"
```

Choose one destination to avoid duplicate entries. Keep the following shell commands in the same terminal session, with the working directory still at the root of this clone.

## Install all nine skills

This links each skill individually and skips existing files, directories, or links. It will preserve an existing installation of zen-python.

```sh
mkdir -p "$zen_skill_dir"
for zen_source in skills/zen-*; do
  zen_target="$zen_skill_dir/${zen_source##*/}"
  if [ -e "$zen_target" ] || [ -L "$zen_target" ]; then
    printf 'Keeping existing: %s\n' "$zen_target"
  else
    ln -s "$PWD/$zen_source" "$zen_target"
  fi
done
```

To install just one skill, change `skills/zen-*` in the loop to `skills/zen-python`, `skills/zen-build`, or another folder name.

To replace an existing installation deliberately, first back it up outside any discovered skills directory, remove its old directory or link, and rerun the loop. Do not delete a directory containing changes you still need.

Keep this clone in place: moving or deleting it breaks the links. For a portable project installation that can be committed with the project, replace the `ln -s` line with `cp -R "$zen_source" "$zen_target"`. Copies do not receive updates automatically.

zen-python needs its entire folder, including `references/`. The other eight skills contain their working guidance directly in SKILL.md.

## Verify and use

Check that the files can be reached:

```sh
test -f "$zen_skill_dir/zen-work/SKILL.md"
test -f "$zen_skill_dir/zen-python/references/design.md"
```

For a partial installation, check only the skills you chose.

In Codex CLI or the IDE extension, use `/skills` or type `$` to select an installed skill. Codex can also select a matching skill automatically. If a new skill does not appear, restart Codex. These discovery and invocation behaviors are described in the [official documentation](https://developers.openai.com/codex/skills/).

Example prompts:

```text
$zen-python Simplify this Python module while preserving its public behavior.
$zen-work Implement the requested change and run the relevant checks.
$zen-review Review this diff for correctness and unnecessary complexity.
```

Start with the relevant skill. The package is not a sequence of nine mandatory stages. An installed skill does not override your task or repository instructions.

If discovery fails, confirm that the link points to a complete skill folder, that SKILL.md is readable, and that the host has not disabled it. Other agents may use different skill locations; follow their documentation or ask the agent to read the relevant SKILL.md directly.

## Update

From the repository clone:

```sh
git pull --ff-only
```

Symlinked installations now point to the updated files. Existing installations skipped by the loop are unchanged. For copied installations, back up local changes and replace only the chosen skill folders with the updated copies. If Git reports local edits or divergent history, resolve those deliberately before updating.

## Remove

For a symlink installation, confirm the target before removing just the link:

```sh
readlink "$zen_skill_dir/zen-build"
unlink "$zen_skill_dir/zen-build"
```

Substitute the skill you want to remove. Removing a link leaves the clone intact. For a copied installation, back up any edits and remove only that skill's directory. Avoid removing other installed skills.
