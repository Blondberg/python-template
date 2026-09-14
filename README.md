# Python Template

A minimal boilerplate for starting new Python projects with a consistent development setup.

Included by default:

* Python 3.14+
* `uv` for dependency and environment management
* `ruff` for linting and formatting
* `mypy` for static type checking
* `pytest` for testing
* `pre-commit` for automated checks
* GitHub Actions CI
* `.env` support
* `src/` project layout

## Requirements

Make sure the following are installed:

* Python 3.14+
* [uv](https://docs.astral.sh/uv/)

## Getting Started

Create a new repository from this template, then clone it locally.

Install the project dependencies:

```bash
uv sync
```

Install the pre-commit hooks:

```bash
uv run pre-commit install
```

Create your local environment file:

```bash
cp .env.example .env
```

The `.env` file is ignored by Git and should be used for local secrets and configuration.

## Configure the Project

Before starting development, update the project-specific values in `pyproject.toml`.

### Project metadata

Update:

```toml
[project]
name = "project-name"
version = "0.1.0"
description = "Short project description"
```

### Package name

The default package lives under:

```text
src/project_name/
```

Rename `project_name` to match your project.

Remember to update any references to `project_name` in:

* `pyproject.toml`
* `tests/`
* CI or tooling configuration, if applicable

### Application command

The template exposes an application command through:

```toml
[project.scripts]
app = "project_name.main:main"
```

After renaming the package, update it accordingly:

```toml
[project.scripts]
app = "awesome_app.main:main"
```

This maps:

```bash
uv run app
```

to the `main()` function inside:

```text
src/awesome_app/main.py
```

## Running the Application

The recommended way to run the project is:

```bash
uv run app
```

You can also run the module directly:

```bash
uv run python -m project_name.main
```

Replace `project_name` with your actual package name.

## Development

### Run tests

```bash
uv run pytest
```

### Lint

```bash
uv run ruff check .
```

Automatically fix supported lint issues:

```bash
uv run ruff check . --fix
```

### Format

```bash
uv run ruff format .
```

### Type check

```bash
uv run mypy src tests
```

### Run all pre-commit checks

```bash
uv run pre-commit run --all-files
```

Pre-commit hooks also run automatically when committing after:

```bash
uv run pre-commit install
```

## Adding Dependencies

Add a runtime dependency:

```bash
uv add <package>
```

Add a development dependency:

```bash
uv add --dev <package>
```

`uv` automatically updates both `pyproject.toml` and `uv.lock`.

## Environment Variables

Put local environment variables in:

```text
.env
```

## License

This template uses the MIT License.

Update the copyright information in `LICENSE`
before publishing a new project.
