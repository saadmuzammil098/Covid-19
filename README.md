# Covid-19 Impact Analysis

A single Jupyter notebook that analyzes COVID-19 spread and its economic impact using `transformed_data.csv` and `raw_data.csv`, aggregating total cases/deaths, Human Development Index (HDI), and Stringency Index by country, then comparing the top-10 hardest-hit countries' GDP per capita before vs. during the pandemic (hardcoded GDP figures).

## Tech stack

- Python
- pandas
- Plotly (`plotly.express`, `plotly.graph_objects`) for bar, grouped-bar, and pie charts
- Jupyter Notebook

## Architecture

```mermaid
flowchart LR
    A["raw_data.csv"] --> C["Aggregate per country:\nHDI, Stringency Index (STI),\ntotal cases, total deaths,\npopulation"]
    B["transformed_data.csv"] --> C
    C --> D["Sort by Total Cases,\ntake top 10 countries"]
    D --> E["Attach hardcoded\nGDP per capita\n(before vs during Covid)"]
    D --> F["Bar charts:\nTotal Cases / Total Deaths\nby country"]
    D --> G["Pie chart:\nCases vs Deaths %,\nDeath rate calculation"]
    D --> H["Bar charts colored by\nStringency Index / HDI"]
    E --> I["Grouped bar chart:\nGDP before vs during Covid"]
    F --> J["Conclusion:\nUS had highest cases/deaths,\nlinked to low stringency index;\nGDP per capita dropped across\nall top-10 countries"]
    G --> J
    H --> J
    I --> J
```

## Setup / How to run

The repo contains only the notebook, `COVID-Analysis.ipynb`; the source CSVs (`transformed_data.csv`, `raw_data.csv`) are not included in the repository and must be supplied separately to reproduce the analysis.

1. Install dependencies: `pip install pandas plotly`
2. Place `transformed_data.csv` and `raw_data.csv` in the same directory as the notebook.
3. Open and run `COVID-Analysis.ipynb` in Jupyter.
