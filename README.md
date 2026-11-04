# Education, Income & Household Welfare in Iran

An empirical Python project exploring how the education of household heads is associated with income and a multidimensional household welfare index in Iranian Household Budget Survey data.

**Ali Abdoli Masinan's contribution:** the education-income analysis, OLS models with interaction terms, and PCA-based household welfare analysis in [`ali.ipynb`](notebooks/ali.ipynb) and [`ali2.ipynb`](notebooks/ali2.ipynb).

**Tools:** Python · pandas · NumPy · Matplotlib · statsmodels · scikit-learn · HBSIR

## Research questions

- How does household-head income vary with education?
- Does the education-income relationship differ across urban/rural areas, genders and provinces?
- How does the picture change when welfare combines income, consumption and expenditure shares?

## Analysis at a glance

The notebooks merge expenditure, income and household-member tables; encode education as years of schooling; and compare additive OLS models with models that include interaction terms. A complementary welfare measure combines regional-price-adjusted, equivalized income and expenditure with food and housing expenditure shares using principal component analysis.

The main multi-year analyses cover **1393–1402 in the Solar Hijri calendar**. Some income cells also attempt 1403, and individual analyses use different year ranges. The notebooks are repeated cross-sectional analyses, not a longitudinal panel of the same households.

![Income models with and without an urban-rural interaction](assets/income-urban-rural-1395.png)

*Example from `ali2.ipynb`: fitted annual head-income models for 1395, in rial. This figure was extracted from the original saved notebook; it was not regenerated during repository preparation.*

## Selected findings

The saved results show a positive association between education and household-head income, with differences across locations. The examples below are taken directly from the existing outputs in [`ali2.ipynb`](notebooks/ali2.ipynb); they are descriptive results from the fitted samples.

- **Education and income:** in the 1395 urban-rural interaction model (27,449 observations), an additional year of education is associated with approximately **5.12 million rial** higher annual head income in rural areas and **9.51 million rial** in urban areas. The urban slope is the sum of the education coefficient and the interaction coefficient.
- **Different slopes across locations:** allowing separate urban and rural education slopes raises the 1395 income model's in-sample R² from **0.083 to 0.088**. This is a modest improvement in fit, not a measure of out-of-sample predictive accuracy.
- **A broader view of welfare:** in the 1394 urban-rural welfare interaction model (27,543 observations), the education slopes are approximately **0.0455 index units** in rural areas and **0.0656** in urban areas. The model's R² is **0.111**. The index combines income, expenditure and expenditure shares rather than measuring income alone.
- **Regional variation:** the five-province welfare comparison for 1393 estimates positive education slopes in all five selected provinces, ranging from approximately **0.00267** in Qom to **0.00730** in Sistan and Baluchestan. These are within-model associations, not a ranking of provinces by overall welfare.

**Where to verify:** see “Urban-rural income models” (1395), “PCA welfare index and urban-rural models” (1394), and “Province interactions: welfare” (1393) in `ali2.ipynb`. Coefficients above are rounded from the saved summaries. The models are unweighted and observational; they do not establish that schooling causes the estimated income or welfare changes. The welfare index is standardized separately by year, so its levels should not be interpreted as absolute welfare growth across years.

## Language

This English overview and the notebook section headings provide an entry point for international readers. The original report, presentation, appendix and many code comments are in Persian, reflecting the language of the original coursework.

## Explore the project

| File | Contents |
|---|---|
| [ali2.ipynb](notebooks/ali2.ipynb) | Start here: total member-income data, household-head income models, welfare construction and regional comparisons |
| [ali.ipynb](notebooks/ali.ipynb) | Employment-income analysis and earlier welfare-index experiments |
| [Project report — Persian](docs/report-fa.pdf) | Group report; student identifiers removed from the public copy |
| [Presentation — Persian](docs/presentation-fa.pdf) | Group presentation |
| [Welfare-index appendix — Persian](docs/welfare-index-appendix-fa.pdf) | Details of the index and interpretation |
| [Contributions](docs/CONTRIBUTIONS.md) | Attribution and scope of individual contributions |
| [Execution and methodology notes](docs/REPRODUCIBILITY.md) | Dependencies, known limitations and validation status |
| [Team reference notebooks](archive/team-notebooks/) | Other group members' original analysis code, with outputs cleared |

## Getting started

The original `ali.ipynb` records **Python 3.10.2** and **HBSIR 0.6.3**. This repository provides a dependency starting point rather than a recovered lockfile.

```bash
python -m venv .venv
```

Activate the environment:

```bash
# Windows PowerShell
.venv\Scripts\Activate.ps1

# macOS / Linux
source .venv/bin/activate
```

Then install the dependencies and open Jupyter:

```bash
python -m pip install -r requirements.txt
python -m jupyter lab
```

Open `notebooks/ali2.ipynb` and execute cells in order. The notebooks obtain data through `hbsir`; the survey data and local cache are **not bundled**. Start with the single-year 1395 cells before running the multi-year loops. Those loops can take substantial time and print exceptions while continuing, so inspect the messages for skipped years.

## Reading the results

This is an exploratory academic analysis. The fitted relationships are associations, not causal estimates of the effect of education. The PCA index is standardized separately within each year, so it describes relative position within that year rather than absolute welfare growth over time. Survey weights are not applied in the supplied models.

The source notebooks include historical execution results. The original saved outputs in Ali’s notebooks are preserved, with local environment-path diagnostics removed. The code was not rerun during repository preparation. See the [execution notes](docs/REPRODUCIBILITY.md) for setup details.

## Team and attribution

This is a collaborative academic project at Sharif University of Technology. The group report names Ali Abdoli Masinan, Mohammad Reza Rahmani and Parsa Mohammadi Torbati. Only `ali.ipynb` and `ali2.ipynb` are attributed to Ali here. See [contributions](docs/CONTRIBUTIONS.md) for the file-level mapping.

No new license has been assigned to the original group work or third-party data in this preparation. Their authors' and providers' rights remain unchanged.
