# Design and source review

The review used the tracked files at commit `db8083687e86dea514e46d7e52f41fd18e87c88c` and compared the paths and contents with GitHub's default-file and funding documentation [@docxologyCommunityFiles; @githubCommunityFiles; @githubFunding]. The review covered the repository overview, the two contributor policies, the pull request template, the two issue forms and chooser configuration, the sponsor URL, and the license. GitHub discovery determines where platform-facing files belong. The documentation index, maintainer guide, backlog, and manuscript are read by people and can share a separate documentation tree.

| Asset | Source evidence and design |
| --- | --- |
| Contribution and security policies | The root policies describe the normal contribution path and private reporting. GitHub supports these filenames at the root. |
| Pull request template | The root template asks for the change, related issues, and confirmation that local checks and documentation were considered. |
| Issue forms and chooser | The audited root directory held both forms and the chooser configuration. The standardized paths place all three under `.github/ISSUE_TEMPLATE/`, as GitHub documents. |
| Funding | The audited root YAML held one custom funding URL. The standardized path is `.github/FUNDING.yml`, which GitHub documents for the Sponsor button. |
| License | The root MIT license applies to this repository. GitHub does not supply account-level default licenses. |

GitHub checks a repository's own eligible files before loading account defaults. A valid issue template or chooser configuration in the current repository supersedes the entire default chooser directory [@githubCommunityFiles]. Repository maintainers considering an override should carry over whichever choices they want to retain, including a route to private security reporting.
