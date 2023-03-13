# GitHub Actions at evoila

## Purpose of this repository

To automate a process with [GitHub Actions](https://docs.github.com/en/actions) at an organization like [evoila](https://www.evoila.de/),

1. the process itself (_what should be done when_) must be defined and agreed upon, and
2. code that automates the process (_how it should be done_) must be developed.

For example, a business unit could

1. agree to check [Markdown](https://daringfireball.net/projects/markdown/) documents (_what_) on pull requests (_when_), and then
2. automate the process with a [GitHub workflow](https://docs.github.com/en/actions/using-workflows/about-workflows) and [`markdownlint`](https://github.com/DavidAnson/markdownlint) (_how_).

This repository serves both purposes.

**On the one hand**,
it hosts code for common processes as a sort of [library](https://en.wikipedia.org/wiki/Library_%28computing%29).
Code sharing is enabled by features of GitHub Actions like

- [reusable workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows) and
- [custom actions](https://docs.github.com/en/actions/creating-actions/about-custom-actions).

This reduces [code duplication](https://en.wikipedia.org/wiki/Duplicate_code),
with all the associated benefits; in particular:

- improvements and fixes are immediatly available to all of [evoila's repositories in GitHub](https://github.com/orgs/evoila/repositories); and
- best practices (which processes usually reflect) are promoted.

[Starter workflows](https://docs.github.com/en/actions/using-workflows/creating-starter-workflows-for-your-organization) are a different thing and do not belong here, but in the [organization's `.github` repository](https://github.com/evoila/.github).

**On the other hand**,
processes are defined and documented in this repository as part of the [GitHub flow](https://docs.github.com/en/get-started/quickstart/github-flow).
Changes may be

- proposed,
- discussed,
- reviewed,
- agreed upon and
- tracked

with GitHub features like

- [issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues),
- [projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects) and
- [pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).

For example, the process of checking Markdown documents on pull requests may be

1. proposed and discussed with an issue and then
2. implemented and reviewed as part of a pull request.
