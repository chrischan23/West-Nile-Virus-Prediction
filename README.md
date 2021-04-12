![](https://www.phdmc.org/images/articles/2018/20180813-mosquitoes.jpg)
# Project 4 - Fighting the West Nile Virus in Chicago

# Problem Statement

**Background**  
The West Nile Virus has been raging through the city of Chicago. According to the CDC, the virus has been the main cause of mosquito-borne diesease in the United States and it is transmitted by the bite of an infected mosquito. With the help of the Department of Public Health, data on mosquito infestation has been made available through their surveillance and control system. The data will help in determining where the best use of resource can be allocated to with the highest efficacy.

**Hence our purpose here is to find the most cost-effective way of eliminating the spread of the West Nile Virus from the transmission through mosquitoes**

# Executive Summary
The West Nile Virus in Chicago has been spreading across the city of Chicago. The proliferation of the diesease can be halted with the certain tools at our disposal. The objective of the team is to use the data shared by the Department of Public Health to derive a plan. This plan is to deploy the spraying of pesticides to the areas which are most at risk. It is with the view that the spraying of pesticide will kill off the mosquitoes.  
Hence, it is the duty of the team to propose which areas are most in need.

**Data Science Process**

* Data extraction  
* Data cleaning
* EDA
 * Data visualisation
 * Feature engineering
* Model selection  
 * Develop baseline
 * Data preparation
 * Model evaluation
 * Model selection

* Model optimisation
 * Adjust hyperparamters
 * Revaluate models

* Model testing and recommendations
 * Test optimised models
 * Evaluation and conclusion

* Conclusions and Recommendations
 * Cost Benefit Analysis
 * Findings and takeaways
 * Further opportunities
 
 # Notebooks

- [Train Test Cleaning](code/01_data_cleaning_train_test.ipynb)
- [Weather Spray Cleaning](code/02_data_cleaning_weather_spray.ipynb)
- [EDA](code/03_eda.ipynb)
- [Model Evaluation](code/04_model_evaluation.ipynb)
- [Model Optimisation and Conclusion](code/05_model_optimisation_conclusion.ipynb)

## Cost-Benefit Analysis 

To provide an initial background, the West Nile Virus has been prevalent in the United States since it first emerged in New York in 1999. Since then, it has spread across the other 48 states and has cost United States about \\$800 million reported in 2014, which is about \\$57 million each year, which does not include vector control.  

The two main methods that most local authorities adopt for widespread control of mosquitos are **aerial and truck-mounted spraying.**  
**Aerial Spraying**  
Advantages  
* Every type of mosquito would be affected quicker, including the Culex mosquitos, which primarily reside high in the trees 
* Helicopter spraying also allows for most of the target areas to be reached. EM is able to spray 95% of the targeted areas

Disadvantages  
* Expensive: The price of a single helicopter starts at \\$100000 with operating costs of \\$80000 per year  

**Truck Mounted Spraying**  
Advantages 
* Cheaper: A single truck with sprayer can cost \\$20,000 to \\$25,000 with an operating cost of \\$20,000 per year  

Disadvantages  
* Not as effective as aerial spraying because truck spraying cannot reach all areas and takes longer to treat a given area.

Zooming in on **Sacramento County California in 2005**, 163 human cases were reported which prompted an emergency aerial spray by local authorities. The spray was conducted over 6 nights, over an area of 477km2.
Costs amounted to approximately \\$701,790 which includes spray procedures and labour costs. 

As the size of Chicago city is approximately 606km2, the cost will be estimated to be roughly the same or less, considering that only certain hotspots will be targeted.  

The total cost of the 2005 Sacramento County WNV epidemic was around \\$2,979,037. Costs for treating patients alone exceeded costs of emergency vector control by \\$1,438,619, a ratio of 3:1. This difference suggests that for the benefits of the vector control to outweigh the cost of the epidemic, the spray event would need to prevent only 15 cases.

In terms of efficacy of the spray conducted, greatest mortality was encountered in cages placed in open fields (100% in each cage), whereas the lowest rates occurred in sentinel cages placed along the bank of a dry creek under dense canopy and between buildings of a residential site.

Overall mortality among mosquitoes placed in exposed or partially exposed sites (77.1%) was significantly higher than mortality
of mosquitoes placed in protected places (24.9%)

In summary, results indicated that the aerial spraying of pyrethrin in north Sacramento significantly reduced mosquito abundance and the number of infective bites received by human population. There were no new human WNV cases in either of the treated areas, whereas 18 new cases occurred in adjacent untreated areas in Sacramento County.

Of course, if local authorities do proceed with the pesticide spraying, we do have to recognise the long-term adverse health effects that it may have on public health. 

* National Research Council found that pregnant women and children have a greater risk of getting sick from pesticides.  
* In NYC in 2000 more people were reported to have gotten sick from pesticide exposure from spraying than from WNV.  
* New York State Department of Health states that adverse outcomes during or after an aerial or ground spraying of adulticides might include acute asthma attacks, other respiratory problems, and/or dermatological problems.

Sources:  
[Economic Cost Analysis of West Nile Virus Outbreak, Sacramento County, California, USA, 2005](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3322011/#:~:text=The%20total%20economic%20impact%20of%20WNV%20was%20%242.98%20million.)  
[The High Cost Of Treating People Hospitalized With West Nile Virus](https://www.npr.org/sections/health-shots/2014/02/11/275262857/the-high-cost-of-treating-people-hospitalized-with-west-nile-virus#:~:text=The%20result%3F,%24678%20million%20to%20%241.01%20billion.)  
[Impact of Aerial Spraying of Pyrethrin Insecticide on Culex pipiens and Culex tarsalis (Diptera: Culicidae) Abundance and West Nile Virus Infection Rates in an Urban/Suburban Area of Sacramento County, California](https://www.researchgate.net/publication/23182100_Impact_of_Aerial_Spraying_of_Pyrethrin_Insecticide_on_Culex_pipiens_and_Culex_tarsalis_Diptera_Culicidae_Abundance_and_West_Nile_Virus_Infection_Rates_in_an_UrbanSuburban_Area_of_Sacramento_County_Cal#pf2)  
[Economic Burden of West Nile Virus in the United States](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3945680/)
[Integrated Pest Management for Mosquito Control in Massachusetts](https://web.wpi.edu/Pubs/E-project/Available/E-project-040713-135959/unrestricted/MQP_-_Paper_-_April_7th_Edition.pdf)

## Conclusion 

**Gradient Boost Classifier** scored the best score in Kaggle as well as on test set. It achieved a score of 85.4% accuracy to predict pressence of virus. The classifer also has the least variance between test and training scores proving that it is not overfit.<br>
Based on feature importance it is evident that the virus is prevalent in certain locations (latitude and logitude has high importance), where certain species of the mosquitoes grow.<br>
Year, month and week of the year as well as some weather features such as resultant wind speed and average temperature are also seen to be influencing the presence of WN Virus. It is in line with our research, higher temperatures and wind conditions do affect pressence of mosquitoes <br>
These features can be used to determine the locations/ traps and decide when and where to concentrate on spraying efforts.  
**Model Limitations**<br>
Model did not perform well on the out of sample set from Kaggle and there is a significant variance in AUC score between the 2 scores. This may be due to the way the in sample training and test sets are split vs. the train and test set split that Kaggle did.<br>  

As per our cost benefit analysis, it would be a better choice to proceed with the vector control measures like aerial spraying as the benefits clearly outweigh the costs

## Recommendation 

Our recommendation is to proceed to conduct the vector control measures as explained above. 

Some areas that we can focus on to make the control measure effective are:
* Focus on areas our model predict are likely to have pressence of West Nile Virus
* Areas where mosquito species like Culex Restuans, Culex Pipiens and Culex Territansare most commonly found
* Certain time of the year where temperatures are warmer and windier like in the Summer

However, due to the long term detrimental effects of pesticide spraying, we reccomend this as a last resort where the virus is getting too out of hand. 

Instead, local authorities should foucs on public education that would prevent the virus from ever happening in the first place.
Good habits that can be taught to the public include:
* Remove all potential breeding areas – any place with standing or slow-moving water such as buckets, holes in trees, clogged gutters and down spouts, old tires.  
* Monitor ponds and sources of water regularly for signs of mosquito larvae.  
* Stock permanent water pools or ponds with fish that eat mosquito larvae and pupae.  
