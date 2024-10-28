# Marketing-Customer-Segmentation-Analysis_Python
## I.Introduction
### Why RFM?
- RFM (Recency, Frequency, Monetary) analysis is a marketing model using customer segmentation based on their transaction history.
- This model could be very useful, especially for small and medium-sized enterprises (SMEs) with limited marketing resources, helping them focus on the potentially right customer segments to increase ROI, reduce churn, reduce cost, improve customer relationships, and a lot more.

### How?
- In RFM analysis, customers are scored based on three factors (Recency - how recently, Frequency - how often, Monetary - how much), then labelled based on the combination of RFM scores.
### Business Questions:
- Customer Segmentation: How can we effectively segment our customer base to identify loyal customers, potential customers, and those at risk of churn?
- RFM Analysis: What insights can we derive from the RFM (Recency, Frequency, Monetary) model to tailor marketing campaigns for each customer segment?
## II. Explore Data
### 1. Prepare the data set suitable for the RFM model
- Customer ID: Customer identification.
- Transaction Date: Transaction date.
- Transaction Amount: Transaction amount.
### 2. Exploratory Data Analysis (EDA)
- Remove invalid or missing records.
- Ensure that the date format is correct.
- Aggregate the data by the customer to get the necessary information for RFM.
#### Check missing values
<img width="908" alt="Screenshot 2024-10-28 at 12 02 48" src="https://github.com/user-attachments/assets/53d37fb2-3e3a-4f5e-9321-870abd56e0bf">
<img width="906" alt="Screenshot 2024-10-28 at 12 03 22" src="https://github.com/user-attachments/assets/7b7438f8-eb7d-4f2c-bb98-0a9844e3ea2c">

--> 
- Description có giá trị Null
- Customer ID có null
- Customer ID sai type
- Unit Price < 0
- Quantity < 0

#### Clean Data
-->
- Xóa các order bị cancel
- Xóa các Customer ID bị null
- Đổi type cho cột Customer id
  <img width="910" alt="Screenshot 2024-10-28 at 12 04 51" src="https://github.com/user-attachments/assets/e63b0950-d58b-4804-8af9-d07dac9366f3">

<img width="904" alt="Screenshot 2024-10-28 at 12 06 13" src="https://github.com/user-attachments/assets/e7f8fcce-fe39-4c79-8cf8-fc3f3949618c">

## III. RFM Analysis
### Determine and Calculate R, F, M Scores for Each Customer
- **R (Recency)**: The number of days since the last transaction to the reference date (December 31, 2011).
  - Formula: R = 31/12/2011 - Last Transaction Date
- **F (Frequency)**: The total number of transactions made by the customer over a specified period.
  - Formula: F = Count of Transactions per Customer
- **M (Monetary)**: The total amount spent by the customer.
  - Formula: M = Sum of Transaction Amount per Customer
### Calculate Corresponding Scores on a Scale from 1 to 5
- **Quintile Method:**
  - **R**: Divide customers into 5 groups based on their R scores, from the most recent customers (lowest R) to the oldest customers (highest R).
  - **F**: Similarly, divide customers into 5 groups based on their frequency of transactions.
  - **M**: Divide customers into 5 groups based on their total monetary value.
- **Corresponding Scores:**
  - Group 1: Score 5 (best)
  - Group 2: Score 4
  - Group 3: Score 3
  - Group 4: Score 2
  - Group 5: Score 1 (worst)
### Group Customers Based on Classification Table
- **Create a Classification Table:** Create a table containing Customer IDs along with their R, F, and M scores.
- **Group Customers:** Use R, F, and M scores to categorize customers into segments such as:
  - Loyal Customers: R = 5, F = 5, M = 5
  - At-Risk Customers: R = 5, F = 1-2, M = 1-2
  - New Customers: R = 5, F = 1, M = 1

**Recommendation:** In a retail model, all three R, F, and M metrics are important, but it may be beneficial to prioritize
  
  **F (Frequency):** This metric indicates customer loyalty. Customers who make frequent purchases are likely to become loyal customers, so focusing on increasing purchase frequency can lead to more stable revenue.
  
## IV. Visualize the Number of Segments with Dimensions
<img width="946" alt="Screenshot 2024-10-20 at 14 45 31" src="https://github.com/user-attachments/assets/329ba60b-9aaa-48bd-a2e2-df77143f23e0">

----------------------------------------------
<img width="945" alt="Screenshot 2024-10-20 at 14 45 57" src="https://github.com/user-attachments/assets/b6a1dbd9-3f4a-4101-9a2d-1ebff50d0417">

## V. Insights
<img width="695" alt="Screenshot 2024-10-20 at 14 48 14" src="https://github.com/user-attachments/assets/cf2ce5bf-176b-4c02-aad3-be1444b50ca2">

