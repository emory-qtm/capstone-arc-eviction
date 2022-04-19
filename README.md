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
There are 3.85 million people living within the 5-county region. These people come from a wide variety of different social and/or economic backgrounds, living in rural areas to high-rises. Stable housing is one of the most important tenets of social and economic stabilitiy for an individual or household. Evictions negatively disreupt stable housing in an immediate sense and potentially in the long run. The effect of evictions extends to the communities to be destabilizing and destructive. Especially due to the COVID-19 pandemic, housing security is at risk in the American society. Approximately 1 in 5 workers have had their hours cut off or have been laid off. The vulnerable are the most impacted population, with the risk of being displaced due to loss of income. Evictions do not occur in a uniform manner within the Atlanta Metropolitan area, with certain census tracts having very frequent eviction filing rates whilst others have significantly less frequent rates. 

Due to the detrimental effects of eviction filings and evictions, our team worked to understand why certain census tracts have such high rates of eviction filings by identifying which socio-economic factors are most associated with these census tracts. As a team who are passionate in applying data science for social good, we aim to create two Notebooks. We hope that this project would aid the Atlanta Regional Commission in convening to the local stakeholders that could be shared at the Regional Housing Forum or Community Resource Committee. Moreover, we hope that our work can be used by the Atlanta Regional Commission so they can better assist local governments mitigate the potential harms of evictions. With this project, the quality of life for the residents of Georgia would be improved, and it will provide actionable and stronger solutions.

# Partners of Project
We collaborated with [Atlanta Regional Commission](https://atlantaregional.org/) for this project. Atlanta Regional Commission is the regional planning and intergovernmental coordination agency for the Atlanta region that works with partners that works across the community to plan for a brighter tomorrow. 

For this project, Atlanta Regional Commission has provided us guidelines, daily census tract-level eviction filing count data for the ARC’s 5-county region from 1/1/2019 to 2/3/2022, and feedback to our analysis to convey a more accurate representation of the eviction filings in Atlanta. 

# Intended Use of Project

A typical user of this Github repository should have interest in the following:
- learn the distribution of eviction filings on a census-tract level in five Atlanta metropolitan counties
- understand how different factors (e.g. poverty, education) associate with eviction filings
- explore the impact of government intervention (e.g. CARES Act) on eviction filings

This repository is designed to help R users to analyze and visualize the relationship between factors (e.g. unemployment rate, minorty rate) and eviction filings in five metropolitan counties in Atlanta.

## Use of Data Sources

#### 1. [United States Census Bureau Data:](https://www.census.gov/)
[United States Census Bureau](https://www.census.gov/) is the primary source we get yearly data for our independent variables, namely <i>poverty rate, education rate, unemployment rate, minority rate, renter occupied units, rent burden, and uninsured rate</i>. The original source is from the 5-year American Community Survey (ACS). Users can download datasets directly from the website in various formats and match the independent variables with eviction filings based on census tract ID to understand and explore which factors contribute the most to eviction filings.

#### 2. [Neighborhood Nexus Data:](https://data.neighborhoodnexus.org/)
[Neighbourhood Nexus](https://data.neighborhoodnexus.org/) provides us the yearly data of <i>poverty rate, minority rate, and rent burden</i> for the year of 2019 for each census-tract region we investigate on. The original source is from the 5-year American Community Survey (ACS). Users can download datasets in various formats directly from the website and match data with the eviction filing data based on census tract ID to understand the association between poverty rate, minority rate, rent burden and eviction filings.

#### 3. [Atlanta Regional Commission Data:](https://atlantaregional.org/)
Our stakeholder, [Atlanta Regional Commission](https://atlantaregional.org/), provides us the number of total households and daily eviction filings data for each census-tract region in the five counties we are interested in from January 2019 to January 2022. Users can use this data to explore the distribution of eviction filings during this time frame.

# Setup

This section instructs the user how to download necessary datasets from various data sources and teaches user how to execute both the data cleaning and analysis notebooks to obtain the data analysis and visualization.

## Installation

To begin, first install R and then install RStudio on your computer. Ensure that you installed the lastest version of <i>tidyverse, dplyr, and ggplot2</i>, on your computer. This project requires R 3.30+ and RStudio >= 2022.02.1+461. 

### R
1. Go to [The Comprehensive R Archive Network](https://cran.rstudio.com/)
![img2](/images/r-1.png)
2. Choose the version of R that fits your operating system.
![img3](/images/r-2.png)
3. Download the latest version of R and then install it on the computer based on the instruction

### RStudio

1. To begin, go to [Download the RStudio IDE](https://www.rstudio.com/products/rstudio/download/)
![img1](/images/rstudio-1.png)
2. Choose Download RStudio Desktop Free version
![img4](/images/rstudio-2.png)
3. Download the version of RStudio that fits your computer's operating system

If you have successfully installed R and RStudio, you should see the following when you open RStudio
![img5](/images/rstudio-3.png)


## Download Datasets
Beforing downloading the datasets, first git clone this repository to your local computer. To git clone this repository, go to Terminal and type the following command
>     - git clone https://github.com/emory-qtm/capstone-arc-eviction.git
Now you should have the entire repository cloned into your local computer. Go to the cloned repository and make sure you have a folder called **datasets**
![img6](/images/folder.png)
Now download each dataset from the website provided in the following table. Unzip the downloaded file and then rename each dataset from its raw name (under the column "Raw Name") to its corresponding name under the column "Dataset Name"
| Dataset Name  | Raw Name      | URL           |
| ------------- | ------------- | ------------- |
| education_2019.csv  | ACSST5Y2019.S1501_data_with_overlays_2022-04-16T182809  |   https://data.census.gov/cedsci/table?q=education&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000&y=2019|          
| education_2020.csv  | ACSST5Y2020.S1501_data_with_overlays_2022-04-16T183029  | https://data.census.gov/cedsci/table?q=education&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000 |
| evictions.csv  | evictions.csv  | https://docs.google.com/forms/d/e/1FAIpQLSexUZb9dXIx5h1GjaKmuNekxvp-CkgQ_qGsoAJXDERuLslSCg/viewform |
| household_count.csv  | household_count.csv  |      https://docs.google.com/forms/d/e/1FAIpQLSexUZb9dXIx5h1GjaKmuNekxvp-CkgQ_qGsoAJXDERuLslSCg/viewform |      
| poverty_18_19.csv  | DN-EXPORT-GATRACTS-04-16-22.csv  | https://data.neighborhoodnexus.org/ |
| poverty_2020.csv  | ACSST5Y2020.S1701_data_with_overlays_2022-04-16T183708  | https://data.census.gov/cedsci/table?q=poverty&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000&y=2020 |
| race_18_19.csv  | DN-EXPORT-GATRACTS-04-16-22.csv  | https://data.neighborhoodnexus.org/ |
| race_2020.csv  | DECENNIALPL2020.P1_data_with_overlays_2022-01-16T213307  | https://data.census.gov/cedsci/table?q=decennial%20census&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000&y=2020&tid=DECENNIALPL2020.P1 |         
| rent_burden_2019.csv  | DN-EXPORT-GATRACTS-04-16-22.csv  | https://data.neighborhoodnexus.org/ |
| rent_burden_2020.csv  | ACSDP5Y2020.DP04_data_with_overlays_2022-04-16T184023  | https://data.census.gov/cedsci/table?q=DP04&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000 |
| renter_occupied_2019.csv  | ACSDP5Y2019.DP04_data_with_overlays_2022-04-16T175404| https://data.census.gov/cedsci/table?q=b25003&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000 |
| renter_occupied_2020.csv  | ACSDP5Y2020.DP04_data_with_overlays_2022-04-16T175404| https://data.census.gov/cedsci/table?q=b25003&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000 |
| unemp_2019.csv  | ACSST5Y2019.S2301_data_with_overlays_2022-04-16T184832  | https://data.census.gov/cedsci/table?q=unemployment&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000&y=2019&tid=ACSST5Y2019.S2301 |
| unemp_2020.csv  | ACSST5Y2020.S2301_data_with_overlays_2022-04-16T184941  | https://data.census.gov/cedsci/table?q=unemployment&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000&y=2020&tid=ACSST5Y2020.S2301 |
| uninsured_2019.csv  | ACSST5Y2019.S2701_data_with_overlays_2022-04-16T214752  | https://data.census.gov/cedsci/table?q=s2701&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000&y=2019 |
| uninsured_2020.csv  | ACSST5Y2020.S2701_data_with_overlays_2022-04-16T214904  | https://data.census.gov/cedsci/table?q=s2701&g=0500000US13063%241400000,13067%241400000,13089%241400000,13121%241400000,13135%241400000&y=2020 |

Then, move all datasets (CSV format) inside the folder **datasets**. If you have done this step correctly, you should have the following when you go to **datasets** folder
![img7](/images/datasets.png)

## Run Notebook
To run the notebooks, first run *data_cleaning.Rmd*
![img8](/images/cleaning-1.png)
You should get two new datasets in the **datasets** folder
![img9](/images/cleaning-2.png)
Next run *data_analysis.Rmd* to get all the analysis (e.g. plots, regression models)
![img10](/images/analysis-1.png)




# Notebook

## Overview

In our capstone project, we have two notebooks. *data_cleaning.Rmd* notebook is used for extracting useful explanatory and dependent variables from raw datasets and combine them into cleaned datasets. *data_analysis.Rmd* notebook is used to analyze how different factors interact with eviction filings and finds the top five factors most highly associated with eviction on a census-tract level in Atlanta region. Based on our analysis, we also recommend policies that may help lower eviction rate in certain census tract regions. There are several major functions of our analysis notebook. In the first section, it shows the distribution of explanatory variables and dependent variables as histograms. In the second section, it runs a multiple linear regression model in the combined dataset (2019 & 2020) to analyze which factors have the greatest impact on eviction rate. In the third section, it splits the data into two parts, the data of 2019 and the data of 2020. It compare the distribution of explanatory and dependent variables as histograms in two years. Next, it runs a multiple linear regression in each year to track the changes (both in magnitude and direction) of coefficients of each explanatory variable. In the fourth section, we run correlation matrix, variance inflation factor (VIF), and Lasso to examine the issue of multicollinearity in our regression model. In the final section, we also run a neural network analysis to examine any non-linear behavior existed in the datasets.

## Plots

The two plots below are examples of plots you get by running our analysis notebook.

This plot below shows the distribution of eviction rate in the combined dataset (2019 & 2020). The histogram suggests that the distribution of eviction rate is heavily right-skewed, as it has a rather long tail. This plot informs our team to take the log transformation of eviction rate before running regression analysis to ensure we have a normalized dataset.
![img11](/images/plot-1.png)

This plot below shows the distribution of rent burden rate in the combined dataset (2019 & 2020). Rent burden rate is defined as the percentage of population who spent more than 30% of their income on housing rental fees. This plot indicates the distribution of rent burden rate is roughly normally distributed, as most census-tract regions have rent burden rate somewhere between 0.3 and 0.8.
![img12](/images/plot-2.png)

## Intended Use of Outputs
By running the analysis on the dataset, our team concludes that the top five factors highly associated with evictions on a census tract level in the Atlanta region are poverty rate, race, education, pecentage of renter occupied housing, and rent burden. We conclude the first four factors based on our regression models, and we conclude rent burden based on visually inspecting the dataset and also connecting to external factors, such as policies.

Based on our conclusion, we have also suggested some policy recommendations that might help lower eviction rate. We recommend that the state and/or federal government improve social welfare provision by creating automatic stabilizers. An automatic stabilizer means that when there is an economic downturn or other crisis, that unemployment benefits, SNAP, and other welfare provision that the amount of welfare provision will automatically increase. For example, this would mean that when a recession occurs, unemployment benefits would automatically become more generous. From 2019 to 2020, the association between unemployment rate and poverty rate with eviction filing rate decreased, likely due to the significantly increased welfare provision during 2020.  Another policy is to strengthen emergency rental assistance programs. Emergency rental assistance (ERA) are funds used to help pay people's rent when they lack the funds, with the intentions of pre-empting an eviction filing. ERA funding was expanded during 2020, however those funds were often poorly distributed since many local governments lacked the underlying program infrastructure to quickly distribute the funds to landlords/tenants. ERA funding should be increased, but also the funding for the infrastructure to manage the programs should also be permanently increased. Furthermore, ERA funding should be promoted more heavily in areas with higher rent burden and/or areas with a higher racial minority population. Lastly, we advise the creation of more pre-eviction filing clinics. These legal clinics which can operate in or outside the judicial system are intended to be a central location to direct socially vulnerable renters to legal help for potential legal services such as counsel or mediation as well as economic assistance. Offering a central location outside of the government can make finding these necessary services easier for disadvantaged populations.

# Acknowledgements
These notebooks were created by Fenton Sun, Ryan Lee, Kevin Ding, Hyesun Jun, and Matthew Thompson. This project wouldn't have been possible without the support from Dr. Blake Fleischer, Dr. Ben Miller, [Atlanta Regional Commission](https://atlantaregional.org/), and [Emory University QTM Department](https://quantitative.emory.edu/). These notebooks were built using the R statistical program.
