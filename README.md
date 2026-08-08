# niriga

Like [nixpkgs-review-gha][],
but simple/featureless and security-focused.

[nixpkgs-review-gha]: https://github.com/Defelo/nixpkgs-review-gha

## Why

When used incorrectly,
it is [easy to have security vulnerabilities][gha-vul]
in GitHub Actions.
Attackers can get
your GitHub token or other secrets
when that happens.

This project aims to
only run [nixpkgs-review][] against Nixpkgs PRs
using GitHub Actions
with [security best practices][gha-secure-use],
including but not limited to:

- `GH_TOKEN` with empty permissions
- No secrets
- No [cache][gha-cache]
- Dependencies pinned to git commit hash
- Dependencies regularly updated

[gha-vul]: https://www.youtube.com/watch?v=z68feG_L4yE
[nixpkgs-review]: https://github.com/Mic92/nixpkgs-review
[gha-cache]: https://docs.github.com/en/actions/reference/workflows-and-actions/dependency-caching
[gha-secure-use]: https://docs.github.com/en/actions/reference/security/secure-use

## Usage

1. [Fork][] this project.
1. [Enable][enable-dependabot-upd]
   "Dependabot version updates"
   in your fork.
1. [Enable][enable-dependabot-sec]
   "Dependabot security updates"
   in your fork.
1. Go to the "Actions" tab in your fork
   and enable GitHub Actions.
1. To run nixpkgs-review against a Nixpkgs PR,
   [run][manually-run-gha] the [nixpkgs-review workflow][]
   in your fork.
   The report is available
   in the "Show reports" step of the "Show reports" job
   after the workflow finishes.

[Fork]: https://github.com/jian-lin/niriga/fork
[enable-dependabot-upd]: https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-version-updates#enabling-version-updates-on-forks
[enable-dependabot-sec]: https://docs.github.com/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-security-updates#enabling-or-disabling-dependabot-security-updates-for-an-individual-repository
[manually-run-gha]: https://docs.github.com/en/actions/how-tos/manage-workflow-runs/manually-run-a-workflow#running-a-workflow
[nixpkgs-review workflow]: /.github/workflows/nixpkgs-review.yaml

## Status

This project is usable now.

This project is under development.
Expect any kind of changes.

## Acknowledgment

This project is inspired by [nixpkgs-review-gha][].

## License

[AGPL-3.0-or-later](https://spdx.org/licenses/AGPL-3.0-or-later.html)
