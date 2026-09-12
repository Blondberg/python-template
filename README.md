# python-template
A boilerplate for fresh Python projects containing the most necessary parts.

## Requirements
 - Python 3.14+
 - uv

 ## Setup
 ```bash
uv sync
uv run pre-commit install
cp .env.example .env

 ```

Update in pyproject.toml:
- [project.scripts]

    app = "project_name.main:main"

- [project]

    name = "project-name"

    version = "0.1.0"

    description = "Short project description"

## Development
Run the application
```bash

uv run python -m project_name.main
```
or
```bash

uv run app

```

Run tests:

```bash
uv run pytest
```

Lint:

```bash
uv run ruff check .
```

Format:

```bash
uv run ruff format .
```

Type check:

```bash
uv run mypy src tests
```

Run all pre-commit checks:

```bash
uv run pre-commit run --all-files
```

## License

MIT