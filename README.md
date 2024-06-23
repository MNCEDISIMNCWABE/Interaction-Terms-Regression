## Understanding Interaction Terms in Regression: A Practical Example

#### Overview
In regression modeling, interaction terms are used to capture the combined effect of two or more variables on the target variable. This can be particularly useful in scenarios where the relationship between the variables and the target variable is not simply additive. In this example, we explore the concept of interaction terms using a practical example: predicting the time spent by users on an ecommerce platform based on their activity.

#### Example: User Activity and Time Spent
Let's first generated a synthetic dataset to simulate user activity on an ecommerce platform. The dataset includes:
- ``added_in_cart`` : Whether a user added items to cart or not (1 for adding to cart or 0 for not adding to cart).
- ```purchased``` : Whether a user made a purchase or not (1 for making a purchase or 0 for not making a purchase).
- ```time_spent``` : The total time a user spent on an ecommerce platfotm (continuous). We are trying to predict this feature, i.e, how long a user will spend on an ecommerce platform based on whether they add items to cart and making a purchase.

Data snapshot:
<img width="311" alt="image" src="https://github.com/MNCEDISIMNCWABE/Interaction-Terms/assets/67195600/363df886-3bc6-45e5-86d2-449cbefbce47">
