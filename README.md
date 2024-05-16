# 201764720

‘Deprivation indexes have widespread use in academic research and in local and national government applications.’（Norman et al., 2020）And Lloyd indicates that ‘the measurement of deprivation for small areas in the UK has provided the basis for the development of policies and targeting of resources aimed at reducing spatial inequalities.’, which is helpful. (Lloyd et al., 2023）

In order to investigate whether there is a linear regression relationship between the Leeds Area Deprivation Index and the percentage of the Leeds Area population born in the UK, this analyses are based on Census data for 2021 Lower Layer Super Output Areas(LSOA) in Leeds. In particular, five influencing factors(‘Household Composition: One person household: Aged 65 and over; measures: Value’, ‘Household Composition: One family only: Lone parent; measures: Value’, ‘Household Composition: No adults in employment in household: With dependent children; measures: Value’, ‘Variable: Lives in a communal establishment; measures: Value’, ‘Variable: Schoolchild or full-time student aged 4 and over at their non term-time address; measures: Value’, ) were selected from the aspects of family population composition, economic level and marital status. Since the five factors are nearly extracted from different tables, in order to facilitate data analysis and code readability easier, the five factors are first divided into two groups according to different units (individual or household) and named respectively which are called ‘total_hh’. ‘total_resi’.

This research is divided into two main parts. The first part involves calculating and visualising the deprivation index in the Leeds area and observing its distribution pattern in Leeds. The second part uses the OLS linear regression model to verify the deprivation index and the not British-born population in each area of Leeds. It also seeks to establish whether there is a linear regression relationship between the percentage of the total nonregional population.

Firstly, it is essential to ensure that the polarities of the selected factors are identical (if they differ, they must be converted; however, the five factors selected here have the same polarity. The higher the proportion, the greater the degree of exploitation). On this basis, the percentages for each region are calculated. At this juncture, new dataframes named ‘new_hh’ and ‘new_resi’ are generated and merged into ‘merge_df’. It is advisable to utilise simple code to comprehend data types and structures. The subsequent step is to conduct a correlation analysis on the five factors. The observation results indicate that the correlation between ‘Household Composition: One family only: Lone parent; measures: Value’ and ‘Household Composition: No adults in employment in household: With dependent children; measures: Value’ is greater than 0.8 (0.89), which suggests that the correlation between the two factors is particularly strong and there may be exist collinearity. The method of variance inflation factor was employed to conduct a collinearity analysis on the two factors. The VIF value was found to be less than 10 (4.749044), indicating the absence of multicollinearity. Consequently, the next step of standardisation could be initiated. Typically, the standardisation selection method is z-value standardisation. However, this method is more suitable for data that conforms to the normal distribution. But it has been established that the data does not conform to a normal distribution. Consequently, discrete standardisation has been applied to the five factors, resulting in the generation of a new data frame named ‘scaled_df’. Following this, the deprivation index has been calculated.

The next step is to visualise the results of the deprivation index. The geographic data in the Leeds region should be uploaded in the leeds region .geojson format to the colab and linked with the deprivation index (the link fields are ‘LSOA21CD’ and ‘lsoa11cd’), so that it can be visualised with the index field. Furthermore, the "magma" colour palette should be employed to display colours, in order to prevent patients with red-green blindness and colour weakness from being able to distinguish the colour changes in the picture. Additionally, corresponding colour bars and corresponding questions should be included. As illustrated in the figure, the exploitation index of each LSOA in Leeds is below 2.5 and shows a cluster distribution. In general, the degree of exploitation decreases from the middle to the surrounding areas. However, there are only a few areas in the city centre that show very low levels of deprivation, and there are also areas in the northeast that have very high levels of exploitation. Furthermore, the distribution of various groups in the Leeds area can be understood. The use of the gradient ‘YlGnBu’ can better express the changes in each region.

The second part of the study involved the establishment of an OLS model for the two factors of the deprivation index and crime rates per 1,000 residents in leeds. This was accompanied by the display of tables and fitting diagrams. In order to enhance the visual impact of the fitting diagram, the colour contrast was adjusted to make the fitting line and data points more vivid. The data distribution was found to be highly dispersed The fitting degree was deemed to be unsatisfactory. Consequently, it can be concluded that there is a very weak linear regression relationship between the Leeds area deprivation index and crime rates per 1,000 residents in leeds

Data source: 
census data: https://data.cdrc.ac.uk/geodata-packs 
crime datat: https://climatedataportal.metoffice.gov.uk/datasets/cf8f426fffde4956af27a38857cd55b9_334/explore?location=55.007601%2C-3.277408%2C5.77

Reference:
Norman, P. (orcid:---), Berrie, L. and Exeter, D. 2020. Calculating a deprivation index using census data.
Lloyd, C.D., Catney, G., Wright, R., Ellis, M., Finney, N., Jivraj, S., Manley, D. and Wood, S. 2023. An ethnic group specific deprivation index for measuring neighbourhood inequalities in England and Wales. The Geographical journal.
