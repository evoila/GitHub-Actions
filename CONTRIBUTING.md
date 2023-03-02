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
