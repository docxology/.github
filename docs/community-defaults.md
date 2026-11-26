# Contributor and maintainer guide

## Contributing to a docxology project

Open issues and pull requests in the affected repository. Check its README, contribution guide, and open work before starting. Follow its local instructions, use a focused branch and pull request, and run its tests or validators. For research contributions, cite sources, retain data provenance, and confirm that you can share the material. See the [default contribution guide](../CONTRIBUTING.md).

Use the bug form for unexpected behavior. Provide the behavior and reproduction steps, and include the version, environment, and relevant logs when available. Use the feature form to explain the problem an improvement would solve. The shared chooser also allows blank issues and links to the [security policy](../SECURITY.md). Follow the affected repository's security policy for vulnerabilities. The shared policy lists private reporting through the repository's Security tab where available and an email alternative.

## File locations and settings

| File | Role |
| --- | --- |
| [`CONTRIBUTING.md`](../CONTRIBUTING.md) | Shared contributor guidance. |
| [`SECURITY.md`](../SECURITY.md) | Shared instructions for private vulnerability reports. |
| [`PULL_REQUEST_TEMPLATE.md`](../PULL_REQUEST_TEMPLATE.md) | Prompts for a summary, related issues, local verification, documentation, and handling private material. |
| [`.github/ISSUE_TEMPLATE/`](../.github/ISSUE_TEMPLATE/) | Bug and improvement forms and the issue chooser configuration. |
| [`.github/FUNDING.yml`](../.github/FUNDING.yml) | Custom URL for the Sponsor button. |
| [`LICENSE`](../LICENSE) | MIT terms for this repository. Each project supplies its own license. |

GitHub reads supported defaults from the public `.github` repository when an owned repository lacks a corresponding local file. A valid local issue template or chooser configuration replaces the entire default chooser directory. The `bug` and `enhancement` labels used by the forms must exist in this repository and in each repository that uses the forms. For supported multi-location defaults, GitHub checks the `.github` directory, then the repository root, then `docs/`. Use the configured paths above for the shared files. See [GitHub's default community health documentation](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

## Editing and verification

Clone `https://github.com/docxology/.github.git` and work on a branch. Community files are consumed by GitHub and require no local application runtime. Review the Markdown links from a clean checkout with [Lychee](https://lychee.cli.rs/), using offline mode to check tracked local targets independently of network availability.

```sh
git diff --check
lychee --offline README.md CONTRIBUTING.md SECURITY.md 'docs/**/*.md'
```

Review YAML changes against GitHub's [issue form syntax](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms) and [funding syntax](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/displaying-a-sponsor-button-in-your-repository). After a change reaches the default branch, inspect **New issue**, **New pull request**, **Security**, and the **Sponsor** button on a representative repository that uses the defaults. Check the form labels and contact link without submitting an issue or a report. For comparison, inspect the chooser on a repository with its own issue configuration. These checks depend on repository settings, access, and GitHub's applied defaults.

The documentation is Markdown for GitHub. To generate the manuscript as PDF and HTML, use the [pinned render instructions](manuscript/README.md).
