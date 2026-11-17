# AncestryLab — Ancient DNA Population-Genetics Research Toolkit

An application-first research project for reproducible ancient-DNA workflows. The repository currently contains the Shiny application source archive (ancestrylab-app.zip). The corrected AADR sample-discovery notebook is supplied separately as AADR_Exact_Sample_Discovery_No_Proxies.ipynb in the accompanying project bundle.

> **Scientific status:** research prototype. Python syntax and synthetic cohort-selection tests pass. A live AADR run and R/ADMIXTOOLS 2 runtime integration test have not yet been completed in this environment. Do not treat the project as publication-validated until the validation checklist is complete.

## Statistical scope

The Shiny app orchestrates published ADMIXTOOLS 2 methods for f2, f3, f4/D, FST, qpWave, qpAdm, qpGraph and FindGraph. FindGraph is an ADMIXTOOLS 2 graph-search function. GhostBuster is a separate optional program requiring Relate-inferred genealogical trees and genetic maps; it is not interchangeable with qpAdm or f-statistics.

## Exact AADR sample discovery — no proxies

The companion notebook is a sample-discovery stage only. It queries the current public AADR release, downloads .ind and .anno metadata, matches modern groups by exact labels and ancient cohorts by declared site/entity/date/period rules, and exports a sample inventory and audit.

- Modern targets require exact AADR group-label aliases and present-day annotation.
- Ancient cohorts require explicit site/name, political entity, date range and (where specified) period-token criteria.
- Regional Europe, Greece Bronze Age and Iran Chalcolithic sets are labelled composites.
- Missing groups remain missing. No geographically, temporally, genetically or label-nearest population is substituted.
- The notebook does not calculate ancestry proportions and does not claim to reproduce the formal analyses of Agranat-Tamir et al. (2020).

## Run the app

With R and dependencies installed, launch from the project root:

```r
shiny::runApp("app", host = "0.0.0.0", port = 3838)
```

Or use the Docker template:

```bash
docker compose up --build
```

For exact sample discovery, open the corrected notebook in Colab/Jupyter with internet access. It downloads only the compact metadata in this stage, not the multi-gigabyte genotype matrix.

## Paper-specific reproduction

For *The Genomic History of the Bronze Age Southern Levant* (Agranat-Tamir et al., 2020), reproduce the actual target/source cohorts, SNP intersection, right/outgroup set, qpWave/qpAdm design, uncertainty procedure and sensitivity analyses from the paper and supplement. Do not replace those methods with a generic least-squares mixture fit. The corrected notebook intentionally stops before formal modelling.

## Validation

See [docs/VALIDATION_STATUS.md](docs/VALIDATION_STATUS.md). Offline synthetic selector tests pass. Live Dataverse retrieval was blocked here by outbound DNS/network restrictions. R/Rscript was unavailable, so the Shiny application and ADMIXTOOLS 2 wrappers have not been runtime-tested here. A pinned real-data integration test is required before scientific use.

## References

- Agranat-Tamir et al. (2020): https://doi.org/10.1016/j.cell.2020.04.024
- AADR: https://doi.org/10.7910/DVN/FFIDCW
- AADR resource paper: https://www.nature.com/articles/s41597-024-03031-7
- ADMIXTOOLS 2 documentation: https://uqrmaie1.github.io/admixtools/
- ADMIXTOOLS 2 source: https://github.com/uqrmaie1/admixtools
- Original ADMIXTOOLS: https://github.com/DReichLab/AdmixTools
- GhostBuster: https://github.com/MyersGroup/GhostBuster

AncestryLab orchestration code is MIT-licensed. Upstream datasets and tools retain their own licenses and citation requirements. No genotype dataset is bundled.