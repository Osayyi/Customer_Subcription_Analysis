# Customer_Subcription_Analysis
Customer Data dataset contains comprehensive records of customers subscription details.

### Table of Content
[Project Overview](#project-overview)

[Key Fields](#key-fields)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data Cleaning](#data-cleaning)

[Data Analysis](#data-analysis)

[Findings and Insights](#findings-and-insights)

[Conclusion](#conclusion)

[Future Recommendations](#future-recommendations)



### Project Overview:
---
*Objective*:
The Customer Data dataset contains records of customers associated with a subscription-based service. It provides insights into customer demographics, subscription details, and revenue generated per customer, all essential for understanding customer preferences and behavior.

### Key Fields:
---
The key fields includes the following features related to customer data:
 - CustomerID: A unique identifier for each customer, used to track individual subscription data.
 - CustomerName: Customer unique Identity.
 - Region: Customer’s location or region.
 - SubscriptionType: The type of subscription plan chosen by the customer.
 - SubscriptionStart: Date when the subscription began.
 - SubscriptionEnd: Date when the subscription ended.
 - Canceled: Shows whether a subscription is currently active, or canceled.
 - Revenue: Total revenue generated from the customer’s subscription.
 - Duration: How long each subcription lasted. Calculated as =YEARFRAC(E2,F2)

### Data Sources
---
This data set is a Capstone Dataset and was gotten from The Incubator Hub (LITA) as a task for my final Project.

### Tools Used
---
- Microsoft Excel [Download Here](https://www.microsoft.com)
   1. For Data Cleaning
   2. Analysis
      
- SQL - Structured Query Language
   1. for Quring of Data
  
- PowerBi [Download Here](https://www.PowerBi.com)
    1. for Data Visualization

### Data Cleaning
 - Removing Duplicates: Checked for duplicate rows to ensure each transaction is unique. There was no duplicate rows.
 - Standardizing Dates: Reformatted Subscription Start Date and End Date to a consistent date format.
 - Filtering Relevant Records: Focused on Active or Recently Canceled subscriptions to understand current customer behavior.
 - Handling Missing Values: There was no missing values.

### Data Analysis
 - Excel Analysis

   - Pivot Tables to find:
 1. Subscription Patterns
 2. Average subscription duration.
 3. Most popular subscription type.

#### Subcription Patterns Analysis
I used pivot table to analyze the subcription types to find out which subcription types are the most popular and least popular.

**Basic** is the most popular subscription type and **Premium** is the least.

![Screenshot (16)](https://github.com/user-attachments/assets/4ba44695-900a-4813-b26a-2589918f4bad)


#### Average Subcription Duration
I created another column called Duration and calculated the duration of the Subcription using the SubcriptionStart and SubcriptionEnd. 

The duration of subcription for every customer in the dataset lasted for about a 1year, bringing the **Avearge subcription duration to 1**

![Screenshot (17)](https://github.com/user-attachments/assets/bc00946c-9b74-41e4-8108-3556e9252717)


#### Most Popular Subcription Type
Using the pivot table created, I identified the most popular subcription type based on the customer counts in each category.

**Basic** with 3,553,325 is the most popular subcription type.

|Subcription Patterns|Sum of CustomerID|
|--------------------|-----------------|
|Basic|3,553.325|
|Premium|1,773,724|
|Standard|1,785,348|
|Grand Total|7,112,397|

### Customer Growth by Region
I analyzed the customer growth across different regions to identify which region have the most customers. The **East** has the most customers.

*Insights:*
 - Annual subcriptions are more popular.
 - Basic Subcription is the most poupular subcription type, probably due to the cost of the subcription.
 - The analysis shows that the East followed by the West haa the highest number of customers which shows that these regions have a strong market need for the subcription service.

 
#### SQL Analysis
```
SELECT * FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data]
```

*Insights*
This query provides the customer count for each region, useful for regional analysis.
```
---- Total Number of Customers by Region ----
SELECT Region, COUNT(DISTINCT CustomerID) AS TotalNumberofCustomers
FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data]
GROUP BY Region;
```

*Insights*
Finds the most common subscription type, giving insights into customer preferences.
```
---- Most Popular Subscription Type by Customer Count ----
SELECT SubscriptionType, COUNT(CustomerID) AS CustomerCount
FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data]
GROUP BY SubscriptionType
ORDER BY 1 DESC
```

*Insights*
 Identifies customers who canceled within six months, which could indicate churn risks.
 No Customer canceled their subcription within six months
```
---- Customers Who Canceled Within 6 Months ----
SELECT CustomerID, SubscriptionStart, SubscriptionEnd
FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data]
WHERE DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) <= 6;
```

*Insights*
Calculates the average duration of subscriptions, which helps in understanding customer retention.
The average subscription duration lasted for 12 Months.
```
---- Average Subscription Duration ----
SELECT AVG(DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd)) AS AverageSubscriptionDuration
FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data];
```

*Insights*
Finds loyal customers with subscriptions longer than a year.
No customer has a subcription plan of more than a year (12 Months)
```
---- Customers with Subscriptions Longer than 12 Months ----
SELECT CustomerID
FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data]
WHERE DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) > 12;
```

*Insights*
Aggregates revenue by subscription type, which is valuable for revenue distribution analysis.
```
---- Total Revenue by Subscription Type ----
SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue
FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data]
GROUP BY SubscriptionType;
```

*Insights*
Identifies regions with high cancellation rates, pointing to possible areas for improvement.
West, South and North has the highest cancellation rates.
```
---- Top 3 Regions by Subscription Cancellations ----
SELECT TOP 3 Region, COUNT(*) AS SubscriptionCancellations
FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data]
WHERE Canceled = 1
GROUP BY Region
ORDER BY 1 DESC
```

*Insights*
Gives a quick overview of active vs. canceled subscriptions, providing insights into retention.
0 representing the number of canceled subscriptions sums up to 18612, while
1 which represents the number of active subcriptions sum up to 15175.
```
---- Total Number of Active and Canceled Subscriptions ----
SELECT Canceled, COUNT(*) AS Count
FROM [dbo].[LITA Capstone Dataset Osayi favour Customer Data]
GROUP BY Canceled;
```

#### Power BI Dashboard

*Insights*

### Findings and Insights

### Conclusion

### Future Recommendations
1. Introduce a loyalty program for long-term customers.
2. Expand popular product categories in high-performing regions.
