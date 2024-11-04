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

#### Average Subcription Duration
I created another column called Duration and calculated the duration of the Subcription using the SubcriptionStart and SubcriptionEnd. 

The duration of subcription for every customer in the dataset lasted for about a 1year, bringing the **Avearge subcription duration to 1**

#### Most Popular Subcription Type
Using the pivot table created, I identified the most popular subcription type based on the customer counts in each category.

**Basic** with 3,553,325 is the most popular subcription type.

|Subcription Patterns|Sum of CustomerID|
|--------------------|-----------------|
|Basic|3,553.325|
|Premium|1,773,724|
|Standard|1,785,348|
|Grand Total|7,112,397|

*Insights:*

 - SQL Analysis

*Insights*

 - Power BI Dashboard

*Insights*

### Findings and Insights

### Conclusion

### Future Recommendations
1. Introduce a loyalty program for long-term customers.
2. Expand popular product categories in high-performing regions.
