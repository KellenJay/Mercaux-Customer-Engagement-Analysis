# Mercaux-Customer-Engagement-Analysis

## Overview

This project investigates the impact of customer engagement through the Mercaux tool on purchasing behavior. Using customer communication data and purchase history, we analyze how different levels of customer interaction (via outbound messages) influence purchasing decisions. The analysis includes splitting customers into test and control groups, comparing purchasing behaviors, and performing linear regression to explore correlations between message frequency and purchase behavior.

## Data

The data used in this analysis includes two main sources:

1. **Transaction Data:**
   - Contains information on customer purchases, including purchase amounts and transaction details.
   - Key columns: `phone_encoded`, `amount_including_vat`, `order_date`, `return_date`, `transaction_id_encoded`

2. **Communication Data:**
   - Contains data on customer interactions with messages, such as the number of messages sent and whether the customer responded.
   - Key columns: `phone_encoded`, `number_of_messages`, `has_response`, `date_of_communication`

## Key Insights

- **Customer Purchasing Behavior & Message Engagement:** We observed that while there was a weak correlation between the number of messages sent and the time to purchase, customers who received more messages tended to purchase slightly faster. However, the relationship is not strong.
  
- **Test vs Control Groups:** Customers who responded to messages (test group) and those who did not (control group) were compared. Customers in the control group had a slightly higher average purchase amount, but the overall spending behavior showed significant variability within both groups.

- **Model Results:** A linear regression model showed weak predictive power, despite it's model accuracy score of 71.48%, indicating that the number of messages and customer responses alone have minimal influence on purchase amounts. Other factors, such as product type or customer-specific characteristics, are likely more important.

## Methodology

1. **Data Preprocessing:**
   - Cleaned and merged transaction and communication data based on customer identifiers.
   - Handled missing data and outliers, especially in the number of messages and purchase amounts.

2. **Group Segmentation:**
   - Divided customers into control and test groups based on whether they responded to outbound messages.
   - Performed summary analysis on purchase amounts and time to purchase for both groups.

3. **Statistical Analysis:**
   - Compared the average purchase amounts and time to purchase for test vs control groups.
   - Applied linear regression to assess the relationship between customer engagement (messages and responses) and purchase behavior.

4. **Visualizations:**
   - Generated box plots and histograms to visualize the distribution of purchase amounts and time to purchase across the control and test groups.
   - Used scatter plots to explore the relationship between the number of messages and time to purchase.

## Results

- **Control Group (No Response):** Average purchase amount = $65.96
- **Test Group (Responded to Message):** Average purchase amount = $60.79
- **Model Accuracy Acore:** 71.48%
- **Key Coefficients:** 
  - Number of Messages: -0.0426 (weak negative effect on purchase amount)
  - Has Response: -2.1093 (small negative effect on purchase amount)

## Conclusion

The analysis suggests that customer engagement through outbound messages has a weak effect on purchasing behavior. Despite the slight trend towards faster purchases with more messages, the model's predictive power remains low, indicating that other factors beyond message volume and response play a more significant role in influencing purchases.

## Further Work

- A/B testing could be performed to better measure the effects of different types of messages on purchase behavior.
- Additional customer-specific features (e.g., demographics, browsing history) could be incorporated into future models to improve prediction accuracy.

## Installation and Usage

To run this analysis on your own machine, you'll need Python 3.x along with the following libraries:
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

Install the required libraries using pip:
