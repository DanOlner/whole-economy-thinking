# Notes for Claude: whole_economy_thinking

## Linking to sources outside this folder

Files in this repo can link to sources outside it, such as notes and data in other local repos. Use a path or link that says where the source lives. Dan checks before committing that it's fine to reference any private-access files.

## Sources outside this repo

### Firm-level data

- `~/Code/companieshouseopen/claude/uk_firm_data_sources.md` (written 23 October 2026). It covers UK firm-level data beyond Companies House:
  - the secure-access datasets (IDBR, BSD, LBD, ARDx, BRES microdata, HMRC Datalab), including whether each carries company numbers;
  - how to get access now that the Integrated Data Service has closed;
  - how these sources link to Companies House, including registered office versus site;
  - open and paid sources, sorted by what they say about firms;
  - the coming Statistical Business Register.
- `~/Code/companieshouseopen/claude/companies_house_ixbrl_and_profit_loss_filing.md` (checked 24 October 2026). It covers company accounts as a source for GVA:
  - small companies and micro-entities can still leave their profit-and-loss account out of what they file at Companies House, after the October 2026 pause; iXBRL software filing from April 2028 goes ahead;
  - HMRC gets full statutory accounts, including the profit-and-loss account, in iXBRL with the Company Tax Return (since 2011), with caveats on coverage;
  - existing uses of tax and accounts data for GOS and GVA (ONS, the CenTax Business-to-Worker Register), and an accounts-based GVA formula;
  - the open questions for using it: what a Datalab project can see, coverage gaps, and placing GVA at workplaces rather than registered offices.

### Flow model

- [modelling_demand](https://github.com/DanOlner/modelling_demand) (public GitHub repo). The "where GVA is booked" flow model that `code/tradeable_jobs/functions_flow.R` was ported from. The model spec is `research/notes/model-spec-v1.md`, the TypeScript engine is under `build/src/`, and the build log is `build/plan_docs/build-worklog.md`. The R port's inputs and the TypeScript's reference results are committed in `code/tradeable_jobs/flow_model/`.

## Where this work came from

The tradeable jobs chunk was built in RegEconWorks (`~/Code/Regecon_modular_writeup`, https://github.com/DanOlner/RegEconWorks) and copied here on 18 November 2026. Its commit history up to then is in that repo.
