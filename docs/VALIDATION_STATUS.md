# Validation status

Last checked: 2026-11-17.

## Completed
- Rewrote the AADR exact-sample notebook as a strict no-proxy sample-discovery and validation workflow.
- Removed nearest-proxy selection and the simplex-constrained allele-frequency fit that could be mistaken for qpAdm.
- Added project/method descriptions, comments, explicit cohort rules, provenance exports and missing-cohort audit.
- Parsed all Python notebook cells.
- Executed offline synthetic tests for exact modern labels, ancient period/site matching, outlier exclusion and no-proxy behavior.

## Not completed
- Live AADR retrieval: this environment cannot resolve/connect to dataverse.harvard.edu.
- Full live notebook execution against the current AADR release.
- Shiny runtime test: R/Rscript is not installed here.
- ADMIXTOOLS 2 integration test against a pinned genotype dataset.
- Cloud deployment.

## Required before scientific use
1. Run the notebook in Colab/Jupyter with network access and inspect returned AADR group IDs.
2. Verify sample context, dates, authentication, coverage and relatedness from original studies.
3. Resolve source overlaps and target/source overlaps before modelling.
4. Test the Shiny/ADMIXTOOLS 2 engine on a pinned small public dataset.
5. Reproduce paper-specific SNP, outgroup, qpWave/qpAdm and sensitivity choices from Agranat-Tamir et al. (2020) and its supplement.
6. Archive configuration, dataset release, checksums, session information, logs and all model diagnostics.
