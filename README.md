# UN Regression Analysis: GDP per Person and Fertility

## Overview
This project examines the relationship between economic conditions and fertility using a United Nations dataset. I compare a regression using the original measurements with a **log-log regression** to investigate whether transforming the variables gives a clearer linear representation of their association.

## Research Question
How is GDP per person associated with fertility, and how does the relationship differ between original-scale and logarithmic regression specifications?

## Data
- **Source file:** `HW4_UN1.csv`
- **Variables:** `PPgdp` (GDP per person), `Fertility`, `LogPPgdp`, and `LogFertility`
- **Analysis level:** Observations supplied in the UN dataset

The logarithmic variables are used for the transformed regression. Log models require positive values for GDP per person and fertility.

## Methodology
1. Used scatterplots to examine the relationship on ordinary and logarithmic axes.
2. Fitted an **original-scale ordinary least squares (OLS)** model: `Fertility ~ PPgdp`.
3. Fitted a **log-log OLS** model: `LogFertility ~ LogPPgdp`.
4. Examined regression summaries and ANOVA F-tests for both specifications.
5. Added fitted regression lines to visualize each relationship.

## Selected Results
| Metric | Original-scale model | Log-log model |
|---|---:|---:|
| R² | 0.2147 | 0.4591 |
| Adjusted R² | 0.2106 | 0.4563 |
| ANOVA F statistic | 52.22 | 162.15 |
| Overall p-value | < 0.001 | < 0.001 |

Both estimated relationships were negative: higher GDP per person was associated with lower fertility in this sample. The log-log model showed a stronger linear relationship **on the log-transformed outcome scale** and reduced the influence of extreme GDP observations in the visual analysis.

**Interpretation caution:** The models use different response scales, so their R² values and F statistics are not directly interchangeable as measures of predictive accuracy on the original fertility scale. A fair out-of-sample comparison would transform predictions back to common units and evaluate them with the same error metric.

These findings are correlational; the analysis does not establish that changes in GDP cause changes in fertility.

## Tools
Python, Jupyter Notebook, pandas, NumPy, Matplotlib, statsmodels, and SciPy.

## Repository Files
```text
un-regression-analysis/
├── README.md
├── notebooks/
│   └── un_fertility_gdp_regression.ipynb
└── data/
    └── HW4_UN1.csv
```

**Before uploading:** `un_fertility_gdp_regression.ipynb` is the suggested name for the UN analysis extracted from your original combined `DrugCost_UN_Analysis.ipynb`. Include the dataset only if redistribution is permitted.

## How to Run
1. Open `notebooks/un_fertility_gdp_regression.ipynb` in Jupyter Notebook or JupyterLab.
2. Make sure the Python libraries listed above are installed.
3. Update the CSV path to `../data/HW4_UN1.csv` if following this layout.
4. Execute the notebook cells in sequence.

## Limitations and Next Steps
This is an observational analysis with simple bivariate specifications. Future work could incorporate additional covariates, inspect residuals, and compare out-of-sample prediction errors on a consistent response scale.
