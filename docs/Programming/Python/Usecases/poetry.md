# 🐍 Python Poetry: Simple Dependency Management

**Poetry** is a tool to manage Python project dependencies, virtual environments, and packaging—all in one place.

---

## 🚀 Installation

```sh
curl -sSL https://install.python-poetry.org | python3 -
# or
pip install poetry
```

---

## 🆕 Create a New Project

```sh
poetry new my-project
```
Creates a folder with starter files.

---

## ➕ Add Dependencies

```sh
poetry add requests
```
Adds `requests` to your project.

---

## 📦 Install All Dependencies

```sh
poetry install
```
Installs everything from `pyproject.toml`.

---

## 🏃 Run Python Scripts

```sh
poetry run python script.py
```
Runs scripts inside the Poetry-managed environment.

---

## 🌀 Manage Virtual Environments

```sh
poetry shell
```
Activates the virtual environment for your project.

---

## 🛠️ Build & Publish Packages

**Build:**
```sh
poetry build
```
Creates distributable files in `dist/`.

**Publish:**
```sh
poetry publish
```
Uploads your package to PyPI.

---

## 📝 Example: pyproject.toml

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

---

**Summary:**
Poetry makes Python project management easy—no more manual virtualenvs or requirements.txt! Try the commands above to get started

---

## 🧑‍💻 Practice Questions

1. How do you add a new dependency to your project using Poetry?
2. What command creates a new Poetry project?
3. How do you activate the virtual environment managed by Poetry?
4. How do you build and publish your package to PyPI?
5. What file does Poetry use to track dependencies?
