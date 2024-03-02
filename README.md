# Will a Customer Accept the Coupon?

In this project, the focus is on analyzing customer responses to driving coupons delivered through a mobile application. The dataset, sourced from a survey on Amazon Mechanical Turk, encompasses various driving scenarios, each associated with specific attributes such as gender, age, marital status, number of children, education, occupation, annual income, and driving habits related to different types of coupons (e.g., restaurants, coffee houses, bars).

The overarching goal is to understand the factors influencing a driver's decision to accept or reject a coupon. Scenarios include considerations of proximity to the business, time, weather, presence of passengers, and the specific type of coupon. For instance, questions may arise around whether drivers are more likely to accept a coupon for a restaurant, coffee house, or bar. Moreover, factors such as the age and gender of the driver, the presence of children, and the urgency of the destination are considered.

The analysis involves employing visualizations, statistical summaries, and probability distributions to distinguish between customers who accepted driving coupons and those who did not. Potential questions to address include:

Demographic Influence: Does the age, gender, marital status, education, occupation, or annual income of a driver impact their likelihood of accepting a coupon?

Driving Habits: Are there patterns in the number of times a driver goes to a restaurant, coffee house, bar, or engages in takeaway food purchases that correlate with coupon acceptance?

Location and Urgency: How does the location of the user, destination, and venue influence coupon acceptance? Does the urgency of the destination play a role?

Weather and Time: Are drivers more inclined to accept coupons during certain weather conditions or times of the day?

Passenger Presence: Does the presence of passengers, such as a partner, children, or friends, affect coupon acceptance?

## Data Analysis and Preprocessing Summary

In the initial phase of the analysis, the dataset from the 'coupons.csv' file was loaded into a pandas DataFrame, and the 'car' attribute, which was missing the majority of values, was dropped. The dataset includes diverse attributes such as destination, passenger, weather, temperature, time, coupon type, expiration, gender, age, marital status, presence of children, education, occupation, income, and more.

The investigation revealed some missing values in attributes related to different coupon types (e.g., 'Bar', 'CoffeeHouse', 'CarryAway', 'RestaurantLessThan20', 'Restaurant20To50'). These missing values will need to be addressed during further analysis. Below is a sample info on the dataset.

![Dataset Info](data/Visualizations/data_info.png)

The dataset provides valuable insights into user behavior and preferences, with detailed information on various driving scenarios and coupon acceptance. Key observations include:

The majority of destinations are categorized as 'No Urgent Place,' with passengers often traveling alone.
Sunny weather is predominant, and the temperature distribution is skewed towards 80 degrees Fahrenheit.
The dataset comprises coupons for different establishments, with 'Coffee House' being the most prevalent, followed by 'Restaurant(<20)', 'Carry out & Take away', 'Bar', and 'Restaurant(20-50)'. Subsequently, missing values in the 'Bar', 'CoffeeHouse', 'CarryAway', 'RestaurantLessThan20', and 'Restaurant20To50' columns were identified. The decision to drop the 'car' attribute was also justified, given the significant number of missing values.

Look the screenshots of the results below. The first image on the left shows the attributes with null values where we can observe the car attribute only contains 108 non-null values. It is clear this attribute will not be useful to our analysis. The image on the right shows the remaining attributes with null values after removing car feature.

![Attributes with null values](data/Visualizations/Car%20Null%20values.png) ![After Car was removed](data/Visualizations/Attributes%20w:%20NAs%20After.png)

Further preprocessing steps included cleaning the 'passenger' column by removing parentheses and converting the 'temperature' column to a numerical format. In terms of coupon acceptance, approximately 56.8% of the total observations chose to accept the coupon, indicating a moderate acceptance rate.

![Count of Coupons Accepted Histogram](data/Visualizations/Coupons%20accepted%20hist.png)

To visually represent the data, a bar plot was used to visualize the count of accepted coupons for each coupon type, providing a clear overview of user preferences.

![count of Coupon type accepted](data/Visualizations/CouponType%20Coupon%20accepted.png)

This initial analysis sets the stage for a deeper exploration of factors influencing coupon acceptance, addressing missing values, and uncovering patterns within the dataset. Further steps will involve statistical summaries, exploratory data analysis, and the development of insights to distinguish between customers who accepted and those who did not accept driving coupons.

## Investigating the Bar Coupons

In this section, the focus was on exploring the behavior of customers who accepted bar-related coupons. The following key analyses were conducted:

#### Creating a subset for Bar Coupons:

A new DataFrame was created specifically for customers who chose bar-related coupons. This subset included various attributes such as destination, passenger type, weather conditions, temperature, time, and more.


#### Proportion of Bar Coupons Accepted:

The proportion of bar coupons that were accepted was calculated. Approximately 41.0% of the customers who received bar coupons accepted them. The acceptance rates were compared between customers who visited bars three or fewer times a month and those who visited more frequently. A clear distinction emerged, with a higher acceptance rate (76.88%) observed among customers who frequented bars more often.

![Coupons accepted for range of times drivers visited the bar monthly](data/Visualizations/Time%20went%20to%20bar.png)



#### Comparing Acceptance Rates Based on Age and bar visits frequency:

The acceptance rates were compared between drivers who visited bars and were above 25 years old versus those who were below 25. The results indicated that older drivers had a higher acceptance rate (54.06%).

![Bar Goers over 25 Vs. Inverse](data/Visualizations/Bar%20Goers%20over%2025.png)



#### Comparing Acceptance Rates Based on Family and Occupation:

Acceptance rates were compared between drivers who visited bars without kids and had occupations other than farming, fishing, and forestry, and others. The former group exhibited a higher acceptance rate (59.09%) while the inverse group exhibited a wopping low of 20.23 acceptance rate. 

![Bar Goers (Non-Kids, Non-Farming Fishing Forestry)](data/Visualizations/bar%20goers%20non-kids.png)

#### Comparing Acceptance Rates Based on Multiple Criteria:

Acceptance rates were compared based on a combination of criteria, including frequency of bar visits, age, family status, maritial status, and income. The acceptance rate for this filtered subset was relatively close to the average acceptance rate of the bar coupon accpetance rate but surpassing the overall acceptance rate. Acceptance rate for all Cusotmers of Bar Coupon is 41.00%. Acceptance rate based on the given criteria above is 43.46%

![representing the coupon acceptance rate between the criteria and the total acceptanc rate](data/Visualizations/Given%20Criteria%20q6.png)

<br>

### Hypotheses Formulation:

Hypotheses were formulated based on the observed patterns:

Hypothesis 1: Drivers who visit bars more frequently are more likely to accept bar coupons.<br>
Hypothesis 2: Older drivers (over 25) are more inclined to accept bar coupons.<br>
Hypothesis 3: Drivers without family responsibilities and those in specific occupations are more receptive to bar coupons.<br>
Hypothesis 4: The given criteria, combining age, bar visit frequency, family, and occupation, can predict a higher acceptance rate for bar coupons.<br>

Statistical Techniques: 

Descriptive statistics were utilized to summarize and explore key attributes of the dataset.
Comparison of acceptance rates involved calculating mean acceptance rates for different groups.
Results and Conclusions:
The analysis revealed significant patterns in the acceptance of bar coupons among different customer segments. Frequent bar visits, older age, absence of family responsibilities, and specific occupations were associated with higher acceptance rates. The formulated hypotheses provide a foundation for further testing and validation.

#### Next Steps:

Further statistical testing, such as hypothesis testing and regression analysis, can be employed to validate the observed patterns and assess the significance of the identified factors in predicting bar coupon acceptance. Additionally, qualitative insights or customer surveys may provide deeper understanding and context to the observed behavior.

<br>
<br>

## Investigation on Coffee House Coupon

### Data Exploration and Transformation

In this section, the analysis focused on the Coffee House coupon data, exploring the characteristics of passengers who accept these coupons. The process involved data exploration, transformation, and acceptance rate calculations for various attributes. A new DataFrame, ch, was created containing only data related to the Coffee House coupon.

The CoffeeHouse features contains 5 unique frequency ranges of visits made to the coffee house. The missing values in the 'CoffeeHouse' column were identified and filled based on the proportions of existing categories. The image on the left displays the proportions of each coffee house category before the null data points were filled. The image on the right display the proportions after the null data points were filled based on the proportions of existing categories. 

![Before Nulls filled](data/Visualizations/Coffee%20Coupon%20Visuals/CoffeeHouse%20Proportions%20before.png) ![After Nulls Filled](data/Visualizations/Coffee%20Coupon%20Visuals/Coffeehouse%20Prop%20After%20Nulls%20filled.png)

Below is a distribution plot to show the consistency even after the null values were filled. 

![CoffeeHouse Attribute distribution before and After Null data points filled](data/Visualizations/Coffee%20Coupon%20Visuals/CoffeeHouse%20attrb%20Distribution.png)

#### Income level

A new column, 'income_level' was derived from income attribute to standardize income ranges for further analysis. The income feature is a categorical varible that would be difficult to use when determining the scale of the drivers financial status.

![Income Level display](data/Visualizations/Coffee%20Coupon%20Visuals/Income_level.png)


#### Proportion of Coffee House Coupons accepted. 

Within the Coffee House coupon sub-dataset, we find that only 49.92% of the drivers accepted the coupons. Please see below histogram. 

![Count of Coffee house Coupons accepted](data/Visualizations/Coffee%20Coupon%20Visuals/Count%20Of%20CH%20coupons%20accepted.png)


### Analysis

#### Coupon Acceptance Rate based on the Number of Times Driver Goes to the Coffee House Monthly:

Drivers who tend to to the coffee house 1 time or less or far more likely to decline the coupon to the coffee house than drivers who go to the coffee house more than once. Colored stacked bar graph represents this perfectly. The graph to show proportion of coupon acceptance for each category of Coffee House feature also validates the hypothesis.
Stacked color bar graph was created to show the count of coupons for each category (accepted and not accepted) based on the number of times a driver goes to the coffee house monthly.

![Relation between coupon acceptance and times went to Coffee House](data/Visualizations/Coffee%20Coupon%20Visuals/Stacked%20bar%20%20for%20Ch%20times%20visit.png)

The acceptance rate by the number of times a driver goes to the coffee house.

![Coffee House visits acceptance rate for each category](data/Visualizations/Coffee%20Coupon%20Visuals/CoffeeHouse%20visits%20acceptance%20rate.png)


#### Income Analysis

##### Coupon Acceptance Rate for Less than Average Income vs. Greater than Average Income:

The average income range was determined. Coupon acceptance rates were calculated for drivers with less than average income and drivers with more than average income. This is a perfect senario where the created feature income level was used. The income level feature allows us to calculate the average income range which was 50000 - 62499. As the Income feature is categorical, calculating the average income range directly would have been a challenge. <br>

Now that we have determined the average income range, we will be able to calculate the coffee house coupon acceptance rate for drivers who fall under the income ranges below and above the average income range. Based on the findings, acceptance rate for drivers who make less than average income is 52.26% and acceptance rate for drivers who make more than average income is 45.97%. Drivers who make more then average income are 6.29% more likely to accept the coffee house coupon than the driver who make less than the average income.

For better understanding lets visualize coupon Acceptance rate based on each income range. From the observing the below representation, the bar chart closely represents a uniform distribution. Hence the difference of averages of acceptance rates below and above the average income range are relatively insigificant to consider income as a individual factor to determine the rational for why drivers accept the coupon. 

Income ranges were grouped, and the acceptance rate for each range was calculated and plotted.

![Coffee House coupon acceptance rate by driver income range](data/Visualizations/Coffee%20Coupon%20Visuals/Ch%20acceptance%20rate%20by%20Income.png)






Lowest vs. Highest Acceptance Rate for Each Attribute Subset:

Coupon acceptance rates were calculated for various attributes like destination, passenger, weather, etc.
Subsets with the lowest and highest acceptance rates for each attribute were identified and overall acceptance rates were compared.
Coupon Acceptance Rate Based on the Type of Passenger Present:

Acceptance rates were calculated for different passenger types, and a bar plot was created.
Coupon Acceptance Rate for Drivers with Kids Based on Destination:

Subset analysis was performed for drivers with kids going to "No Urgent Place" and "Home."
Acceptance rates for these subsets were calculated.
Distribution of Passenger Types by Gender:

A violin plot was used to represent the distribution of passenger types by the gender of the driver.
Relationship Between Age of the Driver and Type of Passenger Present:

A boxplot was created to show the distribution of ages for different passenger types.
A bar plot was generated to depict the coupon acceptance rate by age and passenger type.
Income vs. Occupation by Passenger's Coupon Acceptance Rate:

Unique boxplots were created for each passenger group to visualize the relationship between income, occupation, and coupon acceptance.
Overall, the analysis provides insights into various factors influencing coupon acceptance rates, including income, occupation, age, gender, and passenger type. It helps in understanding patterns and preferences among drivers in relation to Coffee House coupons.
