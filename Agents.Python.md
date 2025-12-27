# Python Best Practices

Guidance for writing simple, readable Python that follows PEP 8. Use this as
the default coding mindset for Python work in this repository.

## Principles
- Prefer clarity over cleverness; make intent obvious.
- Keep functions small and focused; favor single-purpose modules.
- Use explicit names; avoid abbreviations unless standard.
- Fail loudly with helpful errors; avoid silent fallbacks.

## Style and Structure
- Follow PEP 8 formatting and naming conventions.
- Use type hints where they improve readability and tooling.
- Write docstrings for public modules, classes, and functions.
- Keep lines short and avoid deeply nested logic.

## Dependencies and Environments
- Always use a virtual environment for development.
- Poetry is the default tool for dependency management.
- Keep dependencies minimal and pinned via Poetry.
- Capture runtime and dev dependencies explicitly.

## Testing and Quality
- Add tests for new behavior; keep them focused and fast.
- Prefer deterministic tests; avoid time and randomness unless required.
- Run the smallest relevant test set before committing.

## Async and Data-Heavy Workloads
- Use async only when it improves throughput or latency; avoid it by default.
- Keep async boundaries clear; expose sync wrappers when it helps callers.
- Limit concurrency with semaphores or pools to protect memory and IO.
- Stream large data; avoid loading whole datasets into memory.
- Prefer vectorized or batched operations for heavy data paths.
- Measure performance with representative data before optimizing.

## Tooling Defaults
- Use `poetry install` to set up the environment.
- Use `poetry run` for commands to ensure the venv is active.
