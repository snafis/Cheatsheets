# Managing project dependencies with with *poetry*



## Official documentations

* https://python-poetry.org
* https://python-poetry.org/docs/
* https://github.com/python-poetry/poetry

## Installation

```bash
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
```



## Location

```bash
▶ ls -l ~/.poetry
total 8
drwxr-xr-x  3 Neo  staff  96 29 Feb 12:27 bin
-rw-r--r--  1 Neo  staff  37 29 Feb 12:27 env
drwxr-xr-x  3 Neo  staff  96  8 Mar 19:10 lib
```

```bash
▶ poetry config --list
cache-dir = "/Users/Neo/Library/Caches/pypoetry"
virtualenvs.create = true
virtualenvs.in-project = true
virtualenvs.path = "{cache-dir}/virtualenvs"  # /Users/Neo/Library/Caches/pypoetry/virtualenvs
```



## Use



### Setting up a project

#### Create a new project

```bash
poetry new <project-name>
```

#### Initialise in an existing project

```bash
poetry init
```

### One configuration to rule them all

```yaml
pyproject.toml
--------------
[tool.poetry]
name = "poetry-project"
version = "0.1.0"
description = ""
authors = ["Shifath Nafis <shifath.nafis@email.com>"]

[tool.poetry.dependencies]
python = "^3.7"

[tool.poetry.dev-dependencies]
pytest = "^4.6"

[build-system]
requires = ["poetry>=0.12"]
build-backend = "poetry.masonry.api"
```

Further details on each section can be found here: https://python-poetry.org/docs/pyproject/



### Installing and managing dependencies

#### Add a dependency

```bash
poetry add <package-name>
```

#### Add a development dependency

```bash
poetry add --dev <package-name>
```

#### Remove a dependency

```bash
poetry remove <package-name>
```

#### Show dependency tree

```bash
poetry show --tree
```

#### Install dependencies

```bash
poetry install
```

#### Check for inconsistencies

```bash
poetry check
```

#### Check for outdated dependency

```bash
poetry show --outdated
poetry show --latest	
```

#### Update a dependency

```bash
poetry update <package-name>
# without a package-name it will update all outdated dependencies
```

#### Export depency as *requirements.txt*

```bash
poetry export -f requirements.txt > requirements.txt
```



### Managing virtual environment

### Get *venv* path

```bash
poetry run which python
# or
poetry env info --path
```

#### Get a shell

```bash
poetry shell
```



### Executing scripts/application

### Run a script/app

```bash
poetry run python <script>
```



### Building and publishing

#### Configure repositories and credentials

```bash
# private repo
poetry config repositories.priv https://private.repository
poetry config http-basic.priv username password
# pypi
poetry config pypi-token.pypi my-token
```

#### Build

```bash
# Builds the source and wheels archives
poetry build
> Building poet (0.1.0)
 - Building sdist
 - Built poet-0.1.0.tar.gz
- Building wheel
 - Built poet-0.1.0-py3-none-any.whl

# specific build
poetry build -F wheel # or sdist
```

#### Deploy

```bash
# pypi
poetry publish
# private repo
poetry publish -r priv
```



## References

* https://hackersandslackers.com/python-poetry-package-manager/
* 