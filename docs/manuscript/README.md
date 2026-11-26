# Shared GitHub Community Defaults for docxology Repositories

Read the [abstract](00_abstract.md), [purpose](01_purpose.md), [source review](02_design.md), [contributor workflow](03_workflow.md), and [limitations](04_limitations.md). The numbered files set the reading order. [`config.yaml`](config.yaml) controls metadata and formats. [`references.bib`](references.bib) records the audit snapshot and GitHub documentation used in the text.

## Render and validate

From a fresh checkout of the [pinned template](https://github.com/docxology/template/tree/87704feae0a4490ef7dad9c931d268e8c30273c2), install Python 3.14+, `uv`, Pandoc, and XeLaTeX with the TeX packages in the [template setup guide](https://github.com/docxology/template/blob/87704feae0a4490ef7dad9c931d268e8c30273c2/README.md#L565-L574). Set `PROFILE_CHECKOUT` to the absolute path of a clean checkout of this repository at the revision you want to render. From a directory where you can create a fresh template checkout, run:

```sh
git clone https://github.com/docxology/template.git docxology-template
cd docxology-template
git checkout --detach 87704feae0a4490ef7dad9c931d268e8c30273c2
uv sync --locked
mkdir -p projects/working
git -C "$PROFILE_CHECKOUT" worktree add --detach \
  "$PWD/projects/working/github-profile" HEAD
uv run python scripts/pipeline/stage_03_render.py --project working/github-profile
uv run python scripts/pipeline/stage_04_validate.py --project working/github-profile
```

The runner discovers `docs/manuscript/` in the registered project. Open the combined PDF at `projects/working/github-profile/output/pdf/*_combined.pdf` and the HTML at `projects/working/github-profile/output/web/index.html`. Check the abstract, review table, workflow, limitations, and resolved GitHub and repository citations. Validation records provenance in the staged project's output directory.
