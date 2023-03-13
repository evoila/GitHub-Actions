# Workflows

This directory contains [workflows](https://docs.github.com/en/actions/using-workflows/about-workflows).
Most of them are [reusable](https://docs.github.com/en/actions/using-workflows/reusing-workflows).

Workflows meant only for this repository and reusable workflows meant for the organization should be in separate directories.
Unfortunately, all workflows must be located in this directory.
This limitation has been brought up in at least two GitHub public feedback discussions:

- [#9050](https://github.com/orgs/community/discussions/9050) and
- [#10773](https://github.com/orgs/community/discussions/10773).

Subdirectories, which would help keep reusable workflows tidy, are not allowed either.
