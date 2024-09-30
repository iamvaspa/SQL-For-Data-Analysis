
Here are some questions and explanations based on the SQL queries and table structure provided:

1. What does the CREATE TABLE statement do?
Question: What is the purpose of the CREATE TABLE statement in SQL?
Explanation: The CREATE TABLE statement defines a new table in the database, including the table name (orders_data) and its columns (order_id, order_date, etc.), along with their data types (nvarchar, date, etc.) and whether they can contain NULL values.

2. What data types are used in the orders_data table?
Question: What are the different data types used for the columns in the orders_data table, and what do they represent?
Explanation: The table uses nvarchar, date, and float data types. nvarchar allows variable-length string data, typically used for textual information like order_id or city. date is used to store dates (e.g., order_date, ship_date), and float is for numeric data with decimal points (e.g., sales, profit).

3. What is the purpose of the SELECT * FROM orders_data query?
Question: What does the SELECT * FROM orders_data SQL query return?
Explanation: The SELECT * statement retrieves all columns and rows from the orders_data table, displaying the entire dataset. This is a commonly used command to view all records in a table.

4. How does the INSERT INTO statement work?
Question: How does the INSERT INTO statement function in the context of SQL?
Explanation: The INSERT INTO statement adds new rows to the orders_data table. In this example, it inserts multiple values such as order_id, order_date, customer_name, etc. This allows you to add records into an existing table.

5. What does the NULL keyword indicate in the CREATE TABLE statement?
Question: What is the significance of the NULL keyword in the column definitions of a table?
Explanation: NULL means that the column can contain NULL values, which indicates the absence of a value. For example, if ship_date is NULL, it means that a shipment date has not been provided for that order.

6. How are primary keys used, and is there a primary key in this table?
Question: What is a primary key in SQL, and does the orders_data table have one?
Explanation: A primary key uniquely identifies each record in a table. In the given CREATE TABLE statement, no primary key is explicitly defined. If order_id is meant to be unique, a primary key constraint could be applied to it.

7. Why might we use nvarchar instead of varchar?
Question: What is the difference between nvarchar and varchar, and why might nvarchar be chosen for this table?
Explanation: nvarchar supports Unicode, meaning it can store a broader range of characters (including multilingual text) compared to varchar, which is for non-Unicode characters. It is useful for applications where non-English characters may appear (e.g., international orders).

8. What would happen if you tried to insert a record with missing columns?
Question: What happens if a record is inserted with fewer values than the number of columns in the table?
Explanation: If a value is missing for a column that allows NULL, SQL will insert NULL into that column. However, if a column does not allow NULL and no value is provided, it will result in an error unless a default value is specified.

9. How can you query for orders with a specific region?
Question: How would you write an SQL query to retrieve all orders where the region is 'South'?
Explanation: You can use a WHERE clause to filter the results. For example:
	SELECT * FROM orders_data WHERE region = 'South';
This retrieves all records where the region column has the value 'South'.

10. How can you calculate the total sales in the orders_data table?
Question: How would you write a query to calculate the total sales in the orders_data table?
Explanation: You can use the SUM() function to aggregate the sales values. The query would look like this:
	SELECT SUM(sales) FROM orders_data;
This returns the sum of all sales in the table.

11. SQL code to create the orders_data table
	CREATE TABLE orders_data (
    order_id VARCHAR(50),
    order_date DATE,
    ship_date DATE,
    customer_name VARCHAR(100),
    region VARCHAR(50),
    city VARCHAR(100),
    category VARCHAR(50),
    product_id VARCHAR(50),
    sales DECIMAL(10, 2),
    quantity INT,
    profit DECIMAL(10, 4)
);

12. INSERT The RECORDS.
	INSERT INTO orders_data (order_id, order_date, ship_date, customer_name, region, city, category, product_id, sales, quantity, profit)
VALUES
('CA-2020-152156','2020-11-08','2020-11-11','Claire Gute','South','Henderson','Furniture','FUR-BO-10001798',261.96,2,41.9136),
('CA-2020-152156','2020-11-08','2020-11-11','Claire Gute','South','Henderson','Furniture','FUR-CH-10000454',731.94,3,219.582),
('CA-2020-138688','2020-06-12','2020-06-16','Darrin Van Huff','West','Los Angeles','Office Supplies','OFF-LA-10000240',14.62,2,6.8714),
('US-2019-108966','2019-10-11','2019-10-18','Sean ODonnell','South','Fort Lauderdale','Furniture','FUR-TA-10000577',957.577,5,-383.031),
('US-2019-108966','2019-10-11','2019-10-18','Sean ODonnell','South','Fort Lauderdale','Office Supplies','OFF-ST-10000760',22.368,2,2.5164),
('CA-2018-115812','2018-06-09','2018-06-14','Brosina Hoffman','West','Los Angeles','Furniture','FUR-FU-10001487',48.86,7,14.1694),
('CA-2018-115812','2018-06-09','2018-06-14','Brosina Hoffman','West','Los Angeles','Office Supplies','OFF-AR-10002833',7.28,4,1.9656),
('CA-2018-115812','2018-06-09','2018-06-14','Brosina Hoffman','West','Los Angeles','Technology','TEC-PH-10002275',907.152,6,90.7152),
('CA-2018-115812','2018-06-09','2018-06-14','Brosina Hoffman','West','Los Angeles','Office Supplies','OFF-BI-10003910',18.504,3,5.7825),
('CA-2018-115812','2018-06-09','2018-06-14','Brosina Hoffman','West','Los Angeles','Office Supplies','OFF-AP-10002892',114.9,5,34.47),
('CA-2018-115812','2018-06-09','2018-06-14','Brosina Hoffman','West','Los Angeles','Furniture','FUR-TA-10001539',1706.18,9,85.3092),
('CA-2018-115812','2018-06-09','2018-06-14','Brosina Hoffman','West','Los Angeles','Technology','TEC-PH-10002033',911.424,4,68.3568),
('CA-2021-114412','2021-04-15','2021-04-20','Andrew Allen','South','Concord','Office Supplies','OFF-PA-10002365',15.552,3,5.4432),
('CA-2020-161389','2020-12-05','2020-12-10','Irene Maddox','West','Seattle','Office Supplies','OFF-BI-10003656',407.976,3,132.592),
('US-2019-118983','2019-11-22','2019-11-26','Harold Pawlan','Central','Fort Worth','Office Supplies','OFF-AP-10002311',68.81,5,-123.858),
('US-2019-118983','2019-11-22','2019-11-26','Harold Pawlan','Central','Fort Worth','Office Supplies','OFF-BI-10000756',2.544,3,-3.816),
('CA-2018-105893','2018-11-11','2018-11-18','Pete Kriz','Central','Madison','Office Supplies','OFF-ST-10004186',665.88,6,13.3176),
('CA-2018-167164','2018-05-13','2018-05-15','Alejandro Grove','West','West Jordan','Office Supplies','OFF-ST-10000107',55.5,2,9.99),
('CA-2018-143336','2018-08-27','2018-09-01','Zuschuss Donatelli','West','San Francisco','Office Supplies','OFF-AR-10003056',8.56,2,2.4824),
('CA-2018-143336','2018-08-27','2018-09-01','Zuschuss Donatelli','West','San Francisco','Technology','TEC-PH-10001949',213.48,3,16.011),
('CA-2018-143336','2018-08-27','2018-09-01','Zuschuss Donatelli','West','San Francisco','Office Supplies','OFF-BI-10002215',22.72,4,7.384),
('CA-2020-137330','2020-12-09','2020-12-13','Ken Black','Central','Fremont','Office Supplies','OFF-AR-10000246',19.46,7,5.0596),
('CA-2020-137330','2020-12-09','2020-12-13','Ken Black','Central','Fremont','Office Supplies','OFF-AP-10001492',60.34,7,15.6884),
('US-2021-156909','2021-07-16','2021-07-18','Sandra Flanagan','East','Philadelphia','Furniture','FUR-CH-10002774',71.372,2,-1.0196),
('CA-2019-106320','2019-09-25','2019-09-30','Emily Burns','West','Orem','Furniture','FUR-TA-10000577',1044.63,3,240.265),
('CA-2020-121755','2020-01-16','2020-01-20','Eric Hoffmann','West','Los Angeles','Office Supplies','OFF-BI-10001634',11.648,2,4.2224),
('CA-2020-121755','2020-01-16','2020-01-20','Eric Hoffmann','West','Los Angeles','Technology','TEC-AC-10003027',90.57,3,11.7741),
('US-2019-150630','2019-09-17','2019-09-21','Tracy Blumstein','East','Philadelphia','Furniture','FUR-BO-10004834',3083.43,7,-1665.05),
('US-2019-150630','2019-09-17','2019-09-21','Tracy Blumstein','East','Philadelphia','Office Supplies','OFF-BI-10000474',9.618,2,-7.0532),
('US-2019-150630','2019-09-17','2019-09-21','Tracy Blumstein','East','Philadelphia','Furniture','FUR-FU-10004848',124.2,3,15.525),
('US-2019-150630','2019-09-17','2019-09-21','Tracy Blumstein','East','Philadelphia','Office Supplies','OFF-EN-10001509',3.264,2,1.1016),
('US-2019-150630','2019-09-17','2019-09-21','Tracy Blumstein','East','Philadelphia','Office Supplies','OFF-AR-10004042',86.304,6,9.7092),
('US-2019-150630','2019-09-17','2019-09-21','Tracy Blumstein','East','Philadelphia','Office Supplies','OFF-BI-10001525',6.858,6,-5.715),
('US-2019-150630','2019-09-17','2019-09-21','Tracy Blumstein','East','Philadelphia','Office Supplies','OFF-AR-10001683',15.76,2,3.546),
('CA-2021-107727','2021-10-19','2021-10-23','Matt Abelman','Central','Houston','Office Supplies','OFF-PA-10000249',29.472,3,9.9468),
('CA-2020-117590','2020-12-08','2020-12-10','Gene Hale','Central','Richardson','Technology','TEC-PH-10004977',1097.54,7,123.474),
('CA-2020-117590','2020-12-08','2020-12-10','Gene Hale','Central','Richardson','Furniture','FUR-FU-10003664',190.92,5,-147.963),
('CA-2019-117415','2019-12-27','2019-12-31','Steve Nguyen','Central','Houston','Office Supplies','OFF-EN-10002986',113.328,9,35.415),
('CA-2019-117415','2019-12-27','2019-12-31','Steve Nguyen','Central','Houston','Furniture','FUR-BO-10002545',532.399,3,-46.9764),
('CA-2019-117415','2019-12-27','2019-12-31','Steve Nguyen','Central','Houston','Furniture','FUR-CH-10004218',212.058,3,-15.147),
('CA-2019-117415','2019-12-27','2019-12-31','Steve Nguyen','Central','Houston','Technology','TEC-PH-10000486',371.168,4,41.7564),
('CA-2021-120999','2021-09-10','2021-09-15','Linda Cazamias','Central','Naperville','Technology','TEC-PH-10004093',147.168,4,16.5564),
('CA-2020-101343','2020-07-17','2020-07-22','Ruben Ausman','West','Los Angeles','Office Supplies','OFF-ST-10003479',77.88,2,3.894),
('CA-2021-139619','2021-09-19','2021-09-23','Erin Smith','South','Melbourne','Office Supplies','OFF-ST-10003282',95.616,2,9.5616),
('CA-2020-118255','2020-03-11','2020-03-13','Odella Nelson','Central','Eagan','Technology','TEC-AC-10000171',45.98,2,19.7714),
('CA-2020-118255','2020-03-11','2020-03-13','Odella Nelson','Central','Eagan','Office Supplies','OFF-BI-10003291',17.46,2,8.2062),
('CA-2018-146703','2018-10-20','2018-10-25','Patrick ODonnell','Central','Westland','Office Supplies','OFF-ST-10001713',211.96,4,8.4784),
('CA-2020-169194','2020-06-20','2020-06-25','Lena Hernandez','East','Dover','Technology','TEC-AC-10002167',45,3,4.95),
('CA-2020-169194','2020-06-20','2020-06-25','Lena Hernandez','East','Dover','Technology','TEC-PH-10003988',21.8,2,6.104),
('CA-2019-115742','2019-04-18','2019-04-22','Darren Powers','Central','New Albany','Office Supplies','OFF-BI-10004410',38.22,6,17.9634),
('CA-2019-115742','2019-04-18','2019-04-22','Darren Powers','Central','New Albany','Office Supplies','OFF-LA-10002762',75.18,6,35.3346),
('CA-2019-115742','2019-04-18','2019-04-22','Darren Powers','Central','New Albany','Furniture','FUR-FU-10001706',6.16,2,2.9568),
('CA-2019-115742','2019-04-18','2019-04-22','Darren Powers','Central','New Albany','Furniture','FUR-CH-10003061',89.99,1,17.0981),
('CA-2020-105816','2020-12-11','2020-12-17','Janet Molinari','East','New York City','Office Supplies','OFF-FA-10000304',15.26,7,6.2566),
('CA-2020-105816','2020-12-11','2020-12-17','Janet Molinari','East','New York City','Technology','TEC-PH-10002447',1029.95,5,298.685),
('CA-2020-111682','2020-06-17','2020-06-18','Ted Butterfield','East','Troy','Office Supplies','OFF-ST-10000604',208.56,6,52.14),
('CA-2020-111682','2020-06-17','2020-06-18','Ted Butterfield','East','Troy','Office Supplies','OFF-PA-10001569',32.4,5,15.552),
('CA-2020-111682','2020-06-17','2020-06-18','Ted Butterfield','East','Troy','Furniture','FUR-CH-10003968',319.41,5,7.098),
('CA-2020-111682','2020-06-17','2020-06-18','Ted Butterfield','East','Troy','Office Supplies','OFF-PA-10000587',14.56,2,6.9888),
('CA-2020-111682','2020-06-17','2020-06-18','Ted Butterfield','East','Troy','Technology','TEC-AC-10002167',30,2,3.3),
('CA-2020-111682','2020-06-17','2020-06-18','Ted Butterfield','East','Troy','Office Supplies','OFF-BI-10001460',48.48,4,16.362),
('CA-2020-111682','2020-06-17','2020-06-18','Ted Butterfield','East','Troy','Office Supplies','OFF-AR-10001868',1.68,1,0.84),
('CA-2019-135545','2019-11-24','2019-11-30','Kunst Miller','West','Los Angeles','Technology','TEC-AC-10004633',13.98,2,6.1512),
('CA-2019-135545','2019-11-24','2019-11-30','Kunst Miller','West','Los Angeles','Office Supplies','OFF-BI-10001078',25.824,6,9.3612),
('CA-2019-135545','2019-11-24','2019-11-30','Kunst Miller','West','Los Angeles','Office Supplies','OFF-PA-10003892',146.73,3,68.9631),
('CA-2019-135545','2019-11-24','2019-11-30','Kunst Miller','West','Los Angeles','Furniture','FUR-FU-10000397',79.76,4,22.3328),
('US-2019-164175','2019-04-30','2019-05-05','Paul Stevenson','Central','Chicago','Furniture','FUR-CH-10001146',213.115,5,-15.2225),
('CA-2018-106376','2018-12-05','2018-12-10','Brendan Sweed','West','Gilbert','Office Supplies','OFF-AR-10002671',1113.02,8,111.302),
('CA-2018-106376','2018-12-05','2018-12-10','Brendan Sweed','West','Gilbert','Technology','TEC-PH-10002726',167.968,4,62.988),
('CA-2020-119823','2020-06-04','2020-06-06','Karen Daniels','South','Springfield','Office Supplies','OFF-PA-10000482',75.88,2,35.6636),
('CA-2020-106075','2020-09-18','2020-09-23','Henry MacAllister','East','New York City','Office Supplies','OFF-BI-10004654',4.616,1,1.731),
('CA-2021-114440','2021-09-14','2021-09-17','Tracy Blumstein','Central','Jackson','Office Supplies','OFF-PA-10004675',19.05,3,8.763),
('US-2019-134026','2019-04-26','2019-05-02','Joel Eaton','South','Memphis','Furniture','FUR-CH-10000513',831.936,8,-114.391),
('US-2019-134026','2019-04-26','2019-05-02','Joel Eaton','South','Memphis','Furniture','FUR-FU-10003708',97.04,2,1.213),
('US-2019-134026','2019-04-26','2019-05-02','Joel Eaton','South','Memphis','Office Supplies','OFF-ST-10004123',72.784,1,-18.196),
('US-2021-118038','2021-12-09','2021-12-11','Ken Brennan','Central','Houston','Office Supplies','OFF-BI-10004182',1.248,3,-1.9344),
('US-2021-118038','2021-12-09','2021-12-11','Ken Brennan','Central','Houston','Furniture','FUR-FU-10000260',9.708,3,-5.8248),
('US-2021-118038','2021-12-09','2021-12-11','Ken Brennan','Central','Houston','Office Supplies','OFF-ST-10000615',27.24,3,2.724),
('US-2018-147606','2018-11-26','2018-12-01','Joel Eaton','Central','Houston','Furniture','FUR-FU-10003194',19.3,5,-14.475),
('CA-2020-127208','2020-06-12','2020-06-15','Stewart Carmichael','South','Decatur','Office Supplies','OFF-AP-10002118',208.16,1,56.2032),
('CA-2020-127208','2020-06-12','2020-06-15','Stewart Carmichael','South','Decatur','Office Supplies','OFF-BI-10002309',16.74,3,8.0352),
('CA-2018-139451','2018-10-12','2018-10-16','Duane Noonan','West','San Francisco','Office Supplies','OFF-AR-10002053',14.9,5,4.172),
('CA-2018-139451','2018-10-12','2018-10-16','Duane Noonan','West','San Francisco','Office Supplies','OFF-ST-10002370',21.39,1,6.2031),
('CA-2019-149734','2019-09-03','2019-09-08','Julie Creighton','South','Durham','Office Supplies','OFF-EN-10000927',200.984,7,62.8075),
('US-2021-119662','2021-11-13','2021-11-16','Christopher Schild','Central','Chicago','Office Supplies','OFF-ST-10003656',230.376,3,-48.9549),
('CA-2021-140088','2021-05-28','2021-05-30','Patrick ODonnell','South','Columbia','Furniture','FUR-CH-10000863',301.96,2,33.2156),
('CA-2021-155558','2021-10-26','2021-11-02','Paul Gonzalez','Central','Rochester','Technology','TEC-AC-10001998',19.99,1,6.7966),
('CA-2021-155558','2021-10-26','2021-11-02','Paul Gonzalez','Central','Rochester','Office Supplies','OFF-LA-10000134',6.16,2,2.9568),
('CA-2020-159695','2020-04-05','2020-04-10','Gary Mitchum','Central','Houston','Office Supplies','OFF-ST-10003442',158.368,7,13.8572),
('CA-2020-109806','2020-09-17','2020-09-22','Jim Sink','West','Los Angeles','Office Supplies','OFF-AR-10004930',20.1,3,6.633),
('CA-2020-109806','2020-09-17','2020-09-22','Jim Sink','West','Los Angeles','Technology','TEC-PH-10004093',73.584,2,8.2782),
('CA-2020-109806','2020-09-17','2020-09-22','Jim Sink','West','Los Angeles','Office Supplies','OFF-PA-10000304',6.48,1,3.1104),
('CA-2019-149587','2019-01-31','2019-02-05','Karl Braun','Central','Minneapolis','Office Supplies','OFF-PA-10003177',12.96,2,6.2208),
('CA-2019-149587','2019-01-31','2019-02-05','Karl Braun','Central','Minneapolis','Furniture','FUR-FU-10003799',53.34,3,16.5354),
('CA-2019-149587','2019-01-31','2019-02-05','Karl Braun','Central','Minneapolis','Office Supplies','OFF-BI-10002852',32.96,2,16.1504),
('US-2021-109484','2021-11-06','2021-11-12','Roger Barcio','West','Portland','Office Supplies','OFF-BI-10004738',5.682,1,-3.788),
('CA-2021-161018','2021-11-09','2021-11-11','Parhena Norris','East','New York City','Furniture','FUR-FU-10000629',96.53,7,40.5426),
('CA-2021-157833','2021-06-17','2021-06-20','Katherine Ducich','West','San Francisco','Office Supplies','OFF-BI-10001721',51.312,3,17.9592),
('CA-2020-149223','2020-09-06','2020-09-11','Elpida Rittenbach','Central','Saint Paul','Office Supplies','OFF-AP-10000358',77.88,6,22.5852),
('CA-2020-158568','2020-08-29','2020-09-02','Rick Bensley','Central','Chicago','Office Supplies','OFF-PA-10003256',64.624,7,22.6184);

13. QUERIES With Explaination.


Sure! Here’s a breakdown of each SQL query along with explanations of what they do:

1. Retrieve All Records from the Table
Query: SELECT * FROM orders_data;

Explanation: This query retrieves all columns and all records from the orders_data table. The * wildcard signifies that all fields should be included in the results.
2. Retrieve Specific Columns
Query: SELECT Order_Id, Order_Date, Sales FROM Orders_Data;

Explanation: This query retrieves only the Order_Id, Order_Date, and Sales columns from the Orders_Data table. It's useful when you only need specific data rather than the entire table.
3. Retrieve the First 10 Records
Query: SELECT Order_Id, Order_Date, Sales FROM Orders_Data LIMIT 10;

Explanation: This query fetches the first 10 records from the Orders_Data table, displaying only the Order_Id, Order_Date, and Sales columns. The LIMIT clause restricts the number of records returned.
4. Retrieve All Records Sorted by Order Date
Query: SELECT * FROM Orders_Data ORDER BY ORDER_DATE;

Explanation: This query retrieves all records from the Orders_Data table but sorts them by the ORDER_DATE column in ascending order (oldest to newest).
5. Retrieve Records Sorted by Order Date and Profit
Query: SELECT * FROM Orders_Data ORDER BY ORDER_DATE, Profit;

Explanation: This query sorts the records first by ORDER_DATE and then by Profit. If multiple records have the same ORDER_DATE, they will be sorted by Profit next.
6. Retrieve Records Sorted by Order Date in Descending Order
Query: SELECT * FROM Orders_Data ORDER BY ORDER_DATE DESC;

Explanation: Similar to the previous query, but the records are sorted in descending order, meaning the most recent orders appear first.
7. Retrieve Top 5 Sales Records
Query: SELECT * FROM Orders_Data ORDER BY SALES DESC LIMIT 5;

Explanation: This query retrieves the top 5 records with the highest Sales values, ordered in descending order. The LIMIT clause restricts the output to 5 records.
8. Calculate Profit Ratio
Query: SELECT *, (PROFIT/SALES) AS PROFIT_RATIO FROM Orders_Data ORDER BY PROFIT_RATIO;

Explanation: This query calculates the PROFIT_RATIO by dividing PROFIT by SALES for each record and adds it as a new column in the result. The records are then sorted by this new PROFIT_RATIO.
9. Calculate Profit Ratio and Profit Difference
Query: SELECT *, (PROFIT/SALES) AS PROFIT_RATIO, (SALES - PROFIT) AS PROFIT_DIFF FROM Orders_Data ORDER BY PROFIT_RATIO;

Explanation: This query calculates both the PROFIT_RATIO and PROFIT_DIFF (the difference between SALES and PROFIT). It adds these as new columns in the result and sorts by PROFIT_RATIO.
10. Retrieve Orders from the Central Region
Query: SELECT * FROM Orders_Data WHERE REGION = "CENTRAL";

Explanation: This query retrieves all records from the Orders_Data table where the REGION is "CENTRAL".
11. Retrieve Records with Quantity Greater than 3
Query: SELECT * FROM Orders_Data WHERE QUANTITY > 3;

Explanation: This query fetches all records where the QUANTITY is greater than 3, filtering out those that do not meet this condition.
12. Retrieve Records Ordered by Quantity
Query: SELECT * FROM Orders_Data WHERE QUANTITY > 3 ORDER BY QUANTITY;

Explanation: Similar to the previous query, but this one sorts the records in ascending order by QUANTITY.
13. Retrieve Orders on a Specific Date
Query: SELECT * FROM Orders_Data WHERE ORDER_DATE = "2019-09-17";

Explanation: This query retrieves all records where the ORDER_DATE matches September 17, 2019.
14. Retrieve Records with Order Date After a Specific Date
Query: SELECT * FROM Orders_Data WHERE ORDER_DATE > "2020-09-17" ORDER BY ORDER_DATE;

Explanation: This query fetches records where the ORDER_DATE is after September 17, 2020, and sorts them by ORDER_DATE.
15. Retrieve Orders from the Central Region in Technology Category
Query: SELECT * FROM Orders_Data WHERE REGION = "CENTRAL" AND CATEGORY = "TECHNOLOGY";

Explanation: This query retrieves records that are from the "CENTRAL" region and belong to the "TECHNOLOGY" category, applying both conditions.
16. Retrieve Orders with Quantity Greater than 2
Query: SELECT * FROM Orders_Data WHERE REGION = "CENTRAL" AND CATEGORY = "TECHNOLOGY" AND QUANTITY > 2;

Explanation: This query retrieves records that meet all three conditions: from the "CENTRAL" region, in the "TECHNOLOGY" category, and have a QUANTITY greater than 2.
17. Retrieve Orders from Central Region or Technology Category
Query: SELECT * FROM Orders_Data WHERE REGION = "CENTRAL" OR CATEGORY = "TECHNOLOGY";

Explanation: This query retrieves records that either belong to the "CENTRAL" region or are categorized under "TECHNOLOGY".
18. Retrieve Orders with Conditions on Region, Category, and Quantity
Query: SELECT * FROM Orders_Data WHERE (REGION = "CENTRAL" OR CATEGORY = "TECHNOLOGY") AND QUANTITY > 5;

Explanation: This query combines conditions using OR and AND. It retrieves records from the "CENTRAL" region or "TECHNOLOGY" category but only if the QUANTITY is greater than 5.
19. Retrieve Orders with Quantity Between 3 and 5
Query: SELECT * FROM Orders_Data WHERE QUANTITY >= 3 AND QUANTITY <= 5 ORDER BY QUANTITY;

Explanation: This query retrieves records where the QUANTITY is between 3 and 5 (inclusive) and sorts them by QUANTITY.
20. Retrieve Orders with Quantity Between 3 and 6
Query: SELECT * FROM Orders_Data WHERE QUANTITY BETWEEN 3 AND 6;

Explanation: Similar to the previous query, but it uses the BETWEEN operator to filter for records with QUANTITY values from 3 to 6 (inclusive).
21. Retrieve Orders with Specific Quantities
Query: SELECT * FROM Orders_Data WHERE QUANTITY IN (3, 4, 5, 6) ORDER BY QUANTITY;

Explanation: This query retrieves records where the QUANTITY is one of the specified values (3, 4, 5, or 6) and sorts the results by QUANTITY.
22. Retrieve Orders with Specific Quantities
Query: SELECT * FROM Orders_Data WHERE QUANTITY IN (3, 5) ORDER BY QUANTITY;

Explanation: This query fetches records where the QUANTITY is either 3 or 5, sorting them by QUANTITY.
23. Retrieve Orders from Specific Cities
Query: SELECT * FROM Orders_Data WHERE CITY IN ("Los Angeles", "San Francisco");

Explanation: This query retrieves records where the CITY is either "Los Angeles" or "San Francisco".
24. Retrieve Orders on Specific Dates
Query: SELECT * FROM Orders_Data WHERE ORDER_DATE IN ("2020-06-12", "2018-08-27");

Explanation: This query fetches records with ORDER_DATE matching either June 12, 2020, or August 27, 2018.
25. Retrieve Orders Within a Date Range
Query: SELECT * FROM Orders_Data WHERE ORDER_DATE BETWEEN "2018-08-27" AND "2020-06-12" ORDER BY ORDER_DATE;

Explanation: This query retrieves records with ORDER_DATE between August 27, 2018, and June 12, 2020, and sorts them by ORDER_DATE.
26. Retrieve Orders Where Customer Name Starts with "A"
Query: SELECT * FROM Orders_Data WHERE Customer_Name LIKE "A%";

Explanation: This query retrieves records where the Customer_Name starts with the letter "A".
27. Retrieve Orders Where Customer Name Ends with "N"
Query: SELECT * FROM Orders_Data WHERE Customer_Name LIKE "%N";

Explanation: This query retrieves records where the Customer_Name ends with the letter "N".
28. Retrieve Orders Where Customer Name Contains "A"
Query: SELECT * FROM Orders_Data WHERE Customer_Name LIKE "%A%";

Explanation: This query fetches records where the Customer_Name contains the letter "A" anywhere in the name.
29. Retrieve Orders Where Customer Name Starts with "e" in the Second Position
Query: SELECT * FROM Orders_Data WHERE Customer_Name LIKE "_e%";

Explanation: This query retrieves records where the second character of Customer_Name is "e". The underscore _ represents a single character.
30. Retrieve Orders Where Customer Name Starts with "a" or "e" in the Second Position
Query: SELECT * FROM Orders_Data WHERE Customer_Name LIKE '_a%' OR Customer_Name LIKE "_e%";

Explanation: This query retrieves records where the second character of Customer_Name is "a" or "e".
31. Calculate Total Sales
Query: SELECT SUM(Sales) AS Total_Sales FROM Orders_Data;

Explanation: This query calculates the total sales by summing the values in the Sales column and labels it as Total_Sales.
32. Find Minimum Sales Value
Query: SELECT MIN(Sales) AS Min_Sales FROM Orders_Data;

Explanation: This query finds the minimum value in the Sales column and labels it as Min_Sales.
33. Retrieve All Orders Ordered by Sales
Query: SELECT * FROM Orders_Data ORDER BY Sales;

Explanation: This query retrieves all records from the Orders_Data table and sorts them by the Sales column in ascending order.
34. Find Maximum Sales Value
Query: SELECT MAX(Sales) AS Max_Sales FROM Orders_Data;

Explanation: This query retrieves the maximum value from the Sales column and labels it as Max_Sales.
35. Calculate Average Sales
Query: SELECT AVG(Sales) AS Average_Sales FROM Orders_Data;

Explanation: This query calculates the average of the Sales values and labels it as Average_Sales.
36. Count Total Number of Records
Query: SELECT COUNT(*) FROM Orders_Data;

Explanation: This query counts the total number of records in the Orders_Data table, returning the count as a single value.
37. Calculate Average Sales Using Sum and Count
Query: SELECT SUM(Sales)/COUNT(*) AS Average_Sales FROM Orders_Data;

Explanation: This query calculates the average sales by dividing the total sales (sum) by the number of records and labels it as Average_Sales.
38. Count All Records and Order_ID Values
Query: SELECT COUNT(*), COUNT(Order_ID) AS No_of_Records FROM Orders_Data;

Explanation: This query counts all records in the table and separately counts non-null Order_ID values, labeling the latter as No_of_Records.
39. Update Records with NULL City Values
Query: UPDATE Orders_Data SET CITY = NULL WHERE ORDER_ID IN ("US-2019-118983", "CA-2020-152156");

Explanation: This query updates the CITY column to NULL for specific Order_IDs listed in the IN clause.
40. Retrieve Records Where City is Not NULL
Query: SELECT * FROM Orders_Data WHERE CITY IS NOT NULL;

Explanation: This query retrieves all records where the CITY column is not NULL, meaning it contains a valid city value.
41. Retrieve Records Where City is NULL
Query: SELECT * FROM Orders_Data WHERE CITY IS NULL;

Explanation: This query fetches records where the CITY column is NULL, indicating missing city information.
42. Count Total Records (Alternative)
Query: SELECT COUNT(1) FROM Orders_Data;

Explanation: This query counts the total number of records in the Orders_Data table. Using 1 instead of * is another way to achieve the same result.
43. Retrieve Distinct Category Values
Query: SELECT DISTINCT CATEGORY FROM Orders_Data;

Explanation: This query retrieves unique values from the CATEGORY column, filtering out duplicates.
44. Count Unique City Values
Query: SELECT COUNT(DISTINCT CITY) AS Unique_Cities FROM Orders_Data;

Explanation: This query counts the number of unique cities in the CITY column and labels it as Unique_Cities.
45. Sum of Sales for Each Category
Query: SELECT CATEGORY, SUM(Sales) AS Category_Sales FROM Orders_Data GROUP BY CATEGORY;

Explanation: This query sums the sales for each category and groups the results by CATEGORY.
46. Sum of Sales and Profit for Each Category
Query: SELECT CATEGORY, SUM(Sales) AS Category_Sales, SUM(Profit) AS Category_Profit FROM Orders_Data GROUP BY CATEGORY;

Explanation: This query retrieves the sum of Sales and Profit for each CATEGORY, grouping the results accordingly.
47. Sum of Sales and Profit for Each Category by Region
Query: SELECT CATEGORY, REGION, SUM(Sales) AS Category_Sales_Per_Region, SUM(Profit) AS Category_Profit_Per_Region FROM Orders_Data GROUP BY CATEGORY, REGION ORDER BY REGION;

Explanation: This query sums the sales and profit for each category grouped by REGION, and sorts the results by REGION.
48. Sum of Sales and Profit for Each City
Query: SELECT CITY, SUM(Sales) AS City_Sales, SUM(Profit) AS City_Profit FROM Orders_Data GROUP BY CITY;

Explanation: This query sums the sales and profit for each city, grouping the results by CITY.
49. Retrieve Cities with Sales Greater than 100
Query: SELECT CITY, SUM(Sales) AS City_Sales, SUM(Profit) AS City_Profit FROM Orders_Data GROUP BY CITY HAVING SUM(Sales) > 100;

Explanation: This query retrieves cities where the total sales exceed 100, using the HAVING clause to filter results after grouping.
50. Retrieve Cities in the West Region with Sales Greater than 100
Query: SELECT CITY, SUM(Sales) AS City_Sales, SUM(Profit) AS City_Profit FROM Orders_Data WHERE REGION = "WEST" GROUP BY CITY HAVING SUM(Sales) > 100;

Explanation: This query retrieves cities in the "WEST" region where total sales exceed 100, using both WHERE and HAVING clauses.
51. Retrieve Top 3 Cities in the West Region with Sales Greater than 100
Query: SELECT CITY, SUM(Sales) AS City_Sales, SUM(Profit) AS City_Profit FROM Orders_Data WHERE REGION = "WEST" GROUP BY CITY HAVING SUM(Sales) > 100 ORDER BY City_Sales LIMIT 3;

Explanation: This query retrieves the top 3 cities in the "WEST" region with total sales greater than 100, ordered by total sales.
52. SQL Clause Execution Order
Answer: FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT.

Explanation: This describes the order in which SQL clauses are processed when executing a query, which is crucial for understanding how to write effective SQL statements.

53. CREATE TABLE RETURNS_DATA.

CREATE TABLE returns_data (
	order_id nvarchar(20),
	return_reason varchar(20)
);

CREATE TABLE returns_data: This command initiates the creation of a new table named returns_data.

order_id nvarchar(20):

order_id is the name of the first column.
nvarchar(20) specifies that this column can store Unicode variable-length character strings, with a maximum length of 20 characters. This is useful for storing text that may include special characters or different languages.
return_reason varchar(20):

return_reason is the name of the second column.
varchar(20) specifies that this column can store variable-length character strings, with a maximum length of 20 characters. This is typically used for non-Unicode text.

54. INSERT INTO RETURNS_DATA TABLE.

INSERT INTO returns_data VALUES
('CA-2018-143336', 'Bad Quality'),
('CA-2020-109806', 'Wrong Items'),
('CA-2020-111682', 'Wrong Items'),
('US-2019-108966', 'Others'),
('CA-2018-167164', 'Bad Quality'),
('US-2019-164175', 'Wrong Item'),
('US-2021-119662', 'Bad Quality');

INSERT INTO returns_data: This command initiates the insertion of new records into the returns_data table.

VALUES: This keyword indicates that the values specified in parentheses will be added to the columns of the table.

Records: Each pair of parentheses contains two values that correspond to the order_id and return_reason columns, respectively. The values are as follows:

('CA-2018-143336', 'Bad Quality')
('CA-2020-109806', 'Wrong Items')
('CA-2020-111682', 'Wrong Items')
('US-2019-108966', 'Others')
('CA-2018-167164', 'Bad Quality')
('US-2019-164175', 'Wrong Item')
('US-2021-119662', 'Bad Quality')

56. How can I retrieve all records from the RETURNS_DATA table?
SELECT * FROM RETURNS_DATA;

57. JOIN Both ORDERS_DATA and RETURNS_DATA Tables.
SELECT *
FROM ORDERS_DATA INNER JOIN RETURNS_DATA
ON ORDERS_DATA.Order_ID = RETURNS_DATA.Order_ID;

58. How can I retrieve the total sales for each category of orders that have returns?
SELECT CATEGORY, SUM(Sales) AS Category_Sales
FROM ORDERS_DATA INNER JOIN RETURNS_DATA
ON ORDERS_DATA.Order_ID = RETURNS_DATA.Order_ID
GROUP BY CATEGORY;

59. How do I get all orders returned with the reason "Wrong Items" specifically from Los Angeles?
SELECT *
FROM ORDERS_DATA INNER JOIN RETURNS_DATA
ON ORDERS_DATA.Order_ID = RETURNS_DATA.Order_ID
WHERE Return_Reason = "Wrong Items" AND CITY = "Los Angeles";

60. How can I retrieve the order details for a specific order ID ("CA-2020-109806") from the ORDERS_DATA and RETURNS_DATA tables?
SELECT *
FROM ORDERS_DATA INNER JOIN RETURNS_DATA
ON ORDERS_DATA.Order_ID = RETURNS_DATA.Order_ID
WHERE Order_ID = "CA-2020-109806";

SELECT *
FROM ORDERS_DATA INNER JOIN RETURNS_DATA
ON ORDERS_DATA.Order_ID = RETURNS_DATA.Order_ID
WHERE ORDERS_DATA.Order_ID = "CA-2020-109806";

SELECT *
FROM ORDERS_DATA O INNER JOIN RETURNS_DATA R
ON O.Order_ID = R.Order_ID
WHERE O.Order_ID = "CA-2020-109806";

61. What is the execution order of SQL clauses?
FROM --> JOINS --> WHERE --> GROUP BY --> HAVING --> SELECT --> ORDER BY --> LIMIT

62. How do I retrieve all orders and their returns, even if there are no returns?
SELECT *
FROM ORDERS_DATA O LEFT JOIN RETURNS_DATA R
ON O.Order_ID = R.Order_ID;

63. How can I get all orders that have no return reason?
SELECT *
FROM ORDERS_DATA O LEFT JOIN RETURNS_DATA R
ON O.Order_ID = R.Order_ID
WHERE R.RETURN_REASON IS NULL;

64. How do I retrieve all orders that do not have any associated returns?
SELECT O.*
FROM ORDERS_DATA O LEFT JOIN RETURNS_DATA R
ON O.Order_ID = R.Order_ID
WHERE R.RETURN_REASON IS NULL;

65. How can I list all orders that have a return reason?
SELECT O.ORDER_ID,R.RETURN_REASON
FROM ORDERS_DATA O LEFT JOIN RETURNS_DATA R
ON O.Order_ID = R.Order_ID
WHERE R.RETURN_REASON IS NOT NULL;

66. How do I calculate the total sales for each return reason?
SELECT R.RETURN_REASON, SUM(O.Sales) AS Return_Sales
FROM ORDERS_DATA O LEFT JOIN RETURNS_DATA R
ON O.Order_ID = R.Order_ID
GROUP BY R.RETURN_REASON;

67. How can I create a new return reason that replaces "Wrong Item" with "Wrong Items"?
SELECT *,
CASE WHEN RETURN_REASON = "Wrong Item" THEN "Wrong Items" ELSE RETURN_REASON END AS New_Return_Reason
FROM RETURNS_DATA;

SELECT * FROM RETURNS_DATA;

68. How can I categorize orders into profit buckets based on profit values?
SELECT *,
	CASE WHEN Profit < 0 THEN "LOSS"
		 WHEN Profit < 50 THEN "Low Profit"
         WHEN Profit < 100 THEN "Medium Profit"
	ELSE "High Profit"
    END AS "Profit_Bucket"
FROM ORDERS_DATA;

69. How can I categorize orders into profit buckets while ensuring proper ordering of conditions?
SELECT *,
	CASE WHEN Profit < 0 THEN "LOSS"
		 WHEN Profit < 100 THEN "Medium Profit"
         WHEN Profit < 50 THEN "Low Profit"
	ELSE "High Profit"
    END AS Profit_Bucket
FROM ORDERS_DATA;

70. How do I create profit buckets with distinct ranges?
SELECT *,
	CASE WHEN Profit < 0 THEN "LOSS"
		 WHEN Profit BETWEEN 0 AND 49 THEN "Low Profit"
         WHEN Profit BETWEEN 50 AND 100 THEN "High Profit"
         ELSE "Very High Profit"
	END AS Profit_Bucket
FROM ORDERS_DATA;

71. How can I categorize profit levels in a specified order?
SELECT *,
	CASE WHEN Profit < 0 THEN "LOSS"
		 WHEN Profit BETWEEN 50 AND 100 THEN "High Profit"
		 WHEN Profit BETWEEN 0 AND 49 THEN "Low Profit"
         ELSE "Very High Profit"
	END AS Profit_Bucket
FROM ORDERS_DATA;

72. How do I retrieve the length of customer names from the ORDERS_DATA table?
SELECT *,
length(customer_name) AS Cust_Length
FROM ORDERS_DATA;

73. How can I extract the country code from the order ID?
SELECT *,
LEFT(Order_id, 2) AS Country_Code
FROM ORDERS_DATA;

74. How do I get the last six characters of the order ID?
SELECT *,
RIGHT(Order_ID,6) AS Order_ID_Value
FROM ORDERS_DATA;

75. How can I extract the year from the order ID?
SELECT *,
SUBSTRING(Order_ID,4,4) AS Order_Year
FROM ORDERS_DATA;

76. How do I replace characters in customer names?
SELECT *,
REPLACE (Customer_Name,'C','P') AS Replaced_Cust_Name
FROM ORDERS_DATA;

77. How can I replace specific characters in customer names with new characters?
SELECT *,
REPLACE (Customer_Name,'CL','PA') AS Replaced_Customer_Name
FROM ORDERS_DATA;

78. How do I retrieve yearly sales by extracting the year from the order date?
SELECT LEFT(Order_Date,4), SUM(Sales) AS Year_Wise_Sales
FROM ORDERS_DATA
GROUP BY LEFT(Order_Date,4);

79. How can I get total sales grouped by year from the order date?
SELECT YEAR(Order_Date), SUM(Sales) AS Year_Wise_Sales
FROM ORDERS_DATA
GROUP BY YEAR(Order_Date);

80. How do I extract the month from the order date for each order?
SELECT Order_ID, Order_Date,
MONTH(Order_Date) AS Order_MONTH
FROM ORDERS_DATA;

81. 
SELECT Order_ID, Order_Date,
MONTH(Order_Date) AS Order_Month,MONTHNAME(Order_Date) AS Order_Month_Name
FROM ORDERS_DATA;

82. How can I get both the month and the month name from the order date?
SELECT Order_ID,Order_Date,
QUARTER(Order_Date) AS Quarters, MONTH(Order_Date) AS Order_Month, 
MONTHNAME(Order_Date) AS Order_Month_Name
FROM ORDERS_DATA;

83. How do I retrieve quarter information along with month and month name from the order date?
SELECT 
YEAR(Order_Date) AS Order_Year,
QUARTER(Order_Date) AS Quarters,
MONTH(Order_Date) AS Order_Month,
MONTHNAME(Order_Date) AS Order_Month_Name, SUM(SALES) AS Sales_Details
FROM ORDERS_DATA
GROUP BY YEAR(Order_Date),QUARTER(Order_Date),MONTH(Order_Date),MONTHNAME(Order_Date);

84. How can I summarize sales details by year, quarter, and month from the order date?
SELECT Order_ID, Order_Date, Ship_Date,
DATEDIFF(Ship_Date,Order_Date) AS Lead_Days
FROM ORDERS_DATA;

85. How do I calculate the lead days between the order date and ship date?
SELECT Order_ID,Order_Date,Ship_Date,
DATE_ADD(Order_Date, INTERVAL 5 DAY) AS Order_5
FROM ORDERS_DATA;