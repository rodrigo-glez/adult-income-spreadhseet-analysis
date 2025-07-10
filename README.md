# Adult Income Analysis Practice

This project explores a sample of U.S. Census data to uncover patterns and relationships related to adult income. The dataset includes demographic and employment-related variables, allowing for both descriptive and inferential analysis.

The goal of this analysis is:

- To practice fundamental data analytics techniques including data cleaning, exploratory data analysis (EDA), and visualization — all performed in Google Sheets.

- To apply inferential statistics to draw conclusions about the broader U.S. working adult population, using confidence intervals and hypothesis testing.

This project is part of my learning journey through the [DeepLearning.AI Data Analytics Professional Certificate](https://www.deeplearning.ai/courses/data-analytics/), and serves as an independent initiative to consolidate my knowladge.

## Data Cleaning

The original dataset includes 32,561 observations (rows) with 15 features (columns) related to demographic and employment data.

In order to simplify analysis, I performed the following cleaning steps:

- Removed rows with missing values (marked as `?`) in the `workclass`, `occupation`, and `native-country` columns. To do this, I:
  - Created a helper column with the formula `=IF(OR(B2="?", G2="?", N2="?"), "remove", "keep")`, which flagged rows with missing data in any of the three columns
  - Applied a filter to the helper column to select the rows marked as `removed`, and delted these rows
  - This step reduced the dataset from 32,561 rows to 30,162 clean rows

- Dropped the fnlwgt column, as it was a sampling weight not required for this analysis.
  
- To simplify income-related analysis and enable proportion and mean comparisons, I created a new column called `income_binary`.
  - I used the formula `=IF(N2=">50K", 1, 0)` which assigns `1` to individuals earning more than $50k and `0` to individuals earning $50k or less

 
