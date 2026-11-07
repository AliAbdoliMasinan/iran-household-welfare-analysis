# Running the notebooks

## Environment and data

- `ali.ipynb` records Python 3.10.2 and HBSIR 0.6.3. Install the dependencies from `requirements.txt`.
- The notebooks load survey data through HBSIR. The survey files are separate from this repository.
- Start with the single-year 1395 cells in `ali2.ipynb` and run them in order before trying the multi-year loops. All survey years use the Solar Hijri calendar.
- `ali.ipynb` primarily uses employment-income records. `ali2.ipynb` uses `Members_Total_Income` for both household-head regressions and household-level income totals.

## Saved results and known issues

The notebooks include saved plots and model summaries. In `ali2.ipynb`, some welfare loops record a download error for 1397. The loops continue after an error, so check the output for skipped years.

The team notebooks use local CSV and schema paths. `parsa-final.ipynb` also requires a separate `utils` module.

## Interpreting the results

The OLS models estimate associations from unweighted survey data. The PCA welfare index is standardized within each survey year and measures relative welfare within that year.
