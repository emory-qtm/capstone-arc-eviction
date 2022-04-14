# Emory QTM Capstone: Atlanta Regional Commission (ARC) - Eviction
![Logo](/images/QTM_Logo.png)

Our capstone project aims to identify the top five factors most highly associated with eviction on a census tract level for the five counties (Clayton, Cobb, Dekalb, Fulton, and Gwinnett) in the Atlanta region.

## Contents
- [Motivation](#motivation)
- [Partners of Project](#partners-of-project)
- [Intended Use of Project](#intended-use-of-project)
- [Setup](#setup)
- [Notebook](#notebook)
- [Acknowledgements](#acknowledgements)


# Motivation
There are 3.85 million people living within the 5-county region. These people come from a wide variety of different social and/or economic backgrounds, living in rural areas to high-rises. Stable housing is one of the most important tenets of social and economic stabilitiy for an individual or household. Evictions negatively disreupt stable housing in an immediate sense and potentially in the long run. However, evictions do not occur in a uniform manner within the Atlanta Metropolitan area, with certain census tracts having very frequent eviction filing rates whilst others have significantly less frequent rates. Due to the detrimental effects of eviction filings and evictions, our team worked to understand why certain census tracts have such high rates of eviction filings by identifying which socio-economic factors are most associated with these census tracts. Our hope is that our work can be used by the Atlanta Regional Commission so they can better assist local governments mitigate the potential harms of evictions.

# Partners of Project
We collaborated with [Atlanta Regional Commission](https://atlantaregional.org/) for this project. Atlanta Regional Commission is the regional planning and intergovernmental coordination agency for the Atlanta region that works with partners that works across the community to plan for a brighter tomorrow. 

For this project, Atlanta Regional Commission has provided us guidelines, daily census tract-level eviction filing count data for the ARC’s 5-county region from 1/1/2019 to 2/3/2022, and feedback to our analysis to convey a more accurate representation of the eviction filings in Atlanta. 

# Intended Use of Project

A typical user of this Github repository should have interest in the following:
- learn the distribution of eviction filings on a census-tract level in five Atlanta metropolitan counties
- understand how different factors (e.g. poverty, education) associate with eviction filings
- explore the impact of government intervention (e.g. CARES Act) on eviction filings

This repository is designed to help R users to analyze and visualize the relationship between factors (e.g. unemployment rate, minorty rate) and eviction filings in five metropolitan counties in Atlanta.

## Use of Data Source

#### 1. [United States Census Bureau Data:](https://www.census.gov/)
[United States Census Bureau](https://www.census.gov/) is the primary source we get yearly data for our independent variables, namely poverty rate, education rate, unemployment rate, minority rate, renter percentage, rent burden, and uninsured rate. Users can download datasets directly from the website in various formats and match the independent variables with eviction filings based on census tract ID to understand and explore which factors contribute the most to eviction filings.

#### 2. [Neighborhood Nexus Data:](https://data.neighborhoodnexus.org/)
[Neighbourhood Nexus](https://data.neighborhoodnexus.org/) provides us the yearly data of poverty rate, minority rate, and rent burden for the year of 2019 for each census-tract region we. Users can download datasets in various formats directly from the website and match data with the eviction filing data based on census tract ID to understand the association between poverty rate, minority rate, rent burden and eviction filings.

#### 3. [Atlanta Regional Commission Data:](https://atlantaregional.org/)
Our stakeholder, [Atlanta Regional Commission](https://atlantaregional.org/), provides us the number of total households and daily eviction filings data for each census-tract region in the five counties we are interested in from January 2019 to January 2022. Users can use this data to explore the distribution of eviction filings during this time frame.

# Setup

This section instructs the user how to download necessary datasets from various data sources and teaches user how to execute both the data cleaning and analysis notebooks to obtain the data analysis and visualization.

## Software Installation

To begin, install the latest version of *RStudio* from [RStudio IDE](https://www.rstudio.com/products/rstudio/download/)

## Download Datasets


# Notebook

## Overview

## Major Functions

## Plots

## Impact and Conclusion

# Acknowledgements
- [Atlanta Regional Commission](https://atlantaregional.org/)
- [United States Census Bureau](https://www.census.gov/)
- [Neighborhood Nexus](https://data.neighborhoodnexus.org/)
- [Emory QTM Department](https://quantitative.emory.edu/)
