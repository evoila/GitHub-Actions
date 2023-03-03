# Set up Python and install dependencies with Poetry

This custom action is based on the [action `setup-python` from GitHub](https://github.com/marketplace/actions/setup-python),
and extends it by installing [Poetry](https://python-poetry.org/) and then the dependencies listed in `poetry.lock`.

## Why you should use this action

This action:

- enforces [pinning of the Python version](https://github.com/actions/setup-python/blob/main/docs/advanced-usage.md#using-the-python-version-file-input), a best practice;
- installs Poetry in a reproducible way, pinning not only Poetry itself but also its dependencies; and
- ensures that Poetry's lockfile (`poetry.lock`) has been committed, which the [Poetry subcommand `install`](https://python-poetry.org/docs/cli/#install) does not.

It will hopefully also cache the Poetry environment, which is not trivial, at some point.
