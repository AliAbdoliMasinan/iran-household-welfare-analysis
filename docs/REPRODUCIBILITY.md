# Execution notes

The notebooks are shared with their original saved results. They were not rerun during repository preparation, at the author's request. Formatting and documentation changes do not establish that a fresh-kernel Run All succeeds.

## Environment and data

- The original `ali.ipynb` records Python 3.10.2 and HBSIR 0.6.3.
- `requirements.txt` records the observed HBSIR version and imported packages; it is not a complete environment lockfile.
- Survey datasets are loaded externally through HBSIR and are not included in the archive.
- Run cells in order if reproducing the work locally. Start with the single-year 1395 cells before running multi-year loops.
- `ali.ipynb` primarily uses employment-income records. `ali2.ipynb` uses `Members_Total_Income`; its income regressions filter household heads and its welfare calculation aggregates incomes by household.
- Dates are Solar Hijri survey years. Individual loops use different ranges.

## Historical execution context

The supplied output records a data-download error for 1397 in some `ali2.ipynb` welfare loops. Those loops catch errors and continue; an attempted year is not necessarily a completed analysis. Existing messages and results in Ali's notebooks have been preserved rather than regenerated.

The team reference notebooks depend on local CSV/schema paths. `parsa-final.ipynb` imports a `utils` module that was not supplied. They are included as attributed reference material.

## Interpretation

These exploratory models describe associations, not causal effects. They do not apply survey weights. The PCA index is standardized within each year, so comparisons across years describe relative positions rather than common-base absolute welfare growth. The original analysis has not been independently statistically audited.
