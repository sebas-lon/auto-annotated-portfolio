---
type: ProjectLayout
title: SALES FROM ADVENTURE WORKS DATABASE
colors: colors-a
date: '2023-12-03'
client: ''
description: >-
  In this project, I will explore the Adventure Works database from Microsoft,
  focusing on sales, customer, and product data analysis.
featuredImage:
  type: ImageBlock
  url: /images/awl-222.png
  altText: SALES FROM ADVENTURE WORKS DATABASE
  caption: SALES FROM ADVENTURE WORKS DATABASE
media:
  type: ImageBlock
  url: /images/awl-222.png
  altText: Project image
---
#### Get the data

I get the latest data from Microsoft, then start working with SQL server management and uploaded the files to Power BI

#### Data that I'll use

I start the exploratory queries to find what type of data I have




```
-- Cleansed DIM_Date Table --
--Calendar
SELECT
[DateKey],
[FullDateAlternateKey] AS Date,
[EnglishDayNameOfWeek] AS Day,
[EnglishMonthName] AS Month,
Left([EnglishMonthName], 3) AS MonthShort,[MonthNumberOfYear] AS MonthNo,
[CalendarQuarter] AS Quarter,
[CalendarYear] AS Year
FROM
[AdventureWorksDW2019].[dbo].[DimDate]
WHERE
CalendarYear >= 2019

```

```
--- Customers
```

```
SELECT
c.customerkey AS CustomerKey,
c.firstname AS [First Name],
c.lastname AS [Last Name],
c.firstname + ' ' + lastname AS [Full Name],
CASE c.gender WHEN 'M' THEN 'Male' WHEN 'F' THEN 'Female' END AS Gender,
c.datefirstpurchase AS DateFirstPurchase,
g.city AS [Customer City] -- Joined in Customer City from Geography Table
FROM
[AdventureWorksDW2019].[dbo].[DimCustomer] as c
LEFT JOIN AdventureWorksDW2019.dbo.dimgeography AS g ON g.geographykey = c.geographykey
ORDER BY
CustomerKey ASC

```

```
-- Products
```

```
SELECT
p.[ProductKey],
p.[ProductAlternateKey] AS ProductItemCode,
p.[EnglishProductName] AS [Product Name],
ps.EnglishProductSubcategoryName AS [Sub Category],
pc.EnglishProductCategoryName AS [Product Category],
p.[Color] AS [Product Color],
p.[Size] AS [Product Size],
p.[ProductLine] AS [Product Line],
p.[ModelName] AS [Product Model Name],
p.[EnglishDescription] AS [Product Description],
ISNULL (p.Status, 'Outdated') AS [Product Status]
FROM
[AdventureWorksDW2019].[dbo].[DimProduct] as p
LEFT JOIN AdventureWorksDW2019.dbo.DimProductSubcategory AS ps ON ps.ProductSubcategoryKey = p.ProductSubcategoryKey
LEFT JOIN AdventureWorksDW2019.dbo.DimProductCategory AS pc ON ps.ProductCategoryKey = pc.ProductCategoryKey
order by
p.ProductKey asc

```

```
--Intertnet Sales
```

```
SELECT
[ProductKey],
[OrderDateKey],
[DueDateKey],
[ShipDateKey],
[CustomerKey],
[SalesOrderNumber],
[SalesAmount]
FROM
[AdventureWorksDW2019].[dbo].[FactInternetSales]
WHERE
LEFT (OrderDateKey, 4) >= YEAR(GETDATE()) -3
ORDER BY
OrderDateKey ASC
```





<iframe title="Report Section" width="800" height="486" src="https://app.powerbi.com/view?r=eyJrIjoiZDM4MmViM2ItMTM4MS00YmEzLWI4N2EtZjc3YmQ4YzEwNjM3IiwidCI6ImU5OTQwNzJiLTUyM2UtNGJmZS04NmUyLTQ0MmM1ZTEwYjI0NCIsImMiOjR9" frameborder="0" allowfullscreen></iframe>

## INFERENCES AND CONCLUSION

*   The sales went up 2.715 M more than expected over the first 3 years

*   Around 96% of the sales were bikes

*   The month of June is when the sales sky up

*   The best customer is Jordan Turner with around 16000

*   The bike with more sales is the Mountain-200 Black, 42

*   The majority of sales are in the west of the states, Uk, german, France, and Australia

RECOMMENDATIONS

\*Increase sales of accessories and clothing, since after a year of introducing these two segments it had a share of sales of around 5%





