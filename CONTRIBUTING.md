# Contribution guidelines

## Resources

GitHub provides the **reference documentation** and primary learning material for:

- [custom actions](https://docs.github.com/en/actions/creating-actions/about-custom-actions),
- [workflows](https://docs.github.com/en/actions/using-workflows/about-workflows) in general and
- [reusable workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows) in particular.

GitHub also offers:

- [numerous actions](https://github.com/actions), most of which are [JavaScript actions](https://docs.github.com/en/actions/creating-actions/about-custom-actions#javascript-actions);
- [a few reusable workflows](https://github.com/actions/reusable-workflows); and
- [many starter workflows](https://github.com/actions/starter-workflows).

These are most of the best **working examples**, because:

- their source code is open;
- they are widely used and therefore well tested; and
- they are developed by GitHub itself.

The source code for [custom actions in the Marketplace](https://github.com/marketplace?type=actions) is open too, because GitHub requires it:

> Actions are published to GitHub Marketplace […] as long as they meet these requirements:
>
> - The action must be in a public repository.
> - […]

However, the quality of third-party actions varies.

## Security

Any action that we call and is not maintained by either:

- ourselves (whether in [this repository](../actions) or some other),
- [GitHub itself](https://github.com/actions) or
- individuals and organizations we trust

must be pinned to git commits (i.e. hashes) instead of tags or branches (e.g. `v3`),
because tags and branches can be modified and such changes could not only break our workflows, but also introduce malicious code.
This approach is [endorsed by GitHub itself](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions#using-third-party-actions):

> Pinning an action to a full length commit SHA is currently the only way to use an action as an immutable release.
> Pinning to a particular SHA helps mitigate the risk of a bad actor adding a backdoor to the action's repository, as they would need to generate a SHA-1 collision for a valid Git object payload.

## Testing

We agree to test changes to this codebase with some tools.

If we used different versions of these tools, we could get different results.
Therefore, everyone should use the same version of each tool and its respective dependencies.
The best way to accomplish that is to install them with package managers that support [lockfiles](https://blog.shalvah.me/posts/understanding-lockfiles), like:

- [npm](https://docs.npmjs.com/cli/v9/commands/npm) for JavaScript and TypeScript tools;
- [Poetry](https://python-poetry.org/) for Python tools; and
- [Bundler](https://bundler.io/) for Ruby tools.

After you clone this repository, install:

- JavaScript and TypeScript tools [locally](https://docs.npmjs.com/downloading-and-installing-packages-locally) with the [npm subcommand `ci`](https://docs.npmjs.com/cli/v9/commands/npm-ci):

  ```Shell
  $ npm ci

  added 34 packages, and audited 35 packages in 527ms

  7 packages are looking for funding
    run `npm fund` for details

  found 0 vulnerabilities
  ```

- Python tools in a [virtualenv](https://docs.python.org/3/glossary.html#term-virtual-environment) with the [Poetry subcommand `install`](https://python-poetry.org/docs/cli/#install):

  ```Shell
  $ poetry install
  Creating virtualenv dummy-1-4uI-Ox-py3.10 in /home/djsp/.cache/pypoetry/virtualenvs
  Installing dependencies from lock file

  Package operations: 3 installs, 1 update, 0 removals

    • Installing pathspec (0.11.0)
    • Installing pyyaml (6.0)
    • Updating setuptools (65.6.3 -> 67.6.0)
    • Installing yamllint (1.29.0)
  ```

### Markdown

Check [Markdown](https://daringfireball.net/projects/markdown/) documents you add or modify with [markdownlint-cli2](https://github.com/DavidAnson/markdownlint-cli2), a JavaScript tool.
After you install JavaScript tools, you can invoke it through the [command `npx`](https://docs.npmjs.com/cli/v9/commands/npx):

```Shell
$ npx -- markdownlint-cli2
markdownlint-cli2 v0.6.0 (markdownlint v0.27.0)
Finding: **/*.md !.git/ !node_modules/
Linting: 4 file(s)
Summary: 0 error(s)
```

You can set up exceptions for this entire repository in the [configuration file `.markdownlint-cli2.yaml`](.markdownlint-cli2.yaml).

### YAML

Check [YAML streams](https://yaml.org/spec/1.2.2/#streams) you add or modify with [yamllint](https://github.com/adrienverge/yamllint), a Python tool.
After you install Python tools, you can invoke it through the [Poetry subcommand `run`](https://python-poetry.org/docs/cli/#run):

```Shell
poetry run -- yamllint -- .
```
