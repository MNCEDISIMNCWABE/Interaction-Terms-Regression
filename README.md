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

Upond building the model the following results were observed: 

- The model without the interaction term explains about 80% (test R-squared) of the variance in the ```time_spent```, with a mean squared error (MSE) of 2.11. This means that, on average, the predictions of ```time_spent``` are off by about 2.11 squared units. While this model is fairly accurate, there's room for improvement.
- Additionally, the plot visually confirms that while the model performs reasonably well, there is significant room for improvement, particularly in capturing higher values of time_spent.

<img width="664" alt="image" src="https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/b9fc1b5a-d27d-4039-b903-f4e5438e7a89">



![image](https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/13ccbb7d-ed3b-405b-93e4-a7cba3b21952)


#### Model with interaction term

