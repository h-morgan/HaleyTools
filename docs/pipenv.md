# Pipenv Cheat Sheet

Pipenv is a Python package used to manage both virtual environments and packages in one. See [here](https://pipenv.pypa.io/en/latest/#:~:text=The%20problems%20that%20Pipenv%20seeks%20to%20solve%20are%20multi%2Dfaceted%3A) for an overview of the benefits of using Pipenv over plain pip/virtualenv.

## Table of Contents
- [How to install](#how-to-install)
- [How to setup a new pipenv](#how-to-setup-a-new-pipenv)
- [Running stuff in a pipenv](#running-stuff-in-a-pipenv)
- [Removing a pipenv virtualenv](#removing-a-pipenv-virtualenv)

## How to install

Pipenv can be installed using plain pip, assuming you already have that installed.

```bas
pip install pipenv
```

It can also be installed via homebrew on a Mac, though this is discouraged because each time homebrew is upgraded, it could break the version of pipenv installed and required a re-installation:

## How to setup a new pipenv

This section details how to setup up a new pipenv for a project.

From the location of your project where you'd typically have your `requirements.txt` file, and run `pipenv install <packagename>` You should specify package version as well, for security and best practice. For example:

```bash
pipenv install requests==2.28.1
```

This does a couple of things:
- Creates a Pipfile and Pipfile.lock in the project folder
- Creates a new global virtualenv named after the folder the Pipfile is in and a hash of the project's root
- Installs the requsts library to the virtualenv created

## Running stuff in a pipenv

To run a project's scripts in the designated pipenv, simply navigate to the project directory and run:

```bash
pipenv run python <scriptname>.py
```

This automatically runs the script within the project's globally stored virtualenv.

If all packages haven't been installed yet, run the following:

```bash
pipenv install
```

You can also start a shell session within the pipenv:

```bash
pipenv shell
```

## Removing a pipenv virtualenv

If you run into issues with a pipenv, you might need to delete it and start over. TO remove a pipenv, navigate to the project root and run:

```bash
pipenv --rm
```

To clear the project cache:

```bash
pipenv lock --clear
```

