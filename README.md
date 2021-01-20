# Indirect Methane Predictions

This is our final project for ENERES 131: Data, Environment, and Society taught by Duncan Callaway and Jessica Katz in Fall 2020. In this course, we applied statistical and analytical methods to build, estimate and interpret models that describe phenomena in the broad area of energy and environmental decision-making.


## Contributors
- Sara Ding
- Devon Madeksiak
- Michelle Kaganovsky
- Justin Wong


## Abstract
After pivoting away from the original methane prediction question we began to focus on other corollaries to methane emissions. Some of the connections between methane and the new prediction problems include: methane and CO are precursors to create the tropospheric ozone (a potent greenhouse gas and air pollutant that impacts food and water supplies) as well as public health effects that result from pollutants like methane. We incorporated various models such as Lasso, Ridge, Linear, and Gradient Boosting to model the datasets, along with using cross-validation to tune hyperparameters such as learning rate, or number of boosts to help us solve these prediction problems. Prediction problems include:

1. How can cattle demand predict the quality of air in California counties?
  - Using Linear Regression methods, we hoped to see how mitigating cattle supply can improve air quality as well as provide evidence for policies to offer incentives for plant-based diets in the future. Although livestock is known to be one of the most prevalent methane emitters, there is little impact on TOG likely due to the various air particles that TOG accounts for.

2. Is data on air quality measurement metrics, facilities known to be methane emitters, livestock population able to be used to predict asthma prevalence across counties?
  - The resource allocation relates to funding for research for the causes of respiratory illness,such as asthma by analyzing environmental and health impacts.

3. Can we predict the CO concentration tons/days based on data readily available for counties?
  - In order to determine which counties should encourage sale of Zero-Emission_vehicles (ZEV), increased access to EV charging stations, or subsidies for ZEV. The best predictor of CO measurements in the dataset was PM2.5, number of NZEV, and population using a shrinkage method of ridge regression.


## Background
Methane is 86 times more potent at trapping heat in the atmosphere than CO2 over a 20 year period, and methane is a precursor of and is often in conjunction with CO to create the tropospheric ozone, a potent greenhouse gas and air pollutant that impact food and water supplies as well as human health. The EPA states roughly 50-65% of methane is related to human activity with farm animals being responsible for about 28% of methane emissions in the U.S. Methane produced by various human activities: leakage from natural gas systems, raising livestock, and municipal waste landfilling.Even though methane itself is not likely to cause health problems, other pollutants typically found among methane are such as increased particulates that can get in your lung worsening respiratory issues like asthma. Some indirect effects on human health are the decrease in crop yield and quality of vegetation through its role as a precursor of tropospheric ozone[Climate & Clean Air Coalition].

For this project we hoped to use data collected from various Satellites to predict methane emissions in the state of California. Upon further research, we found it difficult to incorporate measurements that we could consider as our “true” methane measurement and thus pivoted in a new direction. Our current data focuses on air quality measurement metrics, facilities known to be methane emitters, livestock population, asthma prevalence, GDP, and population metrics for all 58 Counties in California. We hope to then predict how these air quality measurements may change in the future and whether some variables have more impact on air quality than others. Using features from a wide variety of sources has allowed us to explore prediction questions from various forms of human impact. From human preferences, to health effects, and ultimately communities which may be disproportionately affected.

By incorporating quantitative analysis and modeling methods, we are able to capture trends and provide a numerical value as to what extent these trends may change over time. For example, we incorporated records of livestock population, particularly cattle, because of its significant contribution to enteric fermentation (a form of methane emission) in the United States. Cattle not only contributes to over 95% of enteric fermentation but almost 20% of total methane emissions in the U.S (Mangino). We also incorporated data on the prevalence of Asthma because after researching our topic, we learned that living near facilities such as power plants, refineries and farms has links to respiratory health effects, such as Asthma. Additionally, we have incorporated data on the specific coordinates of these counties to produce detailed visualizations. Incorporating quantitative analysis helped quantify the predicted amount of CO ton/day the county produces, and it helped determine which features have the greatest predictive power which features can be excluded. The model's most predictive features were population, area of land, PM10, PM2.5, GDP, and number of Non-Zero Emissions. Predicting CO helps determine where to focus adding EV fueling stations, and possibly states can use part of their budget to subsidies electric vehicles in places with high predicted to help reduce CO, CH4, and tropospheric ozone pollutant.


## Policy Recommendation
Based on the datasets, we observed a strong relationship between EV vehicles, population, air pollutants(including methane), and EV charging stations. Because of this, I suggest the following policy:

**That the Plug-In Electric Vehicle (PEVs) Infrastructure program prioritizes counties with low “Charging Stations Per Capita” and expands the Clean Vehicle Rebate Project (CVRP) to offer private charging station rebates.**

Read more [here](https://docs.google.com/document/d/1zvaZrbekDWHQp6XLPeW_q_MJ188bg3KSs6uURG3o6Lc/edit?usp=sharing).


## Pivots
Initially, we wanted to predict which coastal communities and cities were most likely to be affected (at various seveerities) by global sea leveel rise.

However, we found this was infeasible because gathering data for such prediction was difficult and existing models used a bottom-up physics based modeling approach, which was far more complex than anticipated. We had hoped we could develop a machine learning model to replicate such a physics-based simulation model, but lack of reliable and consistent data on a national level was the main blocker. 

As a result, we switched to focus on methane emissions for reasons pointed out in the Background section above. We generalized our processed dataset(based in California countiees)  such that it is easy to add colummns based on independent data sets, such as the number of EV charging stations, populations, GDP per capita, Vista stations nearest to that county, and asthma prevalence. The thought process was to allow reusabilitity in our method so that other states/regions could follow a similar approach to robustly predict methane emissions by using data that already is collected to reduce the cost of meeasuring atmospheric methane. 


## Data Files

All data files can be found in [this Google Drive](https://drive.google.com/drive/folders/1gVO-JZjgHuoyeFx5ycSWdZOTDbbPbPbB?usp=sharing).

All data files come directly from the data sources. We also processed the data for our particular needs, which can be found in [this Google Drive](https://drive.google.com/drive/folders/1pw7uMJEV7jb5Y_hGf1M_XEFp5-oelMAL?usp=sharing).

## Data Sources
See "Input Data Description" for more details.
- [California Counties](https://catalog.data.gov/dataset/tiger-line-shapefile-2016-state-california-current-county-subdivision-state-based)
- [Vista CA](https://daac.ornl.gov/NACP/guides/NACP_Vista_CA_CH4_Inventory.html)
- [EMSEIC: Emissions by Emission Inventory County](https://ww3.arb.ca.gov/ei/maps/2017statemap/cntymap.htm)
- [California Charging Stations by County](https://www.energy.ca.gov/data-reports/energy-insights/zero-emission-vehicle-and-charger-statistics)
- [California Vehicle Population](https://www.energy.ca.gov/data-reports/energy-insights/zero-emission-vehicle-and-charger-statistics)
- [Cattle](https://quickstats.nass.usda.gov/)
- [Asthma Prevalence](https://healthdata.gov/dataset/asthma-hospitalization-rates-county/resource/9e998582-a70b-4c5c-a2bd-d7b358431944#%7Bquery:%7Bq:!alameda%7D%7D)
- [CA Population by County in 2019](https://www.california-demographics.com/counties_by_population)

## Notebook Explanations
- `Group7_FinalProject_2020.ipynb`: our final deliverable which is a compilation of our semester-long work. This not only includes data visualizatons and model predictions but also the motivations, background, and refereences for the project.
- `Carbon Monoxide.ipynb`: involves all the work done for the Carbon Monoxide prediction question. This includes data exploration, daata standardization, cross validation, feature selection, and model predictions.
- `EPA_gridded_methane_EDA.ipynb`: explorees a GIS dataset that displays geopandas plots of different atmospheric gases, as estimated from a bottoms-up approach.
- `asthma.ipynb`: first iteration of work done for the asthma prevalence prediction question.
- `vista_ca.ipynb`: where much of the data processing was done. 
- `cattle_v_tog (v2).ipynb`: second iteration of work done for the cattle prediction question.
- `flood_station.ipynb`: data visualization of NOAA flood stations in North America
