
# Home_Sales


This project required working with Big Data and SparkSQL to analyze and query home sales data. The data analysis was conducted considering the following processes:

Importing packages: The project began by importing the required packages, which included findspark to initialize Spark and pyspark.sql to work with SparkSQL.

A SparkSession was established with SparkSession.builder.appName("SparkSQL").getOrCreate() to connect to Spark.oms and calculate square footage.

Cache the data: The temporary table "home_sales_df" was cached with the spark. catalog.cacheTable() method to increase query performance by saving the data in memory.

Query runtime comparison: The runtime of a single query was compared to the cached version and the version using Parquet data. Before running each query, the start time was recorded using time. time(), and the difference in time was used to compute the runtime. 
Writing Parquet data: The prepared house sales data was written to Parquet format using the partitionBy().parquet() method, which partitioned the data by the "date_built" field. 
Reading Parquet data: The Parquet data was converted to a DataFrame for further analysis. 
Create a temporary table for Parquet data: The createOrReplaceTempView() method built a temporary table named "parquet_table" for the Parquet DataFrame. 
Querying Parquet Data: SQL queries were run on the Parquet DataFrame to remove view ratings with an average price higher than or equal to $350,000. The runtime was measured and compared to a cached version. 
Detaching the temporary table: To free up memory, the temporary table "home_sales" was uncached with the spark.catalog.uncacheTable() function. 

Checking caching status: The spark.catalog.isCached() function was used to determine whether the table "home_sales" was still cached or not. 
Overall, this project demonstrated the use of SparkSQL to read, query, cache, and analyze home sales data, revealing average prices based on a variety of parameters. 


