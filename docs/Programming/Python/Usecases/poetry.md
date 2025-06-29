# Python Poetry

Python Poetry is a dependency management and packaging tool for Python projects. It simplifies the process of managing dependencies, building, and publishing Python packages. Here’s a step-by-step guide on how to use Poetry:

## 1. Installation

First, you need to install Poetry. You can do this using the following command:

```sh
curl -sSL https://install.python-poetry.org | python3 -
```

Alternatively, you can use `pip`:

```sh
pip install poetry
```

## 2. Creating a New Project

To create a new project, navigate to your desired directory and run:

```sh
poetry new my-project
```

This will create a new directory called `my-project` with a basic structure.

## 3. Adding Dependencies

To add dependencies to your project, use the `add` command:

```sh
poetry add requests
```

This will add the `requests` library to your project and update the pyproject.toml file with the dependency.

## 4. Installing Dependencies

To install all dependencies listed in the pyproject.toml file, run:

```sh
poetry install
```

## 5. Running Scripts

You can run your Python scripts using Poetry’s `run` command:

```sh
poetry run python script.py
```

## 6. Managing Virtual Environments

Poetry automatically creates and manages virtual environments for your projects. You can activate the virtual environment with:

```sh
poetry shell
```

## 7. Building and Publishing

To build your project, use:

```sh
poetry build
```

This will create distribution files in the `dist` directory. To publish your package to PyPI, use:

```sh
poetry publish
```

## Example pyproject.toml

Here’s an example of what a pyproject.toml file might look like:

```toml
[tool.poetry]
name = "my-project"
version = "0.1.0"
description = "A sample Python project"
authors = ["Your Name <you@example.com>"]

[tool.poetry.dependencies]
python = "^3.8"
requests = "^2.25.1"

[tool.poetry.dev-dependencies]
pytest = "^6.2.2"
```

## Summary

Poetry is a powerful tool that simplifies dependency management and packaging for Python projects. It helps you maintain a clean and consistent environment, making it easier to manage and share