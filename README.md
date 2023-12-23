![GfK](https://github.com/satyajitdutt-data/Consumer-spending-price-change-data-analysis/assets/144555009/df358bd1-c148-45e8-ba29-132202a63da7)

This repository consists of a dashboard that summarises the fast moving good expenditure habits of German households in the 2nd half of 2020 (2020 H2) as a result of the 3% VAT cut imposed by the German govt. This was computed using point of sale transactions of FMCG goods of over 8000 households by the German market research firm, GfK. The key insights are: 
- Median fast moving good expenditure increased by 3 euros per supermarket visit in 2020 H2 compared to 2019 H2 
- Households experienced an overall median drop of 2.4% in their fast moving good price basket
- 65% of these households surveyed in 2021 January perceived that prices fell in 2020 H2 

In addition, this repository consists of a set of Python notebooks shows the entire end-to-end data pipeline that was used for the analysis of the research paper Bachmann et al. (2023) "A Temporary VAT Cut as Unconventional Fiscal Policy". See https://bfi.uchicago.edu/insight/finding/a-temporary-vat-cut-as-unconventional-fiscal-policy/ 

The goal was to create a data frame that has one record per household and most importantly aggregates all point-of-sale FMCG expenditures of German households in 20290 H2. The original file is a CSV file that contains millions of point-of-sale transactions of FMCG goods by German households from theGerman market research firm, GfK. 

