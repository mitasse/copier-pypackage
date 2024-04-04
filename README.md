# Welcome to Quickstart - Python 👋

[![python](https://img.shields.io/badge/Python-3.9%7C3.10%7C3.11-3776AB.svg?style=flat&logo=python&logoColor=white)](https://www.python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](CODE_OF_CONDUCT.md)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Imports: isort](https://img.shields.io/badge/%20imports-isort-%231674b1?style=flat&labelColor=ef8336)](https://pycqa.github.io/isort/)
[![security: bandit](https://img.shields.io/badge/security-bandit-yellow.svg)](https://github.com/PyCQA/bandit)

**A faster way to build and share Python packages.**

Quickstart Python lets you create packages in minutes, not weeks. Have some doubt? [Take a look.](https://github.airbus.corp/Airbus/my-project) 🔍

<p align="center">
  <img src="https://github.airbus.corp/Airbus/quickstart-python/blob/master/docs/movies/README.gif" />
</p>

## 🔧 Features

- Search, install and publish Python packages
  with [Airbus Artifactory](https://artifactory.2b82.aws.cloud.airbus.corp/)
- Set up virtual environment with [Conda]
- Packaging and dependency management with [Poetry]
- Documentation built with [Jupyter Book]
- Pre-configured tools for code formatting, quality and security analysis:
    - Code formatting with [Black]
    - Import sorting with [isort]
    - Linting with [Flake8]
    - Static type-checking with [mypy]
    - Static docstrings-checking with [pydocstyle]
    - Docstrings coverage with [Interrogate]
    - Security audit with [Bandit]
- Tests run and coverage with [pytest] and [pytest-cov], respectively
- Ready-to-use command-line interface with [Click]
- CDTNG compliant for Giseh

The template supports Python 3.9, 3.10 and 3.11

[bandit]: https://github.com/PyCQA/bandit

[black]: https://github.com/psf/black

[conda]: https://docs.conda.io/en/latest/

[flake8]: http://flake8.pycqa.org

[interrogate]: https://interrogate.readthedocs.io

[isort]: https://pycqa.github.io/isort/

[mypy]: http://mypy-lang.org/

[poetry]: https://python-poetry.org/

[pydocstyle]: http://www.pydocstyle.org/

[pytest]: https://docs.pytest.org/en/latest/

[pytest-cov]: https://pytest-cov.readthedocs.io/en/latest/

[jupyter book]: https://jupyterbook.org/en/stable/intro.html

[click]: https://click.palletsprojects.com/

## ⚡ Prerequisites

Before you get started, you're going to need a few things:

- Access to [Airbus Artifactory](https://artifactory.2b82.aws.cloud.airbus.corp/ui)
- Proper configuration of `conda` and `pip` for AWS ([Windows](https://confluence.airbus.corp/pages/viewpage.action?pageId=388341419), [Giseh](https://confluence.airbus.corp/pages/viewpage.action?pageId=388341601))
- Have a valid [GitHub token access](https://confluence.airbus.corp/pages/viewpage.action?pageId=388341916)

## 🚀 Generating a project

Create a `conda` virtual environment:

```commandline
conda create -n copier python=3.11
```

Activate the virtual environment:

```commandline
conda activate copier
```

Install the `copier` and `poetry` libraries:

```commandline
pip install poetry copier
```

Grant `poetry` access to [Airbus Artifactory](https://artifactory.2b82.aws.cloud.airbus.corp/):

```commandline
poetry config certificates.aws.cert "path/to/certificates"
```

Depending on the platform you are using, path to certificate differs:

- for Windows: `"C:\\ProgramData\\.cert\\cacerts-airbus.pem"`
- for Giseh: `/etc/ssl/certs/ca-bundle.crt`

In case of not found certificate, you can download
it [here](https://github.airbus.corp/connectivity/airbus-ca/blob/master/bundle/airbus-ca.crt).

Access token is also required. It is used as a mean of authentication to the API of Artifactory.

```commandline
poetry config http-basic.aws "username (e.g. doe, jane)" "token"
```

Please refer to the
dedicated [Confluence section](https://confluence.airbus.corp/pages/viewpage.action?pageId=388341348)
to get an Artifactory access token.

On Giseh, we strongly recommend to override the cache directory to not pollute your `$HOME` directory:

```
poetry config cache-dir /projects/<my_favorite_cpd>/.cache/<login>/pypoetry
```

Go the root location where you want to store your package, create your project directory and go in it:

```commandline
cd /path/to/my_project_root
mkdir my_project
cd my_project
```

Generate the project using the `quickstart-python` template:

```commandline
copier copy https://github.airbus.corp/Airbus/quickstart-python-template.git .
```

Copier will ask you a lot of questions. Answer them to properly generate the template.

Once done, you can deactivate the virtual environment:

```commandline
conda deactivate
```

## 👷 Working on a project

Dependencies and virtual environments are managed by [Poetry].

The first thing you do when entering your repository is to create a dedicated virtual environment:

Create a `conda` virtual environment into your freshly created project:

```commandline
cd /path/to/my_project
conda create -p venv python=3.11
```

Activate the virtual environment:

```commandline
conda activate venv/
```

Install the `copier` and `poetry` libraries:

```commandline
pip install poetry copier
```

Install all `quickstart-python` pre-defined libraries:

```commandline
poetry install
```

This will create the virtualenv the first time and install the dependencies.

Test that the installation worked:

```commandline
my_project hello
```

`Welcome to my_project!` should appear in a new tab in your console!

**You're good to go!**

## 🔌 Connecting to GitHub

Take a look to our dedicated [Confluence section](https://confluence.airbus.corp/pages/viewpage.action?pageId=388341651).

## ✏️ Developer CLI

`quickstart-python` offers a developer-centric command-line interface to your application for testing, checking code
quality, auto-formatting and much more.

Feel free to discover all of them using:

```commandline
my_project --help
```

```
Options:
  --version  Show the version and exit.
  --doc      Open the documentation.
  --help     Show this message and exit.

Commands:
  build         Command to build source distribution and wheel.
  check         Command to check the code quality, typing, docstring...
  docs-build    Command to build the documentation locally.
  docs-publish  Command to publish documentation to Github gh-pages.
  format        Command to run formatting tools on the code.
  hello         Command to check my_project is correctly installed.
  publish       Command to publish on r-fb40-propulsion-pypi-local...
  test          Command to run the test suite.
```

## 📌 Updating on a project

Copier has an "update" feature. It means that, once a project is generated, you can keep updating it
with the latest changes that happen in the template.

It's particularly useful when you manage a lot of projects, all generated from the same template,
and you want to apply a change to all your projects.

Example: the template fixed a bug in the Makefile. You don't want to apply it manually to your
projects.

To update your project, go into its directory, and run `copier update`. Your repository must be
clean (no modified files) when running this command.

## 📚 More information

- Our amazing [community](https://chat.google.com/room/AAAArDQujHw?cls=7) where quickstart-python
  users ask questions, and help each other out
- Our [Wiki](https://github.airbus.corp/Airbus/quickstart-python/wiki) and our [Confluence](https://confluence.airbus.corp/display/1FB40LEMON/Adapted+Guidelines+and+recommendations) to get useful information
- Or just show support by giving a star to [quickstart-python on GitHub](https://github.airbus.corp/Airbus/quickstart-python)! ⭐
