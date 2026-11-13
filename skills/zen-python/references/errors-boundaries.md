# Errors and Boundaries

Errors should never disappear accidentally.

## Exceptions

Never use:

    except:
        pass

Avoid broad `except Exception` recovery unless deliberately justified.

Catch the narrowest meaningful exception.

## Preserve Context

When translating an external exception into a domain error:

    raise ConfigurationError(...) from exc

Preserve the original cause.

## Expected Absence vs Failure

Use return values such as `None` when absence is part of normal behavior.

Use exceptions when an operation cannot fulfill its contract.

Do not return `None` for unrelated failures merely to avoid exceptions.

## External Effects

Effects include:

- filesystem access
- network requests
- database writes
- subprocesses
- external APIs
- global mutation

Keep effects explicit and localized.

Prefer separating:

    load
    transform
    save

when practical.

## Resource Ownership

Make ownership and cleanup clear.

Use context managers for deterministic cleanup.

## Validation Boundaries

Validate untrusted data as it enters the system.

Do not scatter redundant validation everywhere internally.

## Retry Behavior

Retry only failures likely to be transient.

Retries should have:

- bounded attempts or duration
- clearly understood failure conditions
- appropriate backoff where relevant

Do not retry arbitrary exceptions.

## Silent Recovery

Do not convert unexpected failure into successful-looking output.

Fallback behavior must be part of an explicit contract.
