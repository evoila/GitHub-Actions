# Workflows

This directory contains [workflows](https://docs.github.com/en/actions/using-workflows/about-workflows).
Most of them are [reusable](https://docs.github.com/en/actions/using-workflows/reusing-workflows).

Workflows meant only for this repository and reusable workflows meant for the organization should be in separate directories.
Unfortunately, all workflows must be located in this directory.
This limitation has been brought up in at least two GitHub public feedback discussions:

- [#9050](https://github.com/orgs/community/discussions/9050) and
- [#10773](https://github.com/orgs/community/discussions/10773).

Subdirectories, which would help keep reusable workflows tidy, are not allowed either.

Any GitHub actions called by our workflows and not maintained by either:

- ourselves (either in [this repository](../actions) or some other),
- [GitHub itself](https://github.com/actions) or
- individuals or organizations we trust

must be pinned to git commits instead of tags or branches,
because tags and branches can be modified and such changes could break our workflows and introduce malicious code.
This approach is [endorsed by GitHub](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions#using-third-party-actions) itself:

> Pinning an action to a full length commit SHA is currently the only way to use an action as an immutable release.
> Pinning to a particular SHA helps mitigate the risk of a bad actor adding a backdoor to the action's repository, as they would need to generate a SHA-1 collision for a valid Git object payload.
