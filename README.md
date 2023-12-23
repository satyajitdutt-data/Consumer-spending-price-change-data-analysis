![GfK](https://github.com/satyajitdutt-data/Consumer-spending-price-change-data-analysis/assets/144555009/df358bd1-c148-45e8-ba29-132202a63da7)

This set of Python notebooks shows the entire end-to-end data pipeline that was used for the analysis of the research paper
Bachmann et al. (2023) "A Temporary VAT Cut as Unconventional Fiscal Policy" which looked at the expenditure of fast moving goods by German households in response to a 3% cut in the VAT in 2020 H2.
In the aggregate, consumption spending in Germany rose by 34 billion Euros.

See https://bfi.uchicago.edu/insight/finding/a-temporary-vat-cut-as-unconventional-fiscal-policy/ 

The goal was to create a data frame that has one record per household and most importantly aggregates all point-of-sale FMCG expenditures of German households in 20290 H2. The original file is a CSV file that contains millions of point-of-sale transactions of FMCG goods by German households from theGerman market research firm, GfK. 

