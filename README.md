# Exploratory Analysis of Airbnb Listings in 9 European Cities

Exploratory data analysis of 41,714 Airbnb listings in Amsterdam, Athens, Barcelona, Berlin, Budapest, Lisbon, Paris, Rome and Vienna, to understand which factors are associated with price and guest satisfaction.

**Business goal:** give hosts a reference for pricing and for prioritising what improves their ratings, and help guests understand why prices vary across cities.

*Notebook written in Spanish.*

## Data

[Airbnb Cleaned Europe Dataset](https://www.kaggle.com/datasets/dipeshkhemani/airbnb-cleaned-europe-dataset) (Kaggle), file `Aemf1.csv`: 41,714 listings, 19 columns.

The data is not included in this repository. Download `Aemf1.csv` from Kaggle and place it in a `data/` folder.

## Approach

1. **Data check:** verified data types and missing values (none); dropped 4 attraction and restaurant index columns and worked with 15 variables.
2. **Outliers:** price is highly skewed (mean ≈ €260, median ≈ €204, max ≈ €18,545), so chart axes were capped for readability.
3. **Univariate analysis:** average price by city, room type, capacity and distances.
4. **Bivariate analysis:** price vs. distance (OLS trendline), satisfaction vs. cleanliness and price bands, weekday vs. weekend.
5. **Multivariate analysis:** correlation matrices and superhosts vs. regular hosts. Detected multicollinearity between Room Type and Shared Room and explained apparently contradictory correlations, such as private room vs. price (−0.15).

## Key findings

- **Amsterdam** has the highest average price (≈ €573), followed by **Paris** (≈ €393); **Athens** (≈ €152) and **Budapest** (≈ €177) are the cheapest.
- **Cleanliness** is the variable most strongly and positively associated with guest satisfaction.
- **Distance to the metro and to the city centre** are the variables most associated with price, metro distance more so; the highest prices are within 500 m of a metro station.
- Satisfaction is concentrated above 80 in every price band: **no relationship between price and satisfaction**.
- **Superhosts** have higher satisfaction and cleanliness, a slightly lower average price and listings slightly further from the centre.
- **Capacity** is the room variable most associated with price, although the correlation is weak (≈ 0.18).
- Price does not vary noticeably between **weekdays and weekends**.

## How to run

Install the libraries: `pip install pandas plotly statsmodels kaleido jupyter`

Download `Aemf1.csv` from Kaggle, put it in a `data/` folder next to the notebook, and run `airbnb_europe_eda.ipynb`.

## Tools

Python · pandas · Plotly · Statsmodels (OLS trendlines)
