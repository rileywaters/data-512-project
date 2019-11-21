# Project Proposal - Housing in Calgary

## Motivation

I was born and raised in Calgary Alberta, the [fastest growing urban area](http://worldpopulationreview.com/countries/canada-population/) in Canada since 2011 and the [first choice for “second mover” immigrants](https://moving2canada.com/living-in-calgary/) who relocate from their initial city. Calgary is not limited by natural land restrictions and is known for sprawling communities of single-family homes. However, there have been major efforts in recent years to densify the city with new rail lines and high-rise buildings. There have also been significant changes to demographics as new industries emerge and immigrant intake ramps up. I have observed many changes in recent trips home and would like to explore them from a human-centered data perspective. I hope to learn about districts in Calgary: where new constructions are happening, what types of buildings they are, the people occupying them, and how this has changed from years prior. Few statistical analyses have been on this data so it would provide valuable knowledge for people interested in the city, whether they live there or plan to move there. 
 
I will perform this analysis with Human-Centered Data Science in mind in a form that is reproducible and well-documented. I would also like to investigate potential privacy and ethical concerns in the way the data is formatted and released. Even after aggregation, releasing census data carries privacy risks. The goal of this investigation is to inform the city of potentially negative consequences in the way the data is released so that changes can be made. I will not attempt to reidentify individuals nor will I make public any privacy-risking findings.

## Data

The Calgary Open Data portal released a [Census by Community 2019](https://data.calgary.ca/Demographics/Census-by-Community-2019/rkfr-buzb) dataset, last updated on September 20, 2019. This set is an “official count of dwelling units and population within those units”. 
The dataset is licensed under the [Open Government License – City of Calgary](https://data.calgary.ca/stories/s/u45n-7awa) which allows for freedom to “copy, modify, publish, translate, adapt, distribute, or otherwise use the Information in any medium , mode, or format for any lawful purpose” granted that acknowledgement of the source is made. 
It has 306 rows, each representing a community district within the city. It has 142 columns. The many detailed columns on construction are of interest to me as they are indications of densifying neighborhoods. The demographic data will aid me in exploring who is moving into these new structures. Below are some descriptions of columns that will be of interest to me.

| Column | Description  |  
|---|---|
| Class  | Zoning type eg. Industrial, residential, ect  |  
| SRG  | Yearly development capacity or housing supply  |  
| COMM_STRUCTURE  | Identification code of life-cycle patterns  |  
| RES_CNT  | Number of residents  |  
| DWELL_CNT  | Number of dwellings  |  
| {type}_CNT  | Dozens of columns counting person types  |  
| {type}_SCH | Which school system the dwellings support |
| {building type} | Counts of different building types |
| {type}_OCCPD | The occupation and vacancy of each type of building |
| {type}_UC | The number of buildings of each type under construction |
| {type}_person | The number of persons occupying the units  of each type|
| {sex}_{age range} | Number of male, female, or other residents in each age range |

From the descriptions alone I can see several potential ethical concerns which I outline in the research questions section. 

To compare to previous years, I plan to use the [Civic Census Results 1958-2019](https://data.calgary.ca/Demographics/Civic-Census-Results-1958-2019/rmai-qvzh) dataset. This set is under the same license as the previous one and is also made available by the Calgary Open Data portal. It has 8 columns and 701 rows with information on “citywide and ward-level counts of dwelling units and residents over the past 60 years”. The columns of interest to me in this set are as follows:

| Column | Description  |  
|---|---|
| Year  | The year the data was collected  |
| Ward | The municipal ward | 
| Dwellings | Count of dwellings |
| Residents | Count of residents |
| Vehicles | Count of vehicles |
| Age 65+ | Count of residents 65 and older |
| Voters | Count of voters |  

This dataset will bring greater context to Calgary’s population change and constructions in each district for over half a century. The city’s growth is heavily tied to the energy and natural resources industry so it will be interesting to analyze how major boom and bust cycles affected development. This dataset has fewer ethical considerations as it is not as detailed, but careful consideration will go into handling age and voting fields.

## Dependencies

The project does not depend on external parties, so I do not anticipate delays in its completion. However, in the event that I discover ethical issues in the data, I may refrain from posting such findings while I contact the City of Calgary to handle them.

## Research Questions

I am interested in general trends pertaining to the density of communities and the people living there. Below are some of my questions:

-	_How do construction trends differ by community?_
-	_What construction trends are occurring on the city-level?_
-	_What vacancy trends are there across communities?_
-	_How do demographics differ by community?_
-	_How has community density and population changed over time?_

I would like to explore and visualize this data geographically to answer these questions. From my own observations, I can hypothesize that certain communities are being rapidly built-up due to re-zoning, new transit lines/ring roads, or proximity to emerging industry districts. There may be resistance to zoning around affluent areas. I am also curious to see how single-family home construction is affected by the densification efforts of the city.

From the time-series data I have a hypothesis that construction in Calgary relates to boom and bust cycles in oil prices. Many Calgarians work in the natural resource industry so the growth of the city may be tied closely to it’s health.

As this is a human-centered data analysis, I also have questions I would like to answer about the dataset itself:

-	_Could individual or family units data be compromised despite the aggregated nature of the data?_
-	_Could the inclusion of certain demographic data be used in unethical ways?_

The data contains counts of all kinds of people: Voters, preschool children, employed/unemployed people, homeowners, and even information on pets. The data is aggregated to a community level, but my hypothesis is that there are enough fields, and some districts are small enough, to present privacy risk. I will investigate if the publishing of this dataset could present an ethical problem and if it could be combined with other datasets for malicious purposes. If so, I will take directive to inform the City of Calgary without making public how this could be done.

It is also unclear whether the male/female columns represent biological sex or self-described gender. I do not plan to conduct heavy gender-difference research on this dataset but I will likely visualize the differences in counts across the districts.

## Background and Related Work

“[New Urbanism](https://www.cnu.org/resources/what-new-urbanism)” is a city planning approach that focusses on human-scaled urban design. It promotes walkable districts with dense housing and prioritizes mass transit over private cars. Many North American such as [Portland Oregon](https://oregonhistoryproject.org/narratives/commerce-climate-and-community-a-history-of-portland-and-its-people/portland-neighborhoods/renewing-the-public-space-and-the-new-urbanism/) have been expanding with this approach for decades, but the concept has only recently taken hold in Calgary. 

One research study found that “While land use practices respond slightly to shifting paradigms in community planning theory in rapidly growing communities, in slower-growth regions, conventional development strategies reflect political and economic priorities” (Grant 2003). This may lend credence to my hypothesis that during ‘bust’ cycles, Calgary relies more on conventional, car-based city planning.

A study on urban sprawl in Toronto found that “most households living in higher-density building types plan to eventually move to detached houses” and so if new urbanism were to substitute conventional development, “its projects will have to have a much larger proportion of single-family detached houses than Cornell’s (another research study) 37 percent.” (Skaburskis 2006). This informs my understanding of densification going into this analysis. High-density development does not necessarily replace suburban development, but I may expect new apartment buildings to appeal to young professionals who eventually move to lower-density communities.

The open data initiative in Calgary is quite new so there has not been much related work using the same data as me. I did find one independent data analyst, Willem Klumpenhouwer, who has used related data sets to [create interactive visualizations]( https://www.klumpentown.com/tfc/calgary) on transit times in Calgary. The 2019 census data was only launched in September, so I will keep an eye out for other work that may be done by independent analysts or news sources.

-	Grant, Jill. "Exploring the influence of new urbanism in community planning practice." Journal of architectural and planning research (2003): 234-253.
-	Skaburskis, Andrejs. "New urbanism and sprawl: A Toronto case study." Journal of Planning Education and Research 25.3 (2006): 233-248.


## Methodology

Analysis and presentation will both be done in an [IPython Jupyter notebook](https://jupyter.org). This format allows for accessible documentation and a step-by-step reproducible process for others to obtain my results. I plan to user [Pandas](https://pandas.pydata.org) for data cleaning and [matplotlib](https://matplotlib.org) for some visualizations. These tools are commonly known in the data science community and have BSD licenses permitting free, unlimited redistribution. I will group and filter subsets of the data to find mean and median values. Plotting my findings onto charts will be essential to promote the accessibility of my findings. All of the data attributes I listed in the data section will be explored.

For geographic visualization I plan to use the [folium](https://python-visualization.github.io/folium/) package. This is a powerful and interactive visualizing tool released under an MIT license that I have used in the past. It can make intuitive and beautiful visualizations in-line in a Jupyter notebook, allowing users to explore beyond the findings I come up with. I plan to use several choropleth maps that use shading and coloring to indicate differences in numbers. 

For comparing numbers between communities and years, I will be using different tests for statistical significance. Chi-squared tests are used to compare frequencies of binary data points such as home ownership. T-tests are used to compare if the means of two groups are statistically different. This would be used is situations like comparing different years of data to see if population has increased more in one district than another. Statistical significance is important to consider before drawing any conclusions comparing multiple groups.
