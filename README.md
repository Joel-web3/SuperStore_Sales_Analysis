# SuperStore Sales Analysis

![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Dashboard%201%20(1).png)

[**Link to Dashboard in Tableau Public**](https://public.tableau.com/app/profile/joel.obafemi/viz/SalesDashboard_16990059644250/Dashboard1?publish=yes)

## Introduction
This project provides a comprehensive view of a SuperStore's sales metrics for an observed period from December 2018 to June 2020. 
The data is meticulously categorized into various segments such as sales by month, region, state, payment method, and product category. The report presents a detailed analysis of this data, shedding light on sales patterns, regional performance, and product preferences.

## Problem Statement 
To identify potential growth areas, sales patterns, and areas of concern in this SuperStore's sales data. Analyzing these patterns will assist in formulating strategies to maximize profit, optimize sales channels, and cater to regional preferences.

## Chart Requirements

- **Sales By Month**: Provides a monthly sales trend showcasing peaks and troughs in revenue.

- **Sales & Profit By State**: Depicts state-wise distribution of sales and profit, enabling geographic insights.

- **Sales By Ship Mode**: Breakdown of sales based on shipping modes to understand customer preferences.

- **Sales By Payment Method**: Highlights the preferred payment modes by customers.

- **Sales By Category and Sub-Category**: Showcases which products are more popular and profitable.

- **Sales By Region**: Displays sales distribution across different regions.

- **Sales By Segment**: Splits sales data into three segments - Home Office, Consumer, and Corporate.

## SQL Queries

1. **Total Sales:**

    SELECT SUM(Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales.png)

2. **Total Profit:**

    SELECT SUM(Profit) AS Total_Profit

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Profit.png)

3. **Total Orders:**

    SELECT SUM(Quantity) AS Total_Orders

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Orders.png)

4. **Total Sales By Month & Year:**

    SELECT DATENAME (MONTH, Order_Date) AS Month_Name, DATENAME (YEAR, Order_Date) AS Year_Name,

    SUM (Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY DATENAME(MONTH, Order_Date),  DATENAME (YEAR, Order_Date)

    ORDER BY Year_Name

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales%20By%20Month%20%26%20Year.png)

5. **Total Profit By Month & Year:**

    SELECT DATENAME (MONTH, Order_Date) AS Month_Name, DATENAME (YEAR, Order_Date) AS Year_Name,

    SUM (Profit) AS Total_Profit

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY DATENAME(MONTH, Order_Date),  DATENAME (YEAR, Order_Date)

    ORDER BY Year_Name

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Profit%20By%20Month.png)

6. **Total Sales By State:**

    SELECT (State) AS State_Name, 

    SUM (Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY State

    ORDER BY Total_Sales DESC

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales%20By%20State.png)

7. **Total Profit By State:**

    SELECT (State) AS State_Name, 

    SUM (Profit) AS Total_Profit

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY State

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Profit%20By%20State.png)

8. **Total Sales By Ship Mode:**

    SELECT (Ship_Mode) AS Ship_Mode, 

    SUM (Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY Ship_Mode

    ORDER BY Total_Sales DESC

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales%20By%20Ship%20Mode.png)

9. **Total Sales By Category:**

    SELECT (Category) AS Category, 

    SUM (Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY Category

    ORDER BY Total_Sales DESC

   ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales%20By%20Category.png)

10. **Total Sales By Sub-Category:**

    SELECT (Sub_Category) AS Sub_Category, 

    SUM (Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY Sub_Category

    ORDER BY Total_Sales DESC

    ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales%20By%20Sub-Category.png)

11. **Total Sales By Payment Mode:**

    SELECT (Payment_Mode) AS Payment_Mode, 

    SUM (Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY Payment_Mode

    ORDER BY Total_Sales DESC

    ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales%20By%20Payment%20Mode.png)

12. **Total Sales By Region:**

    SELECT (Region) AS Region, 

    SUM (Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY Region

    ORDER BY Total_Sales DESC

    ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales%20By%20Region.png)

13. **Total Sales By Customer Segment:**

    SELECT (Segment) AS Customer_Segment, 

    SUM (Sales) AS Total_Sales

    FROM [SuperStore Sales DataSet.xlsx - Sheet1]

    GROUP BY Segment

    ORDER BY Total_Sales DESC

    ![](https://github.com/Joel-web3/SuperStore_Sales_Analysis/blob/main/Total%20Sales%20By%20Customer%20Segment.png)

## Key Insights
- **Sales Trend**: Sales observed a noticeable peak around June 2019, followed by a dip and a subsequent recovery around December 2019.
  
- **State Analysis**: Certain states like California and Texas have higher sales and profits compared to other states.

- **Ship Mode Preference**: The majority of customers prefer the 'Standard' shipping mode, followed by 'Second Class'.
  
- **Payment Modes**: A significant chunk (43%) of customers prefer Cash On Delivery (COD) followed by online payments (35%).

- **Product Analysis**: Under categories, 'Office Supplies' is the most sold category, while in sub-categories, 'Phones' and 'Chairs' have the highest sales.

- **Regional Sales**: The 'West' and 'Central' regions account for the majority of sales with 33% and 22% respectively.

- **Segment Analysis**: The 'Consumer' segment dominates sales with a 48% share.

# Recommendations

- **Focus on High-Performance States**: Invest more in states like California and Texas where sales and profits are high.

- **Shipping Mode Optimization**: Given the popularity of 'Standard' and 'Second Class' shipping, ensure efficient logistics support for these modes.

- **Payment Flexibility**: Since a considerable number of customers prefer COD, it would be beneficial to streamline the COD process. However, considering the rise in digital payments, promotional offers can be introduced to encourage more online payments.

- **Product Strategy**: Prioritize stock for 'Phones' and 'Chairs' given their high sales volume. Also, marketing campaigns can focus on popular categories like 'Office Supplies'.

- **Regional Targeting**: Increase marketing efforts in the 'West' and 'Central' regions while devising strategies to tap into the potential of the 'East' and 'South' regions.

- **Engage More Consumers**: Given the high sales in the 'Consumer' segment, tailor promotional activities and discounts targeting this group.
