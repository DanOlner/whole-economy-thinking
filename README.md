# whole_economy_thinking
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

## To do

- [ ] **Zenodo:** switch this repo on in [Zenodo's GitHub settings](https://zenodo.org/account/settings/github/) before the first release, or no DOI is minted.
- [ ] **GitHub Pages:** Settings → Pages, serve the `/docs` folder from the `master` branch.
- [ ] **Actions:** Settings → Actions → General → Workflow permissions, choose "Read and write", so the two workflows can push their commits.
- [ ] **First release:** the citation workflow writes the version, date and DOI into `CITATION.cff` and `.zenodo.json`. Then add the DOI badge to this README by hand, using the concept DOI (it always points to the latest version), and fill in `doi:` in `chunks.yml`.
- [ ] **Chunk write-up:** write `docs/chunks/tradeable_jobs/index.html`, linking to the two reports. The landing page only lists chunk folders that have an `index.html`, so it stays empty until then.
- [ ] **RegEconWorks:** add a pointer there to this repo.
- [ ] **Authorship tracking:** choose which pieces to switch on, from [llm_output/human_llm_commit_tracking.md](llm_output/human_llm_commit_tracking.md).

## What this is

**whole_economy_thinking** is a modular research repository: small, self-contained chunks of work, each with its own write-up, open to feedback and given a DOI before they're anything as big as a paper. It uses the same layout as [RegEconWorks](https://github.com/DanOlner/RegEconWorks), where its first chunk started.

## What's here

- **Chunk 1: tradeable jobs.** Venables (2018, 2020) and Rice and Venables (2023) rebuilt in R, tested against Ricardian benchmarks and replicated on UK data. Round 2 adds supply chains, payment flows, firm data and a flow model.
  - Round 1 report: [tradeable_jobs_firstlook.qmd](docs/chunks/tradeable_jobs/tradeable_jobs_firstlook.qmd), with its plan in [tradeable_jobs_plan.md](docs/chunks/tradeable_jobs/tradeable_jobs_plan.md).
  - Round 2 report: [tradeable_jobs_round2.qmd](docs/chunks/tradeable_jobs/tradeable_jobs_round2.qmd), with its plan and build log in [tradeable_jobs_further_tests_plan.md](docs/chunks/tradeable_jobs/tradeable_jobs_further_tests_plan.md).
  - Code, and how to rebuild everything from the downloads: [code/tradeable_jobs/](code/tradeable_jobs/README.md).

## Layout

| Folder | What's in it |
|---|---|
| `docs/chunks/<chunk>/` | Each chunk's reports, plans and output CSVs. GitHub Pages serves `docs/`, and a chunk's `index.html` is its write-up. |
| `docs/chunks/chunk_template/` | Starting files for a new chunk |
| `code/<chunk>/` | Each chunk's code, run from the repo root |
| `local/` | Gitignored: downloads, caches and copyright papers. The scripts rebuild it. |
| `llm_convos/` | Exported Claude Code conversations. Only those switched on in its `.gitignore` are published. |
| `llm_output/` | Notes drafted by Claude Code |
| `scripts/` | The landing page generator, the citation updater and the conversation export tools |
| `chunks.yml` | Index of chunks: status, DOI, dependencies, feedback |
| `papers/`, `posts/`, `data/`, `human_journal/` | Empty for now |

## Landing page and DOIs

- **Landing page:** on each push that changes `docs/`, [update-index.yml](.github/workflows/update-index.yml) runs `scripts/generate-index.sh`, which rebuilds `docs/index.html` with a link to every `docs/chunks/*/index.html`.
- **DOIs:** on each GitHub release, [update-citation-on-release.yml](.github/workflows/update-citation-on-release.yml) sets the version and date in `CITATION.cff` and `.zenodo.json`, waits for Zenodo to mint the DOI, and writes it into both.

## Sources outside this repo

- **Flow model:** `code/tradeable_jobs/functions_flow.R` is an R port of the TypeScript build in [modelling_demand](https://github.com/DanOlner/modelling_demand). Its inputs and the TypeScript's reference results are committed in `code/tradeable_jobs/flow_model/`, so the rebuild doesn't need that repo.
- **Firm data (test T11a):** the companieshouseopen project's report outputs, read in place from `~/Code/companieshouseopen/local/reports`. The T11a script does nothing if they aren't on the machine.

## History

This work began in [RegEconWorks](https://github.com/DanOlner/RegEconWorks). The commits that built it, up to `9e23c54` (14 November 2026), are there: see the history of [code/tradeable_jobs](https://github.com/DanOlner/RegEconWorks/commits/master/code/tradeable_jobs) and [docs/chunks/tradeable_jobs](https://github.com/DanOlner/RegEconWorks/commits/master/docs/chunks/tradeable_jobs). The Claude Code conversation that built it is in [llm_convos/](llm_convos/).

## Packages

The versions used for the November 2026 build. There's no renv lockfile.

- **R 4.5.1** and **Quarto 1.8.26**.
- **R packages:**

| Package | Version | Used for |
|---|---|---|
| dplyr | 1.2.1 | Everything |
| tidyr | 1.3.1 | Everything |
| readr | 2.1.5 | Everything |
| readxl | 1.4.5 | ONS spreadsheets |
| ggplot2 | 4.0.0 | Figures |
| scales | 1.4.0 | Figures |
| jsonlite | 2.0.0 | Flow model inputs |
| tidyverse | 2.0.0 | Reports |
| knitr | 1.50 | Reports |
| ggrepel | 0.9.6 | Reports |
| data.table | 1.17.8 | Payment flows |
| arrow | 22.0.0.1 | Firm data (T11a) |
| fixest | 0.14.2 | Firm data (T11a) |
| lme4 | 1.1.37 | Firm data (T11a) |

- **`get_papers.py`** (optional): Python 3.12, `curl`, and poppler 26.01 for `pdftotext` and `pdftoppm`.

## How to give feedback

See the [feedback doc](FEEDBACK.md). Any feedback, however big or small, ends up in the contributor list below.

## Licence

- **Code:** [MIT](LICENSE)
- **Text:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- **Data:** the scripts download their own data from ONS and Nomis. [code/tradeable_jobs/README.md](code/tradeable_jobs/README.md) lists the sources.

## LLM

*Drafted by Claude Code from the RegEconWorks README, November 2026.*

## Contributors

Via the [All Contributors bot](https://allcontributors.org) and manual addition to the list for people without GitHub accounts.
<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="http://danolner.net"><img src="https://avatars.githubusercontent.com/u/5830743?v=4?s=100" width="100px;" alt="Dan Olner"/><br /><sub><b>Dan Olner</b></sub></a><br /><a href="#design-DanOlner" title="Design">🎨</a> <a href="https://github.com/DanOlner/whole_economy_thinking/commits?author=DanOlner" title="Code">💻</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->
