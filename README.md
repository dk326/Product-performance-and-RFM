# Product-performance-and-RFM

**About the project**
The project was done to answer a few business questions for an organisation which sells online news items. The data was provided by a real world organisation but is reffered with a hypothetical name. 

The main analysis was done to identify the purchase patterns of customers, performance of different product types and customer segmentation. 

Customer segmentation has been done by using the RFM model (recency, frequency and monetary values). Further, customers have been segmented into 5 quantiles (RFM Cells) based on their RFM value with 555 being the best and 111 lowest. 

**Questions**

**1. For each product, how many unique customers have made a purchase?*

<img width="542" alt="Screenshot 2024-10-10 at 2 12 50 PM" src="https://github.com/user-attachments/assets/774e3a10-e7c5-47db-b342-186444312f04">

<img width="634" alt="Screenshot 2024-10-10 at 2 13 06 PM" src="https://github.com/user-attachments/assets/4bb5a7a4-11b1-48fb-a9b7-bb20ffb68601">

- The unique customers have been identified by counting the disctinc IDs
- The results are grouped by product type and ordered in descending order by number of customers
   
**2. What is the best-selling product based on total sales?*

<img width="595" alt="Screenshot 2024-10-10 at 2 15 16 PM" src="https://github.com/user-attachments/assets/7d7a95b6-4fc4-4d18-9223-035de0f0310c">

<img width="615" alt="Screenshot 2024-10-10 at 2 15 29 PM" src="https://github.com/user-attachments/assets/12e3dcb0-e702-4054-a630-e566de0796b1">

- The products have been selected and the total amount paid is aggregated by using sum to identify profitability
- The final result is grouped by product and limited to 1 to only show the best selling product
  
**3. For each customer, calculate and list their RFM Value scores based on their transaction history?*

<img width="636" alt="Screenshot 2024-10-10 at 2 17 00 PM" src="https://github.com/user-attachments/assets/abba5299-c47a-4a1c-83c0-1ddb1f105752">

<img width="696" alt="Screenshot 2024-10-10 at 2 17 16 PM" src="https://github.com/user-attachments/assets/11870ad5-d22d-439f-9f13-e41b1c2c3f99">

- It is important to note that, in this dataset the product type of gold membership is an ongoing subscription. Therefore, if this membership is active, the fulfilment end date column is null. 
- Therefore, in order to get the frequency scores of this type, the null values have been replaced by current date
- Frequency is taken as the count of all disctict fulfilment end dates and the monetary is the sum of total paid. 
   
**4. Segment customers into five groups for each of the three key metrics: Recency,Frequency, and Monetary value based on their transaction history?*

<img width="647" alt="Screenshot 2024-10-10 at 2 18 01 PM" src="https://github.com/user-attachments/assets/315e4d16-0bb3-4cfa-9783-b963eecb0e14">

<img width="719" alt="Screenshot 2024-10-10 at 2 18 31 PM" src="https://github.com/user-attachments/assets/1807e6e9-fe58-4859-9d52-c498ebeaca30">

- This code uses to common table expressions (CTE). The first CTE is used to identify RFM scores of each id
- The second CTE selects the RFM scores by ID and creates 5 quantiles for each of Recency, Frequency and Monetary value and then combines these values ointo a single RFM cell value.
- The final Query is ordered by descending RFM cell value to identify the best customers first.

**Additional Segmentation*

<img width="695" alt="Screenshot 2024-10-10 at 3 47 28 PM" src="https://github.com/user-attachments/assets/a38995b2-7e6f-44bd-ab82-a9e48557b2fb">

<img width="709" alt="Screenshot 2024-10-10 at 3 47 53 PM" src="https://github.com/user-attachments/assets/8c95ebdc-613e-45a2-b618-2c14fc002410">

- By using two other CTEs customers can be further segmented based on RFM cell values. 
- Eventhough the customers have been grouped by the Ids here, they can be grouped by the rfm group if needed.

**Data Cleaning*

The dataset consisted of missing values. Based on the data dictionary, the null values of gold memberships were active subscriptions. Therefore, the cleaning has been done while keeping the active memberships. 

<img width="738" alt="Screenshot 2024-10-10 at 3 52 22 PM" src="https://github.com/user-attachments/assets/f19000b1-fd0a-4463-b2d3-5c3e04ba8142">


