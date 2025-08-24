# Real-Estate-Prices-Bankruptcies-in-Germany-2000-2024-
This project's goal was to practice data collection, cleaning, and visualization using multiple formats and Python libraries.

# Exploratory Data Analysis: Correlation between Real Estate Prices and Bankruptcies in Germany

### Hypothesis

I expected to find a negative correlation between real estate prices and bankruptcies: when bankruptcy numbers rise in the wake of a crisis, less capital is available to purchase homes, so demand declines and prices stagnate or fall. Conversely, when bankruptcy numbers are low (indicating economic stability), real estate prices tend to rise.

### Data Sources

The main source was destatis.de, Germany’s official statistical database.
- Bankruptcies: one consistent dataset spanning 1990–2024.
- Real estate prices: multiple datasets, each with different base years. This is a limitation, as indices were repeatedly reset to a new reference year.

Data formats used: CSV, PDF, Excel.

### Data Preparation

The most challenging dataset was the real estate index from 2000–2006, which was only available as a PDF in quarterly format.
- Extracted with Camelot.
- Cleaned with regex to remove text and NaNs.
- Filtered for yearly averages (removing quarterly duplicates such as multiple “4. VJ” entries).

The later datasets (2008–2024) were more straightforward and provided annual or quarterly values. Bankruptcy data was filtered to the relevant periods: 2000–2005, 2008–2013, 2020–2024.

Data manipulation and cleaning were done with Pandas; visualizations were created with Matplotlib.

### Method

Three plots were created to visualize developments during major crises:
- DotCom bubble (2000–2005)
- Financial crisis (2008–2013)
- COVID-19 pandemic (2020–2024)

For each, I merged the housing price index with bankruptcy numbers on the yearly level.
- X-axis: time (years)
- Y-axis (left): housing price index
- Y-axis (right): bankruptcies

This setup highlights possible correlations over time.

### Results

- DotCom bubble & Financial crisis: clear negative correlation — as bankruptcies rose, real estate prices stagnated or fell.
- COVID-19 pandemic: an outlier. A positive correlation appeared, with both prices and bankruptcies rising after 2020. This can be explained by the Corona-Soforthilfe (government grants), which temporarily reduced bankruptcies in 2020 but was followed by a sharp correction in 2021. Unlike earlier crises, real estate prices continued to increase despite economic disruptions.

### Limitations
- This project was a practice in data analysis with Python, not a polished academic study.
- Housing price indices across different datasets used different base years, preventing seamless long-term comparisons.
- Broader macroeconomic factors (interest rates, fiscal policy, labor market conditions) were ignored.
- The DotCom and Financial crises primarily hit financial markets, while COVID-19 was unique in that stock markets surged despite global supply chain disruptions.

### Next Steps

A natural extension would be to:
- Re-index all housing price datasets to a common base year.
- Incorporate additional variables such as interest rates and stock market indices.
- Investigate whether the divergence during COVID-19 represents a structural change in real estate dynamics.
