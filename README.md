Data pipeline file description

This set of Python notebooks shows the entire end-to-end data pipeline that was used for the analysis of the research paper
Bachmann et al. (2023) "A Temporary VAT Cut as Unconventional Fiscal Policy" 
(https://sites.nd.edu/rbachman/files/2023/04/BBGKLW_current.pdf)

See https://bfi.uchicago.edu/insight/finding/a-temporary-vat-cut-as-unconventional-fiscal-policy/ 
for a summary about the paper

Goal: To create a data frame that has one record per household and most importantly aggregates all point-of-sale FMCG expenditures of German households 
in the 2nd half of 2020. Our original file is a CSV file that contains millions of point-of-sale transactions of FMCG goods by German households from the
German market research firm, GfK.

#1 Initial dataset preparation.ipynb

This file imports the raw CSV data with the point-of-sale transactions of FMCG goods (Kaufinformationen_FMCG_2020.csv)
We first merged this information with demographic information about the household (Haushaltsinformationen_FMCG_2020) and saved it as a Pandas data frame. 
In this file, we performed some basic housekeeping where we used the Pandas date time module to transform the original date and extracted the month, week 
and day within our data frame to a useful form for our analysis later on and also for use in another research paper by one of the co-authors of the paper above 
who used the point-of-sale data at a daily frequency. See Goldfayn-Frank et al. (2023) "Spending effects of fiscal transfers in a pandemic" 
https://cepr.org/system/files/publication-files/DP17058.pdf

#2 FMCG point of sale data creation.ipynb

This file takes the data frame created above and basically aggregates the FMCG expenditures for each household for the 2nd half of 2020
We use the groupby method to create a new data frame of the aggregated expenditures and merge it back to the original data frame. As 
the records for each household are basically the same apart from the specific expenditure made (this is not relevant ), we sort the data 
and keep the first observation per household which has the aggregated expenditure and other demographic characteristics of the household

#3 data_cleaning_and_regression_analysis.ipynb

The information from the point of sale data is then merged with a special survey commissioned by the GfK for a subset of the households which contains
more demographic information and other special questions. This was where some feature engineering was conducted and the column of interest was the subjective 
qualitative perception of how prices evolved in the 2nd half of 2020 under the context of the 3% VAT cut in Germany in that period. The 6 qualitative categories 
were classified into a binary summary column, VAT_PT_b1, and VAT_PT_mint, which took the midpoint of the interval of each category.

Other columns of interest were created and then at the end, regression analysis for the paper was conducted using the Statsmodels package for the basic
OLS regressions. The Tobit regressions which are not well documented and supported in Python required the use of in-built packages from R. The rpy2 and aer modules 
were imported so that these Tobit regressions could be run.
