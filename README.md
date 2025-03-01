# Project Readme: Food Consumption and Income Analysis in London

## Overview
This project analyzes the relationship between food consumption patterns and household income across different wards in London. The analysis is based on grocery purchase data and income estimates, combined with geographical data to visualize spatial trends. The project includes data preprocessing, visualization, statistical analysis, and predictive modeling.

## Key Features
- **Data Preprocessing**: Cleaning and merging datasets for analysis.
- **Visualization**: Interactive maps and plots to explore food consumption and income patterns.
- **Statistical Analysis**: Correlation analysis and hypothesis testing.
- **Predictive Modeling**: Linear regression, ridge regression, SVM, decision trees, and gradient boosting models to predict income based on food consumption.

## Project Structure
- **Data**: Contains the input datasets (`year_osward_grocery.csv`, `modelled-household-income-estimates-wards.csv`, etc.).
- **Notebooks**: Jupyter notebooks for data analysis and visualization.
- **Output**: Generated visualizations and model results (e.g., `maps.html`).

## Dependencies
The project requires the following Python libraries:
- `pandas`, `numpy`, `geopandas`, `matplotlib`, `seaborn`, `statsmodels`, `scikit-learn`, `bokeh`, `scipy`.

To install the dependencies, run:
```bash
pip install pandas numpy geopandas matplotlib seaborn statsmodels scikit-learn bokeh scipy
```

## Usage
1. **Loading Libraries and Data**:
   - Import necessary libraries and load the datasets.
   ```python
   import pandas as pd
   import geopandas as gpd
   import matplotlib.pyplot as plt
   from bokeh.plotting import figure, show
   grocery = pd.read_csv("year_osward_grocery.csv")
   ```

2. **Data Preprocessing**:
   - Clean and merge datasets for analysis.
   ```python
   df = grocery.rename(columns={'f_beer':'beer', 'f_dairy':'dairy', ...})
   join_df = gdf.join(df.set_index('area_id'), on='GSS_CODE', how='left')
   ```

3. **Visualization**:
   - Generate interactive maps and plots to explore food consumption patterns.
   ```python
   p_meat_red = make_plot('meat_red')
   show(layout)
   ```

4. **Statistical Analysis**:
   - Compute correlations between food categories and income.
   ```python
   correlation_msoa = compute_correlations_categories_incomes(groceries_income_msoa, income='mean_income')
   ```

5. **Predictive Modeling**:
   - Train and evaluate models to predict income based on food consumption.
   ```python
   linear_regression(X_tr, y_tr, X_te, y_te)
   ridge_model(X_tr, y_tr, X_te, y_te)
   ```

## Example Visualizations
### Interactive Maps
![Interactive Map of Food Consumption](images/map_food_consumption.png)
*Interactive map showing the fraction of meat consumption across London wards.*

### Correlation Plots
![Correlation Plot](images/correlation_plot.png)
*Correlation between food categories and mean income.*

### Predicted vs. Actual Income
![Predicted vs. Actual Income](images/predicted_vs_actual.png)
*Scatter plot showing predicted vs. actual mean income.*

## Results
- **Correlation Analysis**: Strong correlations were found between certain food categories (e.g., wine, spirits) and income levels.
- **Predictive Models**: Linear regression and gradient boosting models performed well in predicting income based on food consumption patterns.

## Future Work
- Incorporate additional demographic data for more granular analysis.
- Explore machine learning models for better predictive accuracy.
- Extend the analysis to other cities or regions.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## Contact
For questions or feedback, please contact Mahima Yadav at [mahimayadav97@gmail.com].
