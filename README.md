# PA_5.1
Contains code for practical application repository 5.1. This project will use data visualizations and probability distributions to distinguish between customers who accepted a driving coupon vs those who did not.

# Will the Customer Accept the Coupon?

### Goal: 
The goal of this project is to use data analysis methods to distinguish between customers who accepted a driving coupon versus those that did not.

Imagine driving through town and a coupon is delivered to your cell phone for a restaurant near where you are driving. Would you accept that coupon and take a short detour to the restaurant? Would you accept the coupon but use it on a subsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaurant? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?

Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

### Data: 
This data comes from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. Answers that the user will drive there ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’.  There are five different types of coupons -- less expensive restaurants (under \$20), coffee houses, carry out & take away, bar, and more expensive restaurants (\$20 - $50).

### Analysis:
Data has been examined for missing values. It was found that more than 99% of data is missing for 'car' column. The 'car' column has been deleted based on this finding.
Less than 2% of values were missing for the columns - Bar, CoffeeHouse, CarryAway, RestaurantLessThan20, and Restaurant20To50. These have been replaced with most common values. The mode was calculated and used to replace the missing values for these columns. 
Data is re-examined using info() function. 
Next, the proportion of drivers who chose to accept the coupon was calculated and visualized. 
Then, the temperature column was visualized. Then, analysis was focussed on 2 parts - part 1 consisted of investigating bar coupons acceptance rates as directed by the assignment questions and part 2 consisted of exploratory data analysis of coffee house coupons and their acceptance rates based on various criteria.
For part 1, a dataframe was created for just the bar coupons and for part 2, a dataframe was created for just the coffee house coupons.
Acceptance rates for various criterion were calculated and some were plotted using bar plots.

### Results and hypothesis:

**Part 1 - Investigating the Bar Coupons**

**Observations:**
41% of bar coupons were accepted.
Drivers visiting bars more than once a month, especially >3 times, have about 77% acceptance rate, likely due to their regular bar-going habits.
Drivers with non-kid passengers and non-farming occupations show a 71% acceptance rate, reflecting social, urban lifestyles.
Frequent bar-goers over 25 have a 70% acceptance rate, showing appeal across young to middle-aged drivers.
Drivers with income < $50K and like to socialize, or those who have spouse or are single, or those under 30, part of a 61% acceptance rate, accept coupons as deal-seekers.

**Hypothesis:**
Drivers who frequently visit bars, especially those with social, urban lifestyles, non-widowers and from lower incomes, are highly likely to accept Bar coupons due to their regular bar-going habits and deal-seeking behaviors. These targeted segments, spanning young to middle-aged adults, show significantly higher acceptance rates (61%–76%) than others, making them prime candidates for coupon campaigns. Overall, acceptance rate for bar coupons is 41%.

**Part 2 - Explorative data analysis of Coffee House coupons**

**Observations:**
Total acceptance rates are 50% for coffee coupons.
Acceptance rates are highest (64%) at 10 am.
Similar acceptance rates between men and women (51% vs 49%)
Acceptance rates for same direction were 53% vs 49% if venue is in the opposite direction.
High acceptance rate of 60% when passanger is a friend/s and when weather is sunny and passanger is a friend(s).
Acceptance rates seem to go down after 50 years of age.
Younger people below 21 years seem to have the highest acceptance rates (close to 70%) but the number of people under 21 are lower compared to other age groups.
As expected, the acceptance rates were slightly higher - 54% in unemployed populations compared to employed people - 49%.
Education levels did not much of a difference with respect to acceptance rates. The 'some high school' group showed a higher rate but upon investigation, it was noted that the subset has significantly low data points.
The income level between 75000 and 87499 showed the lowest acceptance rate of 30% compared to all other income levels.
Acceptance rates decreased as travel time increased - 50% for >= 5 minutes, 45% for >=15 minutes, 35% for >=25 minutes.

**Hypothesis:**
Based on the observations, I hypothesize that younger individuals (below 21) and unemployed populations exhibit higher coffee house coupon acceptance rates, particularly in social settings like sunny weather with friends or at peak morning times (e.g., 10 AM), due to greater social motivation and time availability. People tended to accept the coupon if they are closer to the coupon location, there seems to be an inverse relation between the travel time and acceptance rate as expected. The low acceptance rate (30%) for the $75,000–$87,499 income group may reflect reduced perceived value of coupons among mid-income professionals with less flexible schedules or preferences for alternative venues. Additionally, while gender and education level have minimal impact, the higher rate for the 'some high school' group is likely unreliable due to small sample sizes. Acceptance rates also appear influenced by convenience, with same-direction venues slightly preferred, and decline after age 50, possibly due to differing lifestyle priorities. Overall acceptance rates are 50% for the coffee coupons.

### Next steps:
It is helpful to add additional questions to the survey like how much do people usually spend at a bar, coffee house, or others. It is also useful to get coupon details - eg: discount percentage. Further analysis could give rise to deeper insights and patterns.
