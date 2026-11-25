# Tech Challenge 1 · Brazilian wine exports

Which countries bought the most Brazilian wine between 2009 and 2023? Using Embrapa’s VitiBrasil series, this project ranks export destinations by revenue and compares sustained sales with short-lived peaks. [Analysis notebook](notebooks/tech_challenge_1.ipynb) · [Download the illustrated report](reports/wine-exports.html?raw=1)

## Findings

| Destination | What the data show |
| --- | --- |
| Paraguay | Ranked first at $42.86 million. Annual exports rose from $392,000 in 2009 to $5.52 million in 2023. |
| Russia | Ranked second at $23.15 million, with sales concentrated in 2012–2014. |
| United States | Ranked third, with $9.31 million over the period. |
| Uruguay and Haiti | Had the highest compound annual growth rates among the 20 largest destinations, at 47.40% and 42.94%. Uruguay’s first positive observation in the study window was in 2010, Haiti’s in 2009. |

The notebook calculates cumulative growth and compound annual growth between the first and last years with positive revenue. For selected destinations, it fits a separate linear regression to the positive years and projects export revenue for 2024–2028, with a floor of zero. The projections reflect the history available through 2023.

## Data

The three tables cover 1970–2023. The export table records national shipments by destination. Each year has one quantity column in kilograms and one value column in US dollars. Embrapa groups the series under table wine and includes all wine types in trade codes 2204.21 and 2204.29 from 1996 onward. Production and domestic sales cover Rio Grande do Sul and provide regional context. English labels retain the source row IDs and historical destination distinctions. [Embrapa VitiBrasil export statistics](https://vitibrasil.cnpuv.embrapa.br/index.php?opcao=opt_06)

| File | Contents |
| --- | --- |
| [Wine exports](data/wine_exports.csv) | Annual quantities and values by destination |
| [Production](data/production.csv) | Annual production by product and group |
| [Domestic sales](data/domestic_sales.csv) | Annual domestic sales by product and group |

## Run locally

Use Python 3.12. From the repository root, create a virtual environment, activate it, then run the following commands. In JupyterLab, choose **Run → Run All Cells** to reproduce the tables and plots. The downloaded HTML report also opens directly in a browser.

```shell
python -m pip install -r requirements.txt
python -m jupyterlab notebooks/tech_challenge_1.ipynb
```

The analysis uses pandas, NumPy, Matplotlib, Seaborn and scikit-learn.

Luiz Carvalho · FIAP postgraduate program in Data Analytics. [GitHub profile](https://github.com/latcj)
