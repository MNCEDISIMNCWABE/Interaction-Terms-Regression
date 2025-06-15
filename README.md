Read More on My Blog Post: https://www.analyticsvidhya.com/blog/2024/08/a-guide-to-understanding-interaction-terms/

## Understanding Interaction Terms in Regression: A Practical Example

#### Overview
In regression modeling, interaction terms are used to capture the combined effect of two or more variables on the target variable. This can be particularly useful in scenarios where the relationship between the variables and the target variable is not simply additive. In this example, we explore the concept of interaction terms using a practical example: predicting the time spent by users on an ecommerce platform based on their activity.

#### Example: User Activity and Time Spent
Let's first generated a synthetic dataset to simulate user activity on an ecommerce platform. The dataset includes:
- ``added_in_cart`` : Whether a user added items to cart or not (1 for adding to cart or 0 for not adding to cart).
- ```purchased``` : Whether a user made a purchase or not (1 for making a purchase or 0 for not making a purchase).
- ```time_spent``` : The total time a user spent on an ecommerce platfotm (continuous). We are trying to predict this feature, i.e, how long a user will spend on an ecommerce platform based on whether they add items to cart and making a purchase.

<img width="311" alt="image" src="https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/363df886-3bc6-45e5-86d2-449cbefbce47">

Below we can start by examining the relationship between these two features and time spent.

![image](https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/022919b7-109d-4e65-8c76-4aac47fdfee4)

- As indicated by the boxplots above, both adding items to the cart and making a purchase are associated with significantly higher time spent on the platform.
- The median time spent by users who engaged in these actions is roughly double that of users who did not engage in these actions.


### Modelling

Since we are exploring the use of interaction terms, we'll start by building a regression model to predict the time users spend on the website based on two actions: adding an item to the cart and making a purchase. Initially, we will build the model without considering the interaction between these actions. This means we want to see if each action independently affects the time spent on the website.

Next, we will build another model that includes the interaction term between adding items to the cart and making a purchase. This will allow us to compare the combined effect of these actions on the time spent on the website with their individual effects. This means we want to determine if users who both add items to their cart and make a purchase spend more time on the website than what would be expected by simply adding together the effects of each action done independently.

#### Model without interaction term

Upon building the model the following results were observed: 

- The model without the interaction term explains about 80% (test R-squared) of the variance in the ```time_spent```, with a mean squared error (MSE) of 2.11. This means that, on average, the predictions of ```time_spent``` are off by about 2.11 squared units. While this model is fairly accurate, there's room for improvement.
- Additionally, the plot visually confirms that while the model performs reasonably well, there is significant room for improvement, particularly in capturing higher values of time_spent.

<img width="664" alt="image" src="https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/b9fc1b5a-d27d-4039-b903-f4e5438e7a89">



![image](https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/13ccbb7d-ed3b-405b-93e4-a7cba3b21952)


#### Model with interaction term

```df['purchased_added_in_cart'] = df['purchased'] * df['added_in_cart']```

- The scatter plot with the interaction term shows predicted values much closer to the actual values, indicating a better fit for the model with interacting term.
- The higher test R-squared value (from 80.36% to 90.46%) indicates that the model with the interaction term explains much more of the variance in the ```time_spent```.
- The lower MSE (from 2.11 to 1.02) indicates that the predictions of the model with the interaction term are more accurate.
- This improved fit is evident from the closer alignment of points to the diagonal line, especially for higher values of ```time_spent```. The interaction term helps capture the combined effect of user actions on the time spent.

<img width="620" alt="image" src="https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/e5ad2eb5-7565-423b-ba8f-433249c8d0f5">

![image](https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/e491fadc-ca0e-47e2-8e09-73270d6b8e76)


### Putting it all together

- The blue points represent the model predictions without the interaction term. These points are more spread out from the diagonal line, especially for higher actual time spent values.
- The red points represent the model predictions with the interaction term. These points are closer to the diagonal line, showing that the model with the interaction term makes more accurate predictions, particularly for higher actual time spent values.
- 
![image](https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/360fd295-0f10-4ef8-b267-b06a362de2ab)


## Conclusion
The improvement in the model's performance with the interaction term demonstrates that sometimes adding interaction terms to your model may enhance its importance. This example highlights how interaction terms can capture additional information that is not apparent from the main effects alone. In practice, considering interaction terms in regression models can lead to more accurate and insightful predictions.




