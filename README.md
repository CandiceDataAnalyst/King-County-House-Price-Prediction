# King-County-House-Price-Prediction
<img width="614" alt="Screenshot 2023-07-08 at 18 47 41" src="https://github.com/CandiceDataAnalyst/King-County-House-Price-Prediction/assets/127648422/81dfaa75-c317-4179-a8f4-b3489d80db3b">

## PROJECT OVERVIEW
As a data scientist at FlyHomes, I am tasked with analyzing house sales data in the King County area to build predictive models for sale prices and identify the significant factors influencing these prices.</p>
**Business Question**:</p>
**Location**: Which areas in King County have the highest average house prices?</p>
**Inner Factors**: What specific house features (e.g., square footage, number of bedrooms) have the most substantial impact on the sale price?</p>
**External Factors**: How do external elements such as crime rates, school ratings, and demographic data affect house prices in King County?</p>
**Goal**: </p>
My goal is to support potential investors and homebuyers in making well-informed decisions by offering them data and insights gathered through the comprehensive analysis of the King County real estate market. Moreover, we aim to cultivate a more confident home-buying experience, assisting them in navigating the market with certainty and success.</p>

## DATA USED FOR THIS PROJECT
<img width="524" alt="Screenshot 2023-09-15 at 23 33 18" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/80e45a9b-f518-49b8-9b74-205eb25274a5"></p>
The main dataset utilized is the 'House Sales in King County, USA' dataset from Kaggle, selected to analyze house sales data. This dataset encompasses sales from May 2014 to May 2015 and includes 21 variables, with over 21,000 rows of data, each representing a single house sale. I downloaded it in CSV format and removed unnecessary columns, retaining only essential columns such as price, bedrooms, bathrooms, square footage of living space, square footage of the lot, floors, view, condition, grade, year built, and zip code.</p>

To enhance our analysis, I incorporated location-based data by sourcing tables from federal and state databases. This additional data brought in crucial factors such as property tax rate, the number of crimes, school ratings, unemployment rate, average commute time, median household income, total population, and median age. I then merged five different datasets based on zip codes to construct a comprehensive dataset for predicting house prices. To review the process of merging the datasets, you can check my GitHub under the 'data merging' folder.</p>

## DATA PROCESSING
<img width="1083" alt="Screenshot 2023-09-16 at 19 47 30" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/cd924ff8-bd83-4a1b-b3ca-1d49543626ea"></p>
The primary tool I utilized for data cleaning and modeling is Python. During the cleaning process, I identified and addressed issues such as missing values and duplicates, and rectified incorrect data types and values. A significant step in this process was applying a log transformation to the 'price', 'sqft_living', and 'sqft_lot' variables. This transformation was chosen because it helped in normalizing the distribution of these variables, making them more symmetric and thereby facilitating more accurate predictive modeling compared to the removal of outliers. Essentially, log transformation mitigates the effects of extreme values, rendering the data more homoscedastic and ensuring the residuals are normally distributed, which is a desirable property in regression analysis.</P>
For the modeling phase, I have selected the following variables: 'price_log', 'condition', 'grade', 'floors', 'bedrooms', 'bathrooms', 'sqft_living_log', 'sqft_lot_log', 'house_age', 'school_rate', 'unemployment_rate', 'travel_time_to_work', 'total_population', 'typical_levy_rate', 'median_age', 'median_household_income', and 'area_crime'. To delve into the specifics of the data cleaning process, you can check my GitHub under the 'data cleaning' folder.</p>

## METHODOLOGIES
<img width="1106" alt="Screenshot 2023-09-15 at 23 40 18" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/85cc1e93-43cc-477d-ae25-92f9978312f9"></p>
To provide potential investors and homebuyers with precise insights into the King County real estate market, I employ a combination of exploratory and predictive analytics. Initially, I utilize Exploratory Data Analysis (EDA) to clean, enrich, and visualize the data, thereby establishing a solid foundation for the subsequent predictive modeling.</P>

Following this, I build predictive models using two well-established approaches: Multiple Linear Regression (MLR) and Extreme Gradient Boosting (XGBoost). These methods were chosen for their complementary strengths; MLR, a classical statistical method, is favored for its straightforward interpretability, allowing for easy understanding and explanation of the factors influencing house prices. On the other hand, XGBoost, a machine-learning technique, is renowned for its high predictive accuracy, making it a powerful tool for predicting house prices with a higher degree of precision. Despite employing different techniques, both methods share a common objective: to create reliable predictive models for house pricing in King County, leveraging the unique advantages of each approach to offer a more rounded analysis.</P>

Upon the completion of both models, I proceed to the comparison and validation phase. In this stage, the performances of the MLR and XGBoost models are rigorously evaluated through cross-validation. I use key performance metrics such as Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R-squared value to assess their predictive power and reliability.</P>

## EXPLORATION
### City vs. Price
<img width="1099" alt="Screenshot 2023-09-17 at 23 42 23" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/095c8fc2-4c1d-44b1-b08d-2b18d40030e5"></p>
**Insights**:
- The top five cities with the highest average house prices are Medina, Mercer Island, Bellevue, Sammamish, and Redmond.</p>
- A significant portion of the houses are located in Seattle.</p>

### Bedrooms vs. Price
![bedrooms](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/f8e6a902-4396-45b2-9dec-aedbc2e5e8d4)
**Insights**:
- The majority of houses in the dataset have three bedrooms.</p>
- Generally, more bedrooms result in a higher house price. However, houses with 0, 11, and 33 bedrooms are exceptions. During deep exploration, I identified that these houses have impractical layouts, which affects the dataset accuracy.</p>
- To maintain data integrity, I removed entries with 0, 11, or 33 bedrooms.</p>

### Bathrooms vs. Price
![bathrooms](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/952688b2-892b-4d7b-8ce0-8345fe7929f3)
**Insights**:
- The majority of houses in the dataset have 2.5 bathrooms.
- Similar to the bedrooms, a higher number of bathrooms tends to increase the house price. However, houses with 0 and 7.5 bathrooms are exceptions. During deep exploration, I identified that these houses have impractical layouts, which affects their pricing.
- To maintain data integrity, I removed entries with 0 or 7.5  bathrooms.

### Floors vs. Price
![floors](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/f850ce18-1268-4024-889e-db0c55c82ef6)
**Insights**:
* Most houses are designed with one or two floors.
* Houses boasting 2.5 floors fetch the highest average prices in the market.

### Condition vs. Price
![condition](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/fce3f9b5-5367-471b-ae52-f17991b15996)
**Insights**:
* A large swath of houses has been awarded a condition score of 3.
* The average house prices don't vary much for homes with condition scores between 3 and 5.

### Grade vs. Price
![grade](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/7448cb75-1e25-453c-a44b-edb8667e8319)
**Insights**:
* The majority of houses receive a grade score of 7.
* A direct correlation exists between the grade score and the house price, with a higher grade denoting a higher price.
## MODEL COMPARISON
<img width="1002" alt="Screenshot 2023-09-16 at 00 01 41" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/91549de3-7896-4b89-9af8-ac0ab483b0e5"></P>
**Insights**:</P>
- **Inner Factors**:</P>
Both models emphasized that the variables sqft_living_log, sqft_lot_log, grade, and bathrooms consistently exert a significant impact on house prices. However, they displayed low R-squared values, indicating at a potentially limited relationship between the inner factors and the predicted outcomes. Before deploying the MLR model, I noticed that each variable had a high Variance Inflation Factor (VIF), which signals potential inaccuracies in the MLR results due to multicollinearity. In this case, where variables are highly correlated, this can skew the results and underrepresent the importance of some variables. Despite my attempts to remove the high VIF variables one at a time, I was left with no variables to analyze. Conversely, an article on Medium highlighted the XGBoost model's adeptness at managing multicollinearity issues effectively, suggesting it might furnish more reliable predictions compared to the MLR model in this context.</p>

- **External Factors**:</P>
Both models showed that the unemployment rate, travel time to work, and median age have a substantial impact on house prices. Yet, they encountered the same issue as in the inner factors analysis, presenting lower R-squared values, each variable having a high Variance Inflation Factor (VIF), and no variables were left for modeling after removing the variables with high VIF one by one.</p>

- **Overall Factors**:</P>
Both models exhibited high explanatory power when considering the overall factors, with XGBoost slightly outperforming MLR. The sqft_living_log and grade variables were significant in both models, highlighting their importance in the prediction.</P>

## Findings
- **Prime Locations for Investment**</p>
Based on my analysis of the various cities in King County, I identified that premium areas such as Medina, Mercer Island, Bellevue, Sammamish, and Redmond exhibit the highest average house prices. Therefore, investments in these regions are most likely to yield substantial returns due to the premium value attached to properties in these localities.</p>
**Actionable Insight**: Investors looking for high-value investments should prioritize these areas, while homebuyers aspiring to reside in upscale neighborhoods should focus their search in these cities.</p>

- **Desirable Floor Plans**</p>
My analysis highlighted that homes with approximately 2.5 floors command the highest average prices in the market.</p>
**Actionable Insight**: Sellers should consider renovating older homes to meet this standard, potentially increasing their market value. Conversely, buyers should be prepared to pay a premium for homes with this feature, viewing them as valuable assets in terms of both living experience and future resale value.</p>

- **The Significance of House Features**</p>
There are two factors that consistently influence a home’s market price: grade and square footage of living space. Simply put, houses that are graded higher and have more living space are priced higher on the market.</p>
**Actionable Insight**: For buyers, it’s a smart move to look for homes with larger living areas and higher grades, as these homes not only offer a better living experience but are also likely to appreciate more in value over time. Sellers, on the other hand, can increase the market value of their homes by making improvements that enhance the grade of the home, helping to secure a better offer when it comes time to sell</P>

- **Influential External Factors**</p>
The unemployment rate, commute time, and median age play pivotal roles in significantly influencing housing prices</p>
**Actionable Insight**: Buyers could look for areas with lower unemployment rates and reasonable commute times to work, coupled with a favorable median age demographic, to secure a property that promises a good quality of life and appreciation over time.</p>

## Recommendation
- **Data-Driven Marketing**:</p>
 Utilize the insights derived from the analysis to create data-driven marketing strategies. For example, highlighting the optimal house features (like the number of floors and grade score) in marketing.</P>
- **Advisory Services**: </p>
Offer advisory services to clients, helping them make informed decisions based on the significant factors influencing house prices in King County.</P>
- **Leveraging XGBoost**: </p>
Recommend leveraging the XGBoost model for predictive analyses given its slightly superior performance compared to the MLR model, especially in handling multicollinearity issues effectively.</P>

## Further Work
- **More sales data**:</p>
The dataset covers the period from May 2014 to May 2015. To reach a more accurate conclusion, it is essential to obtain data that is both more recent and spans a longer period.</P>
- **Temporal Analysis**:</p>
Conduct a temporal analysis to understand how house prices have evolved over time and identify any seasonal trends or patterns.</P>
- **Interactive Dashboard**: </p>
Develop an interactive dashboard that allows users to explore the data and insights visually and to generate custom reports based on their preferences.</P>
