                                                       Task 6
Step 1: online_sales (orders table with order_date, amount, product_id)
	create table online_sales(order_id int primary key,order_date date not null,amount decimal(10,2),product_id int);
	desc online_sales;
	INSERT INTO online_sales VALUES(1,'2025-04-01', 199.99, 101),(2,'2025-04-02', 49.50, 102),(3,'2025-04-03', 89.00, 103),(4,'2025-04-03', 25.00, 101),(5,'2025-04-04', 300.00, 104),(6,'2025-04-04', 75.00, 102);
	Select * from online_sales
 

 

Step2: Use EXTRACT(MONTH FROM order_date) for month
	SELECT  order_id,order_date,EXTRACT(MONTH FROM order_date) AS order_month,amount,product_id FROM online_sales;


 
Step 3: 
	GROUP BY year/month. 
	Use SUM() for revenue.
	COUNT(DISTINCT order_id) for volume. 
	Use ORDER BY for sorting

SELECT EXTRACT(YEAR FROM order_date) AS order_year,EXTRACT(MONTH FROM order_date) AS order_month,SUM(amount) AS revenue,COUNT(DISTINCT order_id) AS volume FROM online_sales GROUP BY EXTRACT(YEAR FROM order_date),EXTRACT(MONTH FROM order_date) ORDER BY order_year,order_month;
 
