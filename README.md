<div id="header" align="center">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/64395120/183522052-b85d6959-2490-4d61-b47c-bffd30015efd.png">
</div>

<h3 id="header" align="center">
 :notes: Pursuit of Happiness
</h3>

### :globe_with_meridians: Context
The World Happiness Report is a publication of the Sustainable Development Solutions Network, powered by the Gallup World Poll Data. The data used in the analysis is collected from the year 2015 to 2022; contains 175 countries ranking by happiness score on a scale from 1 to 8. There is no fixed formula to determine what makes a country happy. However, in recent years, happiness has become a strongest indicator to judge a country's social progress. The happiness indicator has been getting more attention from people accross the globe. 

### :star: Data Preprocessing 
- Rename the fields for consistency 
- Combine the world happiness reports from 2015 to 2022
- Remove the unnecessary fields in Tableau Prep
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/64395120/184283157-7f8e61d4-8b3d-4cb0-a952-e3a8ccd48513.png">

### :bulb:Data
- Here is a slice of the data:
<img width="1077" alt="Screen Shot 2022-08-11 at 11 29 49 PM" src="https://user-images.githubusercontent.com/64395120/184285333-a1e0fbb0-d797-4b5f-bd2c-85022d87c96b.png">

### :mag:  Data Cleaning 
- Checking the null values using isnull().sum() in pandas libaray. No null values are found
- Rename the fields using rename() in pandas library
<img width="922" alt="Screen Shot 2022-08-11 at 11 12 01 PM" src="https://user-images.githubusercontent.com/64395120/184283851-e172305b-8eb5-4982-8c43-c5e113034636.png">

### Exploratory Data Analysis
Exploring numerical features by visualizing in histogram
- There are 147 countries ranging from 1 to 146 based on their happiness score 
                  - In the happiness score, the score is from a minimum of ~2 to a maximum of ~8. Most of the countries received an average score of 5

      
![Screen Shot 2022-08-11 at 11 32 36 PM](https://user-images.githubusercontent.com/64395120/184285508-735b18bc-534a-4964-8557-59308117807c.png)
