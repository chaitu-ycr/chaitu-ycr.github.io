# ⚡️ uv: Super-fast Python Package Manager

**uv** is a blazing-fast Python package manager and build tool written in Rust. It handles Python versions, projects, scripts, tools, and environments—all with simple commands.

---

## 🐍 Python Version Management

- **Install a Python version**
  ```bash
  uv python install 3.12
  ```
- **List available versions**
  ```bash
  uv python list
  ```
- **Find an installed version**
  ```bash
  uv python find 3.10
  ```
- **Pin project to a version**
  ```bash
  uv python pin 3.11
  ```
- **Uninstall a version**
  ```bash
  uv python uninstall 3.9
  ```

---

## 📜 Script Management

- **Run a script**
  ```bash
  uv run script.py
  ```
- **Add a dependency to a script**
  ```bash
  uv add --script requests
  ```
- **Remove a dependency from a script**
  ```bash
  uv remove --script requests
  ```

---

## 📦 Project Management

- **Create a new project**
  ```bash
  uv init
  ```
- **Add a dependency**
  ```bash
  uv add numpy
  ```
- **Remove a dependency**
  ```bash
  uv remove numpy
  ```
- **Sync dependencies**
  ```bash
  uv sync
  ```
- **Create a lockfile**
  ```bash
  uv lock
  ```
- **Run a command in the project environment**
  ```bash
  uv run python main.py
  ```
- **View dependency tree**
  ```bash
  uv tree
  ```
- **Build the project**
  ```bash
  uv build
  ```
- **Publish the project**
  ```bash
  uv publish
  ```

---

## 🛠️ Tool Management

- **Run a tool temporarily**
  ```bash
  uvx ruff --version
  ```
- **Install a tool globally**
  ```bash
  uv tool install black
  ```
- **Uninstall a tool**
  ```bash
  uv tool uninstall black
  ```
- **List installed tools**
  ```bash
  uv tool list
  ```
- **Update shell for tools**
  ```bash
  uv tool update-shell
  ```

---

## 🧪 Pip Interface (Advanced)

- **Create a virtual environment**
  ```bash
  uv venv .venv
  ```
- **Install a package**
  ```bash
  uv pip install flask
  ```
- **Show package details**
  ```bash
  uv pip show flask
  ```
- **Freeze installed packages**
  ```bash
  uv pip freeze
  ```
- **Check for dependency issues**
  ```bash
  uv pip check
  ```
- **List installed packages**
  ```bash
  uv pip list
  ```
- **Uninstall a package**
  ```bash
  uv pip uninstall flask
  ```
- **View dependency tree**
  ```bash
  uv pip tree
  ```
- **Compile requirements to lockfile**
  ```bash
  uv pip compile requirements.in
  ```
- **Sync environment with lockfile**
  ```bash
  uv pip sync requirements.txt
  ```

---

## 🧹 Utilities

- **Clean cache**
  ```bash
  uv cache clean
  ```
- **Prune outdated cache**
  ```bash
  uv cache prune
  ```
- **Show cache directory**
  ```bash
  uv cache dir
  ```
- **Show tool directory**
  ```bash
  uv tool dir
  ```
- **Show Python versions directory**
  ```bash
  uv python dir
  ```
- **Update uv itself**
  ```bash
  uv self update
  ```

---

## 📝 Practice Questions

1. How do you install Python 3.11 using uv?
2. What command creates a new Python project?
3. How do you add the `requests` package to a script?
4. Which command lists all installed tools?
5. How do you sync your project dependencies?
6. What is the command to build your project into a distribution archive?
7. How do you uninstall a Python version?
8. How do you check for dependency issues in your environment?
9. What command updates uv to the latest version?
10. How do you view the dependency tree for your project?
