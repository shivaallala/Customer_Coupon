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
The dataset comprises coupons for different establishments, with 'Coffee House' being the most prevalent, followed by 'Restaurant(<20)', 'Carry out & Take away', 'Bar', and 'Restaurant(20-50)'.
Subsequently, missing values in the 'Bar', 'CoffeeHouse', 'CarryAway', 'RestaurantLessThan20', and 'Restaurant20To50' columns were identified. The decision to drop the 'car' attribute was also justified, given the significant number of missing values.

Further preprocessing steps included cleaning the 'passenger' column by removing parentheses and converting the 'temperature' column to a numerical format. In terms of coupon acceptance, approximately 56.8% of the total observations chose to accept the coupon, indicating a moderate acceptance rate.

To visually represent the data, a bar plot was used to visualize the count of accepted coupons for each coupon type, providing a clear overview of user preferences. Additionally, a histogram depicted the distribution of temperatures in the dataset, with a peak around 80 degrees Fahrenheit.

This initial analysis sets the stage for a deeper exploration of factors influencing coupon acceptance, addressing missing values, and uncovering patterns within the dataset. Further steps will involve statistical summaries, exploratory data analysis, and the development of insights to distinguish between customers who accepted and those who did not accept driving coupons.