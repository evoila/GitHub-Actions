# Set up Node.js and install dependencies with npm

This custom action is based on the [action `setup-node` from GitHub](https://github.com/marketplace/actions/setup-node-js-environment),
and extends it by installing Node.js dependencies with npm.

## Why you should use this action

This action:

- enforces [pinning of the Node.js version](https://github.com/actions/setup-node/blob/main/docs/advanced-usage.md#node-version-file), a best practice;
- ensures that npm's lockfile (usually `package-lock.json`) has been committed; and
- [caches dependencies](https://github.com/actions/setup-node#caching-global-packages-data).
