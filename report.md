Data-Driven Insights for Community Safety in Los Angeles: Analyzing
Crime Patterns and Trends in Recent Years
================
Yunjia Liu(yl5830), Linshan Xie(lx2346), Jianming Wang(jw4693), Yuwei
Xia(yx2953), Tingyu Qian(tq2171)
2024-12-04

  

## Motivation

Los Angeles is a city of vibrant diversity and a lively urban
landscape—but it’s also a city where the dynamics of crime can vary
widely across neighborhoods, demographic groups, and even times of day.
For law enforcement, policymakers, and community members alike,
understanding these complex crime patterns is key to fostering safer and
more resilient communities.  
Our project dives into the Los Angeles Police Department crime dataset
to uncover the “who, what, where, and when” of crime across LA’s diverse
neighborhoods. We’re on a mission to decode the patterns of crime by
exploring how different demographics, time frames, and locations shape
the city’s unique crime profile. Whether it’s catching late-night
trends, uncovering hotspots, or spotlighting demographic factors, we’re
here to map the hidden story of LA’s crime scene and uncover what drives
certain areas’ steady patterns—or sudden disruptions!  

  

## Related work

For HW5, we worked with data on homicides in 50 large U.S. cities. Our
group found this dataset incredibly meaningful and decided to explore it
further. To expand our research, we selected the “Crime Patterns and
Trends in Recent Years - LA” dataset. This dataset includes latitude and
longitude information, which inspired us to create a map-based
visualization.  

  
Building on the Shiny introduced in class, we realized that Shiny would
be an excellent tool for analyzing and visualizing this dataset. By
implementing interactive filters, we can create dynamic visualizations
tailored to specific insights we want to uncover. Overall, this
assignment and the course material have been instrumental in motivating
us to select this dataset and approach, providing both the direction and
tools for our project.  

  

By utilizing advanced visualization and analysis tools, we aim to
contribute to a deeper understanding of these issues, potentially
helping policymakers and communities address crime more
comprehensively.  

  

## Initial questions

We’re on a mission to decode the patterns of crime by exploring how
different demographics, time frames, and locations shape the city’s
unique crime profile. We are interested in:  
**1.**What does the general demographic profile of victims look like?
What’s the distribution of their races, genders and ages?  
**2.**What is the distribution of crime across time dimensions? What if
analyzing in terms of hours, weekdays, seasons and years?  
**3.**How crime is associated with location information? What does the
geographic maps and spatial distribution look like?  
  

## Data

The source dataset is the Los Angeles Police Department (LAPD) crime
dataset, which contains all cases received by the LAPD from January 1,
2020 to September 30, 2024, and contains 982638 observations and 28
variables. After deleting variables such as weapon_cd, weapon_desc,
etc., which contain a large number of missing values, the variables that
are not needed are further deleted according to the needs of this
project.The final data used for analysis contains the following
variables:  
  
- `dr_no`: Unique identifier for each reported crime.  
- `date_occ`: Date the crime occurred.  
- `time_occ`: Time the crime occurred.  
- `serious_level`: Indicates whether the crime is a “1” (serious) or “2”
(less serious) offense. - `crime_type`: Description of the type of crime
\[eg.VEHICLE - STOLEN, VANDALISM - MISDEAMEANOR (\$399 OR UNDER)\]  
- `vict_age`: Age of the victim.  
- `vict_sex`: Sex of the victim.  
- `vict_descent`: Racial or ethnic background of the victim.  
- `rpt_dist_no`: Reporting district number.  
- `premis_cd`: Premises code (e.g., residential, commercial).  
- `premis_desc`: Concatenation of the sighting session day and month. -
`status`: Description of the case status. (eg. Invest Cont, Juv
Other).  
- `lat`: Latitude coordinates of the crime location.  
- `long`: Longitude coordinates of the crime location.  
  

## Exploratory analysis

The Exploratory analysis of our project is divided into three main
sections: Victim Demographic, Time Trend, and Location.  
  
In the Victim Demographic Analysis Section, we analyze victim
demographics and their relationship with crime severity, focusing on
examining the impact of factors such as age, gender and race. We employ
various visualization techniques, including histograms, bar charts, pie
charts and box plots, to explore the distributions and relationships
within the data. Statistical methods, such as Pearson’s Chi-squared
test, are utilized to identify significant associations between
categorical variables, such as age groups and crime severity. Key
demographic variables were categorized to better understand their
relationship with crime patterns. Age groups were divided into
categories (Juveniles, Young Adults, Middle-aged and Elderly), while
gender included categories for males, females and non-binary
individuals. Racial diversity among victims was also assessed, with
proportions of different racial categories analyzed alongside crime
severity. Through this analysis, we uncover significant trends and
disparities, such as the concentration of crime involvement in specific
age and gender groups, as well as variations in crime severity across
racial categories and geographic regions. These findings provide
valuable insights for understanding victimization patterns and could
inform policy-making and targeted interventions aimed at addressing
these disparities effectively.  
  
In the Time Trend analysis section, we examine crime data from four
temporal perspectives: yearly, seasonally, weekdays, and hourly. Bar
plots are used to show the total number of crimes for each time period,
with stacked bar plots comparing the counts of serious and less serious
crimes. To further explore spatial variations, interactive line charts
created with `Plotly` visualize the temporal trends in crime counts
across different areas. Finally, line charts are also used to display
changes in crime counts over time by crime type, providing insights into
patterns of criminal activity.  
  
In the Location analysis section, according to the existing location
information of crimes in LA, including the area names, the premises
types, the geographic coordinators, the serious levels and the status of
crimes occurring, we do some exploratory analysis to further understand
the distribution of crimes. For visualization, we first use barplots to
show the distribution of crimes and their serious levels(1 for serious
and 2 for non-serious) in terms of their areas, premises and crime
status. Areas like 77th Street and Central have large numbers of total
crimes and serious criminal acts. What’s more, the crimes with continued
investigations status are much more than other types of status. Using
longitude and latitude information, we combine the visualization results
with the geographic and interactive map to better reflect the different
dimensions(serious level, crime status, etc.) of crimes information.  
  
After finished on analyzing patterns and trends in crime occurrences
based on various time scales, such as yearly, seasonal, weekdays, and
hourly, visualizing how crime evolves over time and across different
dimensions, examing distribution of primary crime locations, exploring
geospatial mapping data and modes of different crime types, as well as
the number of crimes in each area. We decide to bring these insights to
life, we chose to use Shiny to create an interactive dashboard. This
allows users to apply filters based on different areas in LA and time
trends, enabling them to observe crime counts and distributions
dynamically.  
  
For the shiny, we specifically selected data from 2023 instead of
including all available time periods. This decision was made because
2023 represents the most recent year with complete data and is
unaffected by the disruptions caused by the pandemic, ensuring a clearer
and more relevant analysis.  
  

## Additional analysis

**1. Chi-Squared Test**  
**1.1 Chi-Squared Test Between Age Group and Crime Severity**  
We conducted a Pearson’s Chi-squared test to evaluate the relationship
between victim age groups and crime severity. This statistical method
assesses whether there is a significant association between two
categorical variables. In our analysis, age was divided into four groups
(Juveniles, Young Adults, Middle-aged, and Elderly) and crime severity
was categorized as serious or less serious. The test yielded a
Chi-squared statistic of 4762.7 with 3 degrees of freedom and a p-value
less than 2.2e-16, indicating a highly significant association between
age groups and crime severity. The results revealed distinct patterns:
Juveniles were associated with a lower proportion of serious crimes
(~30%), while Young Adults and Middle-aged individuals had significantly
higher proportions (~55%), highlighting their greater involvement in
serious crimes. Elderly victims followed a similar pattern to Young
Adults but with slightly fewer serious crimes. This analysis confirms
that age is a significant factor influencing crime severity, providing
critical insights for targeted interventions and policy development.  
  
**1.2 Chi-Squared Test Between Different Time Period and Crime
Severity**  
The chi-squared statistic for yearl-difference is 387.8, p-value \<
2.2e-16; while for seasonal difference, the X-squared = 58.749, p-value
= 1.088e-12. For difference between weekdays, the X-squared = 262.23,
whose p-value is less than 2.2e-16. And for the difference in different
hour period of the day, the X-squared is 13747,p-value \< 2.2e-16. All
these test result shows that there are significant differences in the
distribution of severity of cases between different year, seasons,
weekdays and hour periods of the day.  
  
**1.3 Chi-Squared Test between serious levels and areas & premise
types**  
Using chi-squared test combining with heatmaps, we can find significant
differences of crime serious levels in different areas and premise
types. Also, the premise types of crimes in different areas are also
significantly different. In testing relationship between crime
seriousness level and areas, the Chi-Square Statistic is 2858.69,
indicating a very high dependence between serious level and area in LA.
In testing relationship between the type of premises and the serious
level of incidents, the Chi-Square statistic is 182154.31, indicating a
very high dependence between serious level and premises types. In
testing the relationship between the type of premises and different
areas, the Chi-Square statistic is 179318.97, indicating a very high
dependence between areas and premises types.  

**2. Prediction of the Crime Serverity**  

We designed a robust machine learning model using the **XGBoost
algorithm** to predict the severity of crimes based on fundamental
information, focusing on the “what,” “when,” and “where” of the crimes.
**This classification enables better prioritization for resource
allocation and decision-making in law enforcement.** The model’s
performance was rigorously evaluated through standard metrics, including
**accuracy** and **ROC-AUC**, which measured the overall predictive
capability, as well as **cumulative gains** and **lift**, which assessed
its ability to rank high-severity crimes effectively. Additionally, the
analysis highlighted the importance of temporal features (such as date
and time) and demographic attributes (e.g., location and victim details)
in determining crime severity. These insights provide valuable
information about the underlying patterns and factors influencing crime,
offering actionable intelligence for improving crime prevention
strategies and resource management.

## Discussion

This project provides a comprehensive analysis of crime patterns in Los
Angeles, utilizing data from the LAPD to explore the dynamics of crime
across various time scales and geographic locations. By examining crime
trends from different temporal perspectives—yearly, seasonal, weekday,
and hourly—we uncovered significant variations in crime severity and
frequency. The project also explored spatial trends, revealing that
certain areas experience higher crime rates, which are strongly
associated with specific types of premises. Interactive visualizations
created using Shiny allowed for dynamic exploration of these trends,
providing insights into how crime evolves over time and across different
neighborhoods.  
  
However, this analysis has several limitations. The dataset only
includes reported crimes, which may not fully represent the entire scope
of criminal activity, especially incidents that go unreported. Another
limitation of this analysis is its reliance on aggregated data, which
may obscure granular details or patterns unique to specific
neighborhoods or communities. Aggregation can sometimes mask disparities
in crime rates and prevent a nuanced understanding of localized issues.
Future research could expand the analysis by incorporating additional
variables, such as socio-economic conditions or environmental factors,
to better understand the underlying causes of crime. Enhancing the
analysis with machine learning techniques could also improve the
accuracy of crime severity predictions, offering more precise and
actionable insights for law enforcement and policymakers to make
informed decisions.  
  

## Data Source

This is a dataset of recent crime data from Los Angeles, covering a wide
range of crime types, from violent crimes like homicide and assault to
property crimes like theft and burglary. The data is carefully
organized, providing insights into crime trends, geographic differences,
and temporal patterns. The dataset can be downloaded directly from
<https://www.kaggle.com/datasets/arpitsinghaiml/u-s-crime-dataset/data>.
