---
title:  "RENTAL VARIATIONS IN THE BAY AREA"
mathjax: true
layout: post
categories: media
---

![Oakland housing](https://www.essexapartmenthomes.com/-/media/Project/EssexPropertyTrust/Sites/EssexApartmentHomes/Blog/2020/2020-03-13-Oakland-Cultural-Hub-of-the-East-Bay/Oakland-Cultural-Hub-of-the-East-Bay-2-Downtown-Oakland.jpg)


## Introduction

The housing landscape of Bay Area has been profoundly impacted by the COVID-19 pandemic, leading to a reevaluation of rental dynamics and migration patterns. With remote work becoming the new norm for many industries, residents have begun to prioritize factors such as affordability, space, and quality of life over proximity to urban centers. Additionally, the area has experienced notable out-migration trends in the wake of the pandemic. The allure of the region, once synonymous with lucrative tech jobs and cultural vibrancy, has been tempered by concerns over affordability and quality of life. Residents, particularly those in the tech sector, have increasingly sought alternatives outside of the Bay Area, driven by factors such as remote work opportunities, housing affordability, and lifestyle preferences.

In this context, I aim to understand the relation between rental change and housing affordability in the region.


## Data and Methodology

The primary dataset utilized in this project is the Zillow Observed Rent Index (ZORI), which provides a smoothed representation of typical market rate rents across various regions. ZORI is a repeat-rent index that accounts for the entire rental housing stock, ensuring comprehensive market representation beyond just currently listed properties. It is dollar-denominated and calculated by averaging listed rents falling within the 40th to 60th percentile range for all homes and apartments in a region, weighted to reflect the rental housing stock.

The analysis focuses specifically on multi-family homes within the ZORI data, as the aim is to examine the correlation between renting trends and income. Future iterations of this analysis might explore homeownership versus renting trends in single-family homes concerning income and affordability, but such exploration is beyond the current project scope.

Additionally, the project utilizes data from the Census API, particularly the detailed estimate tables B19013, which provide income levels at both the county and zip code levels. Geographic boundaries for counties and zip codes in the Bay Area are sourced from the UC Berkeley database of shapefiles and geojson files.

The initial analysis begins by examining the Zillow data at the county level, aiming to grasp a comprehensive overview of rental variations across the Bay Area. This exploration spans recent years to discern prevalent trends. Subsequently, the focus shifts to understanding the relationship between these trends, income patterns, and affordability, still at the county level. Notably, anomalies observed within San Francisco and Alameda counties prompt a more detailed investigation at the zip code level. This granular analysis seeks to uncover potential correlations between income fluctuations and rent dynamics within these specific areas.



## Key Findings

### Temporal trends

Between 2015 and 2024, rents in the Bay Area experienced significant variation across different counties. Most notably, there was a consistent upward trend in rents across the majority of counties in the bay. Marin County stands out for its notably steady rent hikes during this period. However, San Francisco presents an anomaly, as rents appear to be declining rather than increasing.

![Chloropleth 2024](/assets/chloropleth_2024.png)


![Chloropleth subplot](/assets/chloropleth_subplots.png)


The onset of the pandemic brought about a sharp decline in rents specifically within San Francisco. Since then, rents in San Francisco have remained relatively low compared to other counties in the region, which have shown an upward trend. This divergence suggests a shift in rental market dynamics, with San Francisco experiencing a prolonged period of subdued rental prices while neighboring counties see a resurgence in rental demand and prices.

![3_pct_change](/assets/3_pct change.png)


![1_SF_Bay avg](/assets/1_SF_Bay avg.png)


### Housing affordability

![2_County pct_rent](/assets/2_County pct rent.png)


Examining housing affordability in the region involves analyzing rent burden, where households allocate more than 30% of their income to rent, across different counties and years. While most counties witness a decrease in rent burden over time, San Francisco notably exhibits a more pronounced decline in this trend. This prompts the question: could this be attributed to rising income levels in various parts of the city?

To investigate further, a closer look at the data at the zip code level reveals that this trend primarily manifests within the San Francisco-Oakland Metropolitan Area, spanning across San Francisco and Alameda counties. The aim is to see whether lower-income zip codes are seeing any trends of decreasing rents after the pandemic, and if it translates to housing quality. This is the reason why instead looking at the absolute rent values, the interest of the project is more about the changing trends after the pandemic.

{% include embed.html url="https://a-bellapu.github.io/map.html" %}

By comparing data at both the zip code and county levels, we can gain a more nuanced understanding of the factors contributing to San Francisco’s unique trajectory in rent burden reduction. This analysis will shed light on the complex interplay between economic factors, demographic shifts, and urban development policies shaping housing affordability in the Bay Area.

Conducting a correlation test reveals the relationship between median household incomes at the zip code level and the percentage change in rent prices since the pandemic. Interestingly, in San Francisco County, there is no significant correlation between income levels and rent price changes. Both high-income neighborhoods.

In contrast, Alameda County demonstrates a significant correlation between income levels and rent variations. Higher-income neighborhoods have witnessed rent increases post-pandemic. However, it's crucial to consider that several zip codes within the Average Area Median Income (AMI) limit of $147,900 have experienced rising rent prices. This raises questions about whether these neighborhoods are prepared to withstand the repercussions of escalating prices.

![correlation_both](/assets/correlation_both.png)

Alameda County | Correlation coefficient: 0.33 | P-value: 0.026
San Francisco County | Correlation coefficient: 0.25 | P-value: 0.23


## Conclusion
In conclusion, this analysis has shed light on the intricate dynamics shaping the Bay Area's housing landscape in the aftermath of the COVID-19 pandemic. While we've uncovered significant insights regarding rental trends, housing affordability, and their correlation with income levels, several questions remain ripe for further exploration.

One avenue for future research is to delve deeper into the drivers behind San Francisco's unique trajectory of declining rents and reduced rent burden, despite no significant correlation with income levels. Understanding the underlying factors influencing these trends could provide valuable insights into the city's evolving housing market dynamics.

Additionally, exploring the impact of remote work on migration patterns and housing preferences warrants further investigation. As remote work becomes increasingly prevalent, how will this influence housing demand and urban development in the Bay Area? Understanding these implications could inform future policy decisions and urban planning strategies.

Reflections on the methodology highlight the effectiveness of utilizing multiple datasets, such as the Zillow Observed Rent Index and Census API, to provide a comprehensive understanding of housing dynamics. By leveraging both county and zip code-level data, this analysis was able to capture nuanced trends and correlations at different spatial scales.

However, it's important to acknowledge the limitations of the data sources utilized. While the Zillow data provides valuable insights into rental trends, it may not capture the full spectrum of housing dynamics, such as informal rental markets or rent control policies. Additionally, while the Census API offers income data at various geographic levels, its estimates may be subject to sampling error and demographic shifts over time.

Despite these limitations, the compatibility of sources allowed for robust analysis and interpretation of trends. By triangulating data from multiple sources, this analysis was able to provide a comprehensive perspective on housing affordability in the Bay Area.

In moving forward, addressing these unanswered questions and refining methodological approaches will be essential for gaining a deeper understanding of the complex interplay between economic, demographic, and policy factors shaping housing dynamics in the region.


## Sources
[https://www.sfchronicle.com/bayarea/article/rent-prices-increase-pandemic-17884597.php](https://www.sfchronicle.com/bayarea/article/rent-prices-increase-pandemic-17884597.php)

[https://ternercenter.berkeley.edu/wp-content/uploads/pdfs/Disparity_in_Departure.pdf](https://ternercenter.berkeley.edu/wp-content/uploads/pdfs/Disparity_in_Departure.pdf)

[https://www.sfchronicle.com/sf/article/s-f-exodus-population-recovery-data-18564064.php](https://www.sfchronicle.com/sf/article/s-f-exodus-population-recovery-data-18564064.php)

