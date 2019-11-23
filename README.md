# DATA 512 Final Project
This repository contains the materials used in my final project for Human-Centered Data Science, Fall 2019. All of my code is released under MIT license.

# Abstract
I analyzed City of Calgary Census data to better understand high-density housing patterns, demographics, and changes in the city over time. I found that new outlying communities are leading the way in high-density housing construction despite being far from the city code. I also found that that Calgary's population and building construction patterns are closely tied to the natural reasource economy. Few discoveries were made with age demographics, but more demographic data will be added in the next census which will pave the way for exciting new discoveries.

# Running the analysis
All required data files are in this repository to ensure reproducibility. The repository can be downloaded from GitHub or by running `git clone https://github.com/rileywaters/data-512-project`

The analysis can be found in the "DATA-512-Final-Project.ipynb" file. It contains step-by-step instructions and a detailed write-up on the background, methods, findings, and implications. For any questions about the analysis, contact me at rdwaters@uw.edu

The following tools are required:
- [IPython Jupyter notebook](https://jupyter.org). A tool for executing Python Code. We use Python 3.7. [License here](https://jupyter.org/about)
- [pandas](https://pandas.pydata.org). A data analysis library. We use v0.25.3. [License here](https://pandas.pydata.org/pandas-docs/stable/getting_started/overview.html)
- [folium](https://python-visualization.github.io/folium/). An interactive mapping library. We use v0.10.0. [License here](https://github.com/python-visualization/folium/blob/master/LICENSE.txt)
- [numpy](https://numpy.org). A scientific computing package. We use v1.18. [License here](https://numpy.org/license.html)
- [matplotlib](https://matplotlib.org). A 2d plotting library. We use v3.1.1. [License here](https://matplotlib.org/3.1.1/users/license.html)

# Data
Three data files are needed for this analysis. They are included in the project /data/ directory but may also be downloaded and placed there. Be aware that the City of Calgary Data Portal updates the datasets in-place so any updated datasets may break the notebook.

## Dataset 1 - Census by Community 2019
The Calgary Open Data portal released a [Census by Community 2019](https://data.calgary.ca/Demographics/Census-by-Community-2019/rkfr-buzb) dataset. The version in this project was last updated on September 20, 2019. This set is an “official count of dwelling units and population within those units”. 
The dataset is licensed under the [Open Government License – City of Calgary](https://data.calgary.ca/stories/s/u45n-7awa) which allows for freedom to “copy, modify, publish, translate, adapt, distribute, or otherwise use the Information in any medium , mode, or format for any lawful purpose” granted that acknowledgement of the source is made. 
It has 306 rows, each representing a community district within the city. It has 142 columns. Below are some descriptions of columns that will be of interest.

| Column | Description  |  
|---|---|
| Class  | Zoning type eg. Industrial, residential, ect  |  
| SRG  | Yearly development capacity or housing supply  |  
| COMM_STRUCTURE  | Identification code of life-cycle patterns  |  
| RES_CNT  | Number of residents  |  
| DWELL_CNT  | Number of dwellings  |  
| {type}_CNT  | Dozens of columns counting person types  |  
| {type}_SCH | Which school system the dwellings support |
| {type}_OCCPD | The number of occupied units of each type of building |
| {type}_VACANT | The number of vacant units of each type of building |
| {type}_UC | The number of buildings of each type under construction |
| {type}_person | The number of persons occupying the units  of each type|
| {sex}_{age range} | Number of male, female, or other residents in each age range |


## Dataset 2 - Civic Census Results 1958-2019
To compare to previous years, we will use the [Civic Census Results 1958-2019](https://data.calgary.ca/Demographics/Civic-Census-Results-1958-2019/rmai-qvzh) dataset. The version in this project was last updated on September 20, 2019. This set is under the same license as the previous one and is also made available by the Calgary Open Data portal. It has 8 columns and 701 rows with information on “citywide and ward-level counts of dwelling units and residents over the past 60 years”. The columns of interest in this set are as follows:

| Column | Description  |  
|---|---|
| Year  | The year the data was collected  |
| Ward | The municipal ward | 
| Dwellings | Count of dwellings |
| Residents | Count of residents |
| Vehicles | Count of vehicles |
| Age 65+ | Count of residents 65 and older |
| Voters | Count of voters |  

## Dataset 3 - Community Boundaries Layer
The third and final data download is the [Community Boudaries Layer](https://data.calgary.ca/Base-Maps/Community-Boundaries/ab7m-fwn6). It is a GeoJSON file that we will use purely for mapping purposes. It is under the same license as the previous datasets as it is also hosted by Calgary Open Data Portal.

