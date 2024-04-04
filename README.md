# Welcome to Quickstart - Python 👋

[![python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](CODE_OF_CONDUCT.md)
[![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)
[![security: bandit](https://img.shields.io/badge/security-bandit-yellow.svg)](https://github.com/PyCQA/bandit)

**A faster way to build and share Python packages.**

Copier-pypackage lets you create packages in minutes, not weeks. Have some doubt? [Take a look.](https://github.com/mitasse/my-project) 🔍

## 🔧 Features

- Packaging and dependency management with [Poetry]
- Documentation built with [Jupyter Book]
- Pre-configured tools for code formatting, quality and security analysis:
    - Linting and code formatting with [Ruff]
    - Static type-checking with [mypy]
    - Static docstrings-checking with [pydocstyle]
    - Docstrings coverage with [Interrogate]
    - Security audit with [Bandit]
- Tests run and coverage with [pytest] and [pytest-cov], respectively
- Ready-to-use command-line interface with [Click]
- CDTNG compliant for Giseh

The template supports Python 3.8 or newer.

[bandit]: https://github.com/PyCQA/bandit

[interrogate]: https://interrogate.readthedocs.io

[mypy]: http://mypy-lang.org/

[poetry]: https://python-poetry.org/

[pydocstyle]: http://www.pydocstyle.org/

[pytest]: https://docs.pytest.org/en/latest/

[pytest-cov]: https://pytest-cov.readthedocs.io/en/latest/

[ruff]: https://docs.astral.sh/ruff/

[jupyter book]: https://jupyterbook.org/en/stable/intro.html

[click]: https://click.palletsprojects.com/

## ⚡ Prerequisites

Before you get started, you're going to need a few things:

- Install Python 3.8 or newer
- Install Git 2.7 or newer
- Install [Copier](https://copier.readthedocs.io/en/stable/)
- Install [Poetry](https://python-poetry.org/)

## 🚀 Generating a project

Go the root location where you want to store your project, create your project directory and go in it:

```commandline
cd /path/to/my-project-root
mkdir my-project
cd my-project
```

Generate the project using the `copier-pypackage` template:

```commandline
copier copy https://github.com/mitasse/copier-pypackage.git .
```

Copier will ask you some questions. Answer them to properly generate the template.

## 👷 Working on a project

Dependencies and virtual environments are managed by [Poetry].

The first thing you do when entering your repository is to install the dependencies:

```commandline
poetry install
```

Test that the installation worked:

```commandline
my-project hello
```

`Welcome to my-project!` should appear in a new tab in your console!

**You're good to go!**

## 📌 Updating on a project

Copier has an "update" feature. It means that, once a project is generated, you can keep updating it
with the latest changes that happen in the template.

It's particularly useful when you manage a lot of projects, all generated from the same template,
and you want to apply a change to all your projects.

To update your project, go into its directory, and run `copier update`. Your repository must be
clean (no modified files) when running this command.
