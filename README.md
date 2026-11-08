# Community environment, temperature and incident cardiometabolic multimorbidity

Analysis materials for *Community built environment and long-term temperature exposure in relation to incident cardiometabolic multimorbidity: A cohort study in China*.

## Download the code and verification data

Download [cmm_reproducibility_v1.0.zip](cmm_reproducibility_v1.0.zip) and extract it to a local directory. The archive preserves the analysis directory structure and includes:

- 16 selected R analysis scripts and a stage-specific entry point;
- input requirements, execution order, named environment overrides and software documentation;
- non-identifiable aggregate model results, exposure cutoffs, spline knots, imputation settings and province-level baseline temperatures;
- a standard-library Python verifier, which checks saved aggregate outputs.

From the extracted directory, run `python verify_aggregate.py` for the aggregate audit. R requires authorized local inputs; read `INPUTS.md`, `ENVIRONMENT_VARIABLES.md` and `RUN_ORDER.md` before using `Rscript run_stage.R`. Run `Rscript run_stage.R --list` to list selected stages.

The archive was checked by parsing 17 R files (including the entry point) and verifying saved aggregate results. These checks are not a participant-level rerun of all models. This is an analysis-from-prepared-inputs release, not a complete raw-data-to-publication pipeline. The archive contains no individual-level CHARLS records, participant identifiers, imputation objects, account credentials or local account configuration.

## Source data and licensing

Participant data must be obtained through [CHARLS](https://charls.pku.edu.cn/) under its access terms. They are not redistributed or relicensed here.

Temperature source: Zhang, L., Hu, Y., Zhao, Y., Che, T. (2025), *ChinaMet*, National Cryosphere Desert Data Center. DOI: https://doi.org/10.12072/ncdc.nieer.db6722.2025. ChinaMet is available under CC BY 4.0. The study used supplied provincial Tmax/Tmin summaries for 2008–2010; their original grid selection and spatial weighting are not documented in the available archive. Study exposures are provincial, not individual grid-level assignments. Details are in `PROVENANCE.md` inside the archive.

Code is released under the MIT license in [LICENSE](LICENSE). Archive integrity can be checked with [SHA256SUMS.txt](SHA256SUMS.txt).
