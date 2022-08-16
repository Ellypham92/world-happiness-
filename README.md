<div id="header" align="center">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/64395120/183522052-b85d6959-2490-4d61-b47c-bffd30015efd.png">
</div>

<h3 id="header" align="center">
 :notes: Pursuit of Happiness
</h3>


#### ** [View visualization in tableau](https://public.tableau.com/app/profile/elly.pham/viz/Thingsthatmakeyouhappyaccordingtoscience/HappinessDashboard)

### :globe_with_meridians: Context
The World Happiness Report is a publication of the Sustainable Development Solutions Network, powered by the Gallup World Poll Data. The data used in the analysis is collected from the year 2015 to 2022; contains 175 countries ranking by happiness score on a scale from 1 to 8. There is no fixed formula to determine what makes a country happy. However, in recent years, happiness has become a strongest indicator to judge a country's social progress. The happiness indicator has been getting more attention from people accross the globe. 

### :star: Data Preprocessing 
- Rename the fields for consistency 
- Combine the world happiness reports from 2015 to 2022
- Remove the unnecessary fields in Tableau Prep
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/64395120/184283157-7f8e61d4-8b3d-4cb0-a952-e3a8ccd48513.png">

### :bulb:Data
- [View data source](https://www.kaggle.com/datasets/mathurinache/world-happiness-report)
- Here is a slice of the data:
<img width="1077" alt="Screen Shot 2022-08-11 at 11 29 49 PM" src="https://user-images.githubusercontent.com/64395120/184285333-a1e0fbb0-d797-4b5f-bd2c-85022d87c96b.png">

Definition:
- GDP per capita: a reflection of such economic health into an individual citizen perspective
- Social support: tangible and intangible resources that are available to one
- Healthy life expectancy: the average number of years that one is expected to live in a good health 
- Freedom to make life choices: the ability to decide or choose things without any constraints from external parties
- Generosity: how kind one to another
- Perceptions of corruption: the levels of corruption by country
### :mag:  Data Cleaning 
- Checking the null values using isnull().sum() in pandas libaray. No null values are found
- Rename the fields using rename() in pandas library
<img width="922" alt="Screen Shot 2022-08-11 at 11 12 01 PM" src="https://user-images.githubusercontent.com/64395120/184283851-e172305b-8eb5-4982-8c43-c5e113034636.png">

### Exploratory Data Analysis
1. Exploring numerical features by visualizing in histogram
![Screen Shot 2022-08-11 at 11 32 36 PM](https://user-images.githubusercontent.com/64395120/184285508-735b18bc-534a-4964-8557-59308117807c.png)
- In the happiness score, the score is from a minimum of ~2 to a maximum of ~8. Most of the countries received an average score of 5
- In GDP per capita, we found an outlier where it got 0. However, most of the countries are in the bucket of 1.5 to 2.0
- In Social support, we also found some countries are in the lower tail. However, a lot of the countries are having good social support programs as we see the histogram is left skewed
- In Healthy life expectancy, looks like the majority are having healthy life with a very few that are still struggling
- In Freedom to make life choices, then we can see the histogram is left-skewed, meaning people now with the freedom to decide on their course
- In Generosity, we found outliers that are at the higher end. However, many countries are ranked from 0 to 0.2 which is the lower
- In Perceptions of corruption, the average score is 0.154781 which is way lower than the max score of 0.587

2. Exploring the correlation between the numerical features
![Screen Shot 2022-08-11 at 11 42 55 PM](https://user-images.githubusercontent.com/64395120/184286430-8b2eaa6c-2c4b-42b6-8788-be1e80c6af00.png)
- Happiness score is highly correlated to GDP per capita, Social Support, and Healthy life expectancy. Weak correlation to Generosity
- GDP per capita is moderately correlated to Freedom to make life choices and having a weak correlation with Generosity
- Healthy life expectancy is highly correlated to GDP per capita and having a weak correlation with Generosity
- It is unexpected that Generosity is having a weak correlation to GDP per capita, Social support, and healthy life expectancy

3. The proportion of 'Country', 'GDP per capita', 'Social support', 'Healthy life expectancy', 'Freedom to make life choices','Generosity', 'Perceptions of corruption' in top 15 happiest countries and top least 15 happy country
**Top 15 happiest country**
![Screen Shot 2022-08-11 at 11 46 04 PM](https://user-images.githubusercontent.com/64395120/184286714-e9acbe71-fb3a-4fd8-b4b5-6e2d3659e921.png)
- The visualization shows the estimated contributions of the reported factors to the overall happiness of a country. In the happiest countries, it appears that GDP per capita, Social support, Healthy life expectancy, and Freedom to make life choices play the most important roles
- On another note, the proportion of these factors is almost the same across these happy countries

**Top 15 least happy country**
![Screen Shot 2022-08-11 at 11 50 17 PM](https://user-images.githubusercontent.com/64395120/184287078-3e694687-ce24-4c36-a0ff-833e475042ca.png)
- For the least happy countries, the main three factors that play important roles are also GDP per capita, Social support, and Health life expectancy, Freedom to make life choices
- Additionally, we discovered the proportion of the reported factors changes and are proportionally different across these countries compared to the top 15 happiest countries which we do not see much. An example, Afghanistan has no social support and Rwanda is not having good social support programs

4. Predictive Analysis 
- We choose Linear Regression since the model produces the highest accuracy in comparision to Random Forest, Decision Tree, or Ridge Regression
![Screen Shot 2022-08-11 at 11 54 09 PM](https://user-images.githubusercontent.com/64395120/184287417-6a3002b2-94b3-4b49-94cd-861babe7fc48.png)
![Screen Shot 2022-08-11 at 11 54 45 PM](https://user-images.githubusercontent.com/64395120/184287448-a809b402-679a-4edf-bde0-eba17080fc9a.png)

- The most important features that affect the well-being of the citizens by examining the coefficents 
![Screen Shot 2022-08-11 at 11 52 07 PM](https://user-images.githubusercontent.com/64395120/184287682-4e43f826-87fc-4f22-b3f3-9adc3b699c06.png)

- Visualizing the important features
![Screen Shot 2022-08-11 at 11 56 13 PM](https://user-images.githubusercontent.com/64395120/184287740-23cbd312-cf9e-45cc-a639-c40bed937d37.png)

- It appears that Freedom to make life choices is the most important factor contributing to the country happiness followed by Healthy life expectancy, Social support. GDP per capita seems to be less important than the other factors based on what we found

### :star2: Conclusion 
As our life has significantly improved over the past century, it is important for us to pay more attention to our well-being life. This analysis result would ultimately provide a direction for the government in deciding where a country should be heading in the next years and how to maintain and improve the happiness of their citizens.

We learned that most of the happiest countries are located in Western Europe, North America, and ANZ area where their economy is fully developed and public services is fully accessible. On another hand, the least happy countries are located in South Africa and South Asia which often experience the instability. The reported indicators in the reports are not consitent between the least happy countries; an example is that Afganistan has no social support program and their citizens seem not having the social right to make the decision on their own course. 

All of the variables in the report are somehow correlated; however we discovered a truthful fact is Freedom to make life choices, healthy life expectancy, Social support, and lastly GDP per capita appear to deciding whether a country or region is being happier or less happy. Our living conditions have improved across the regions compared to the past, people tend to care more about their rights as a citizen and how they can maintain a healthy life.

Due to the limited availability of data dimensions, the accuracy of our research can be improved over time as more information is collected.
