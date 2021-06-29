HERMES Instrument Package Template
==================================

This is a Python template meant for the `HERMES <https://science.nasa.gov/missions/hermes>`_ Instrument package teams though it may be more generally useful.

Using the package template
--------------------------

To generate a new package from the template first install `cookiecutter <https://cookiecutter.readthedocs.io/>`_ then run::

  $ cookiecutter gh:hermes-soc/instrument-package-template


This will create a new directory in your current directory. Change into this directory and run `git init` to make it into a git repository.
This is required for the package to work properly.

Python version
--------------
This package template works only with Python 3.8.

Tox Automation
--------------
The package makes use of `tox <https://tox.readthedocs.io/en/latest/#>`_ as a virtualenv manager to perform many package functions.
To see what is supported see the tox.ini files. For example the following commands are available::

  $ tox -e py38  # run tests on python 3.8
  $ tox -e build_docs  # build your documentation
  $ tox -e codestyle  # test and fix codestyle if needed


Continuous Integration on Github
--------------------------------
This package will automatically set up continuous integration using `Github Actions <https://github.com/features/actions>`_.
This means that continuous integration will be run on githubs servers automatically on every pull request.

Documentation
-------------
Documentation builds make use of the `Sphinx <https://www.sphinx-doc.org/en/master/>`_
documentation generation system. In addition, settings are provided to host the documentation on readthedocs.
To build your documentation run::

  $ tox -e build_docs  # build your documentation


Versioning
----------
This package makes use of `setuptools_scm <https://github.com/pypa/setuptools_scm/>`_ to manage package versioning automatically
with git. See the `default versioning scheme <https://github.com/pypa/setuptools_scm/#default-versioning-scheme>`_, primarily
major versions are set by using git tags.

Pre-commit
----------
This package supports `pre-commit <https://pre-commit.com>`_. To enable this install pre-commit and then run::

  $ pre-commit install


This will install a hook to git which will run a test before you actually commit.

