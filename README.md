
![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/iStock-1042841208.jpg) 

# user-engagement-analysis

## **1. Introduction**


The product team at Showcase wants to better understand "user engagement​" on the platform in October 2019. The purpose of this analysis is to define engagement, provide insights, and question any other metrics the Showcase can use to understand our approach better. 

## **2. Product success and user engagement metric definition**

First of all, Showcase's goal is to build a platform that encourages users to share, exchange ideas, connect, and learn from other users.

Therefore, there's an increasing need to better understand how users engage with the products and services.

Specifically, we should determine:

- Understand what factors affect user engagement.
- Predict long-term engagement early in the customer journey.
- Design and measure the effect of interventions on improving engagement.

To do these 3 things, we need a “North Star” metric we could focus on improving.

Here, I would like to use the "active time" per user spends on the Showcase's platform, within a given amount of time. Because engagement is when our user is realizing value, the more time users spend on our product, the more engaged they are. The real active time per user indicates how well the Showcase's platform meets user expectations after they log in and over time.


### **2.1 - Summary statistics of the numeric variables**

![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/1.png) 

The standard deviation of active time is 652, indicates that the values are spread out over a wider range. The reason may because of the small dataset, and the concern is that the more variability in the sample, the higher the chances of error.

### **2.2 - Active user amount and active time performance**

![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/2.png)

#### **Observations**:
- On average, the number of active users is 10, but there's a peak on 10/26, we can analyze the factors in the following sections.
- Once a peak reached, the number of active users decreased significantly in the next day.

![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/3.png)

Above graph summarizes the total number of comments, likes, and projects posted every day. As expected, a lot of engagements occurred on 10/5 and 10/26, which coincide with the relatively high user log-ins in the first graph.

We found that 10/5 and 10/26 fall on a weekend (Saturday), whereas the lowest engagement days, 10/14 falls on a weekday (Monday).
That explains that having more spare time on Saturday, users are generally more involved in our platform, while the behavior shows the low frequency, most of the users don't active in daily spurts – which again explains for the peak and trough.

Now, we can breakdown this analysis to see what engagement affects the user's active time most.

### **2.3 - Factors influence the active time**

#### **Breakdown to each level of active users based on the active time**

I clustered the users into 3 levels of active time:

- Low active user: active time is shorten than 5 minutes (300 seconds) in one session.
- Medium active user: active time is longer than 5 minutes, but shorten than 20 minutes (1,200 seconds) in one session.
- High active user: active time is longer than 20 minutes in one session.

![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/4.png)

For the median amount of projects added, the high active users only added 2 projects and are the same as a low active user. That explains that the high active users on our platform don't usually spend time on adding projects.

#### **Correlation between projects added and active time in each active user level**

![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/5.png)

For high active users, there are 2 sessions that have 6 projects added, it indicates that the more time they activate, the more projects were added than other users. However, there are only 2 points, that cannot be explained all in this phenomenon. There might be the outlier, or the data sample is not big enough.

#### **Correlation between likes given and active time in each active user level**

![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/6.png)

There is no significant difference between the active times of likes given and the level of active users.

#### **Correlation between comments given and active time in each active user level**

![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/7.png)

#### **Overall correlation map**

![image](https://github.com/miayuxin/sns-user-engagement-analysis/blob/master/Image/8.png)

## **3. Conclusion**

### **Discovered insights**

We have defined an engagement metric as "active time" per user spends in our platform, within a given amount of time. Based on this, we have discovered the below insights.

1. There were a lot of likes, comments, and projects posted on 10/24, which we determined happen to be Saturday, while not every weekend days follow this pattern. Perhaps there have other factors that influenced the engagement on that day.

2. For the median amount of projects added, the high active users only added 2 projects and are the same as a low active user. That explains that the high active users on our platform don't usually spend time on adding projects.

3. There's no linear relationship or any other correlation between the active times and likes are given / comments given. It does not indicate that the more likes / comments given, the more active time does.

### **Discovered problems**

*1. Small sample size*:

Small dataset reduces the power of this study. A study with low statistical power has a reduced chance of detecting a true effect. Additionally, to increase the accuracy on understanding what factors influence the active time, we should use the machine learning technique of building Random Forest model to extract the feature importances by evaluating the correlation value. However, it is hard to build the model due to the small dataset. It is hard to split data into training and testing dataset, and the small dataset will cause the issue with high variance. It means the model fits the training data well, but it does not generalize well on out of training datasets.

*2. Possibility of other features affected the user active time:*:

- Click through rate of projects/articles: Count the click when a signed-in member clicks on the specific article, user portfolio. Although it does not include other interactions like shares, reactions, or comments, it affects the active time. For example, we can identify that most of our users are active because of interested in reading various articles or viewing other users' portfolios.

- Login time: different times of day may affect the user's active time. For example, nighttime may be the peak, and most users won't engage in the platform during the daytime.

- Marketing promotion: there might have some e-mail marketing or commercial message influence the users visit, or some job applications might force candidates to build their portfolios on our platform, which influences the active time.

- Number of following / followers: the more following / followers may cause a longer active time.

### **Future work**

To improve problems, I have below recommendations.

- Collect more sample and additional features to determine what factors influence the user active time.

- Use Random Forest model to examine the feature importances, as well as predicting the active time.

- Construct the partial dependence plot to show how the predictions partially depend on values of the input variables of interest. We can measure this active time metric when conducting different experiments, such as A/B testing on increasing/update the feature, or business performance monitoring, etc.

Furthermore, if we have collected more data and features, we can calculate update engagement rate by adding the number of interactions, clicks, and new followers acquired, divided by the number of impressions the post receives.





