# Managing multiple Python versions with *pyenv*



## Official documentation

* [GitHub Page](https://github.com/pyenv/pyenv)
* [Command Reference](https://github.com/pyenv/pyenv/blob/master/COMMANDS.md)



## Installation

Using Homebrew:

```bash
brew update
brew install pyenv
```



## Location

```bash
▶ ls -l ~/.pyenv
total 0
drwxr-xr-x   2 Neo  staff    64 23 Jan 17:04 cache
drwxr-xr-x  35 Neo  staff  1120 30 May 10:49 shims
drwxr-xr-x   4 Neo  staff   128 28 May 17:27 versions
```



## Use

### List of available commands

```bash
pyenv commands
```

### List all Python versions available in pyenv

```bash
pyenv versions
```

### List installed Python versions

```bash
pyenv version
```

### Install a Python version

```bash
pyenv install 2.7.6
```

### Set a local Python version

```bash
pyenv local 2.7.6
# this will create a .python-version file in the same directory
```

### Set a global Python version

```bash
pyenv global 2.7.6
# sets the global version of Python to be used in all shells, in ~/.pyenv/version file.
# can be overridden by an application-specific .python-version file
```

