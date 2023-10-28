# Global Superstore Sales
The project aims to create a Power BI dashboard to deliver decision-making insights to a stakeholder.

## Business Questions

The senior manager needs to access information about the business situation within international markets to develop a strategy for market expansion and make decisions on the selection of strategic products.

## Data Description

The dataset stores information on the sales of several products of the company worldwide. It includes three tables:
- The **Orders** table: Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Customer Name, Segment, City, State, Country, Postal Code, Market, Region, Product ID, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit, Shipping Cost, Order Priority.
- The **People** table: Person, Region.
- The **Returns** table: Returned, Order ID, Market.

## The Design Thinking Process

### Empathize
| **Detail** | **Answer** |
|---------------------------|---------------------------------------|
| **Stakeholders Challenge**       | Desire to expand into international markets, but lacking knowledge about: <br> - Which markets to expand. <br> - Which products are suitable for the strategic markets. |
| **Dashboard Goal**       | - Present the company's global business performance through key metrics such as revenue, profit, ROS... <br> - Identify potential markets and suitable products/product categories for those markets. |
| **Ask and Answer Questions**      | - Viewers: Senior Manager. <br> - Purpose: To gain insights into the company's business situation, identifying potential markets, and strategic product selection. <br> - Expectation: A comprehensive overview to determine potential markets and suitable products for those markets. |
| **Dataset Discovery**     | **1. Metric** <br> - Sales <br> - Quantity <br> - Discount <br> - Profit <br> - Shipping Cost <br><br> **2. Dimension** <br> The other columns |
| **Dataset Cleaning**     | - **Orders.PostalCode:** 81% missing values &rarr; Remove the column as it doesn't use for analysis. <br> - **Orders.OrderDate, Orders.ShipDate:** Convert data type to Date. <br> - **People.Region:** Typographical error &rarr; Replace 'AMEA' with 'EMEA'. <br> - **Return.Returned:** Replace "Yes" with True, convert data type to boolean. <br> - **Returns.Market:** 'United States' and 'US' are the same values &rarr; Replace 'United States' with 'US'. |

### Define Point Of View
| Detail              | Answer                                                                                          |
|---------------------|------------------------------------------------------------------------------------------------|
| **Top Down**        |**1. Market:** <br> - Currently, in which markets is the company operating? How have revenue and profit performed in each market over the past months/quarters/years? <br> - Is there any variation in business performance among these markets? <br> - Which market is experiencing strong growth and has the potential for expansion? <br> - Do consumer habits and cultural factors influence the development of that market? <br> **2. Product** <br> - How is the sales performance and return rate for each category, sub-category, and product? Are there any differences between them? <br> - Are there any seasonal products? <br> **3. Market + Product** <br> How can we identify strategic products for each market? |
| **Bottom Up**       |**1. Key Measures** <br> - Revenue <br> - Success revenue = Revenue - Returned revenue <br> - Profit <br> - Profit margin = Success Profit / Success Revenue <br> - Number of customers <br> - Number of new customers <br> - Number of old customers <br> - Number of orders <br> - Number of successful orders <br> - AOV (Average Order Value) = Total Sales / Total Orders <br> - Return rate = Number of returned orders / Number of orders <br> - Average discount rate <br><br> **2. Key Dimensions** <br> - Year, quarter, month <br> - Market <br> - Category, subcategory, product <br> - Segment |

### Ideate
| Detail              | Answer                                                                                          |
|---------------------|------------------------------------------------------------------------------------------------|
|**List down key metric**|**1. Layer 0 dimension:** <br> - Number of customers <br> - Number of orders <br> - AOV <br> - Revenue <br> - Profit <br> - Return rate <br> <br> **2. Layer 1 dimersion:** <br> - Revenue by time, by market, by category, subcategory <br> - Profit by time, by market, by category <br> - Number of orders by market, by category, by time <br> - AOV by market <br> - Avererage discount rate by market, by subcategory, by category <br><br> **3. Table:** <br> Number of orders by category and market |
|**Split dashboard layout**| The dashboard is divided into 3 parts: <br> - Overview <br> - Market <br> - Product |

### Prototype and Review

The section is shown in the dashboard.

## Visualization

**Overview**

<img width="593" alt="Page 1 - Overview" src="https://github.com/thanhtruchhh/Global_Superstore_Sales/assets/145547282/65ff388d-9a37-4138-bf4d-1052c802217d">


**Market**

<img width="592" alt="Page 2 - Market" src="https://github.com/thanhtruchhh/Global_Superstore_Sales/assets/145547282/3873a86c-7abc-4a32-8000-e329a1701e47">


**Product**

<img width="593" alt="Page 3 - Product" src="https://github.com/thanhtruchhh/Global_Superstore_Sales/assets/145547282/c264dd43-6980-4ebd-bdeb-2ce56f435fe8">

## Insights and Recommendations

### Insights

**Overview**

- The company has maintained stable revenue growth year after year, with a fluctuating profit margin of around 11-12%.
- Quarter 4 is the peak shopping season in the year. 
- Popular customers are Consumer and Corporate (~80%). 
- The number of purchasing customers has been steadily increasing over the years. However, most of them are repeat customers, and there are very few new customers. Since August 2014, there have been no new customer engagements. 

**Market**

- APAC and EU are the two most promising markets, accounting for about 50% of the total market share across 7 markets. These markets have a stable customer base, high customer spending, and a profit margin of around 12%. 
- In Canada, despite having the highest profit margin at 26.62%, it holds an insignificant market share. The reason for this high profit margin might be the absence of discounts.
- Number of orders in Africa and EMEA is still relatively weak *(≤2500 orders)*, despite a high average discount rate. It appears that the discount strategy may not be the appropriate approach for these two markets.

**Product**

- Office supplies are the best-selling subcategory, although its profit percentage is lower than technology products.
- Furniture generates relatively good revenue, but the profit margin is very low, and in the case of the Table subcategory, it may even be negative. The reason for this could be the excessively high discount costs.

### Recommendations

**Market**

- The company should consider for expanding APAC and EU market.
- Africa accounts for a small market share, but it boasts a good profit margin *(11.34%)*, making it a potential market to expand.
- The company may consider suspending investments in the Canadian and EMEA markets.

**Strategies**

- Segment to be targeted is Consumer + Corporate.
- The company needs to implement additional strategies to attract new customers.
- The company should organize promotional programs, discounts, and special offers to stimulate shopping during the holiday season *(in quarter 4)*: Thanksgiving, Black Friday, Cyber Monday, and Christmas.
- For Africa, the company can adjust its sales and marketing strategy instead of solely focusing on discounts. 

**Product + Market**

- The company should contemplate discontinuing the import and sale of products in the Table subcategory.
- The company should diversify its product range within the Technology category, particularly focusing on products in the Accessories, Copier, and Phone subcategories as they are popular and have a high profit margin.
- APAC: Main categories are Technologies, Office Supplies, and Furniture. Main subcategories are Binders, Chairs, Copiers and Phones.
- EU and Africa: Main categories are Technologies and Office Supplies. Main subcategories are Art and Binders, Storage and Phones.
