create database varshitha
use varshitha
select * from Additional
select * from customers
select * from data
--union
select Date,Sales_Rep,Customer_Code,Sales,profit,Region into Gunnu_data from Additional
union all
select * from data
select *from Gunnu_data
---
select Gunnu_data.Date,
Gunnu_data.Sales_Rep,
Gunnu_data.Customer_Code,
Gunnu_data.Sales,
Gunnu_data.profit,
Gunnu_data.Region,
Customers.Customer,
Customers.Association_Date
into complete_data
from Gunnu_data
inner join Customers
on
Gunnu_data.Customer_Code=Customers.Customer_Code
select *from complete_data
--Find sum,min,max,avg sales and Profit
--Sales
select sum(sales) as sum_sales from complete_data
select Avg(sales) as avg_sales from complete_data
select min(sales) as min_sales from complete_data
select max(sales) as max_sales from complete_data
--Profit
select sum(Profit) as sum_Profit from  complete_data
select Avg(Profit) as avg_Profit  from complete_data
select min(Profit) as min_Profit  from complete_data
select max(Profit) as max_Profit  from complete_data
--Find any two sales_Rep in Region
--make a sample data of any two sales_rep in region,witha customer find min,max
--sales
--Find any two sales_Rep in Region
--Find any two sales_Rep in Region
select  Sales_rep,customer_Code,Profit,Region,Customer,Association_Date, 
max(sales) as max_sales,max(Profit) as max_Profit from complete_data
where Sales_Rep in ('Jaspreet','Veronica') and region in ('East')
group by Sales_rep,customer_Code,Profit,Region,Customer,Association_Date
---
select Sales_rep,Region,Customer,
max(Sales) as max_sales,
max(Profit) as max_Profit 
into varshi_data from complete_data
where Sales_Rep in ('jaspreet','Veronica')
group by Sales_rep,customer,Region 
---
--find sales, profit of sales_rep in a region. 
select Sales_rep,Region,Sales,Profit 
into Sample_data from complete_data
group by Sales_rep,Region,Sales,Profit 
--
select * from Sample_data
--find height sales in a Region
select max(Sales) as Highest_Sales,Region,Customer
into Max_Sales from complete_data
group by Region,customer
select*from Max_Sales
--
select * from Max_sales
select * from varshi_data
select * from complete_data
select * from Sample_data


---
--Project :use the data sets "Additional. Csv", "Data. Csv", "Customers. Csv". *Merge all the data using joines and unions.--comp_pro
---find height sales in a Region--Max_Sales
--find  sales, profit of sales_rep in a region. --Sample_data1
--make a sample data of any two sales_rep in region, with a customer find min, max, avg, sum of sales and profit .--sample_data





