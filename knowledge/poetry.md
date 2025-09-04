# Poetry

## Table of Content

- [Getting Started](#getting-started)
- [Syntax for specifying dependency version](#syntax-for-specifying-dependency-version)
- [Best Practices](#best-practices)
- [Jupyter Notebook & Poetry](#jupyter-notebook--poetry)
- [Reference](#reference)

## Getting Started

Poetry is widely used and very popular as a modern python project dependencies management tool. So, we could also consider it a best practice that's worth mentioning.

Poetry is like Pipenv, having built-in virtual environment, lock file for sub-dependencies management. But, the difference is that Poetry has built-in publishing package which made it easier to build and publish a module to Pypi.

Unlike Pipenv, Poetry can use `pyproject.toml` to configure project's dependencies instead of having its own configuration file, like `Pipfile`. However, `poetry.lock` still exists, just like `Pipfile.lock` for the same purpose of locking dependencies and sub-dependencies. 

***Note: Official documentation highly suggest that 'Poetry should always be installed in a dedicated virtual environment to isolate it from the rest of your system. This ensures that Poetry’s own dependencies will not be accidentally upgraded or uninstalled.'***

This means `poetry` shouldn't be installed in project's virtual environment also.

| Install Location | Recommended? | Notes |
|:----------------:|:------------:|:-----:|
|Global system Python | No | Risks affecting system or Poetry packages
|Project venv | No | Can conflict with project dependencies
|Separate venv on host | Yes | Best practice — isolated, safe

You can find installation detail for Linux and MacOS on [official page](https://python-poetry.org/docs/#installing-manually). But, installation for Windows is quite troublesome. Here's the steps for Git Bash approach:

```bash
# 0. (Optional) clear the previous `poetry `installed in global or in project's venv
# poetry should be uninstalled globally from every python versions
deactivate
pip uninstall poetry

# 1. prepare executable path for new poetry's isolated python environment
export POETRY_HOME="/c/Users/<your-pc-username>/.poetry-env"
export VENV_PATH="${POETRY_HOME}/Scripts"

# 2. add new isolated venv to $PATH *temporarily* to be executable for the current session
export PATH="$VENV_PATH:$PATH"

# 3. create venv for poetry
python -m venv ~/.poetry-env

$VENV_PATH/python -m pip install -U pip setuptools
$VENV_PATH/python -m pip install poetry
# OR $VENV_PATH/pip install poetry

# 4. check if poetry is installed in new created isolated environment
poetry -V
# below commands should return with "/c/Users/<your-pc-username>/.poetry-env/Scripts/" path
which python
which poetry

# Optional
# check if python in poetry is executable
# where python should "/c/Users/<your-pc-username>/.poetry-env/Scripts/python" path in list
where python
# below command should be executed after `poetry install` and return in '%/virtualenvs/%' due to using poetry environment
poetry run which python
poetry run where python
```

To uninstall `poetry`, just delete `$VENV_PATH` directory (venv folder). And please, note that this `poetry` is available only within a session, because refreshing terminal session will result in removing `VENV_PATH` environment variable and modified `$PATH` which is modified for temporary.

*Note that setting environment variable: `$PATH` for that isolated `poetry` environment permanently would risk to confuse of which python on Windows is being used*

Below Basic usage refer to this [official documentation](https://python-poetry.org/docs/basic-usage/)

- Initiaing a new project:

```bash
poetry new project_name
```

- Initiating from existing project (creating `pyproject.toml`)

```bash
poetry init
```

- Install project dependencies to virtual environment (created a new one if not activated and detected)
```bash
poetry install
```

*Note: `poetry install` with existing `poetry.lock` file results in installing pre-defined all dependencies and sub-dependencies, which is great. But without `poetry.lock`, the command will generate a new one that should be keep in verion control.*

Note: Poetry will automatically detect active venv and use it before trying to create its own venv.


- checking which poetry is being used for the project
```bash
poetry env list
```

- Using specific python version (requires the python version installed on local machine)
```bash
poetry env use 3.11
```

- Run code using virtual environment
```bash
poetry run python your_script.py

# example
# poetry run streamlit run app.py

# to check how poetry use python
which python
poetry run which python
```

Please, note that one can specify which python version to use in a poetry environment for a project by specifying in `pyproject.toml` with `[project]` table and `requires-python` attribute.

But specified python version must be installed in a host machine (local machine or in docker image).

- Deleting `poetry.lock` file and running install again, resulting in updated all dependencies to their latest version.
```bash
poetry update
```

- Deleting virtual environments for all projects but keep `poetry` installed
```bash
poetry env remove --all
```

- Install project dependencies only specific group for specific usecase
```bash
# excluding certain groups
poetry install --without dev,ci

# including optional groups
poetry install --with dev

# installing only specific group
poetry install --only ci
```

```toml
# in configuration file (pyproject.toml)
[tool.poetry.group.dev]
optional = true

[tool.poetry.group.dev.dependencies]
pyspark = "3.4.0"

[tool.poetry.group.ci]
optional = true

[tool.poetry.group.ci.dependencies]
pytest = "~8.3.5"
black = "^25.1.0"
pylint = "3.3.*"
```

Or it can be added via CLI

```bash
poetry add xgboost

poetry add --group ci black

poetry remove xgboost
```

- publish to PyPI
```bash
# build distributions
poetry build

# publish to pypi
poetry publish
```

*Note: Unlike with other packages, Poetry will **not** automatically install a python interpreter for you. If you want to run Python files in your package like a script or application, you must bring your own python interpreter to run them.*

## Syntax for specifying dependency version

- Caret (^): Allow only patch and minor update e.g. `^1.2.3`
- Tilde (~): Allow only patch e.g. `~1.2.3`
- Exact Version: Not Allow update e.g. `1.2.3`
- Greater than (>)
- Less than (<)
- Greater than or Equal (>=)
- Less than or Equal (<=)
- Version Range: Allow only within a range `>=1.2.3,<2.0.0`
- Wildcard (*): Allow to match any version e.g. `1.2.*`

## Best Practices

1. Always separate project virtual environment with poetry
2. Keep `pyproject.toml` and `poetry.lock` in version control
3. Use semantic layer versioning for package versions *(major.minor.patch)*
4. Specify contraint for dependencies version to avoid conflict
5. Regularly use `poetry update`, but test after updating
6. Use group to separate dependencies for specific usecases and document it using comment
7. `poetry check` to validate `pyproject.toml` syntax
8. Keep production dependencies minimal by specifying optional dependencies
9. Test package installation in a clean environment before publishing 
10. Maintain a clear `CHANGELOG.md`
11. Use `poetry run` to ensure correct environment usage

## Jupyter Notebook & Poetry

You're required to do a couple things to allow a python notebook to use poetry virtual environment:
1. Make sure your poetry is executable.
2. Create poetry virtual environment for a project by `poetry install` command (use tag `--with` if needed).
3. Get the virtual environment path created by poetry with `poetry env info --path`
4. In vscode, `Ctrl + Shift + P` or `Command + Shift + P`, select python interpreter and enter the virtualenv path from the previous step.
5. Open python notebook, select kernel, and select Poetry virtual environment.

*Note1*: make sure to add `ipykernel` dependency to `pyproject.toml`

*Note2*: if there's no option to choose for poetry virtual environment, try `Ctrl + Shift + P` or `Command + Shift + P` and select `Developer: Reload Window`, then try again.

*Note3*: In order to remove poetry virtual env (`poetry env remove --all`), it requires to close the python notebook that's activating the venv and let python interpreter to use other python executable before trying to deleting poetry venv again. 

## Reference

- [Basic usage - Poetry Official](https://python-poetry.org/docs/basic-usage/)
- [Python Poetry - Datacamp (for more detail on commands)](https://www.datacamp.com/tutorial/python-poetry)