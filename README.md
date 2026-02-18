# Microsoft-fabric-project1--End-to-End-Data-Pipeline-Azure-Gen2-Lakehouse-Spark-Azure-Gen2
To build an automated data pipeline that ingests raw files from Azure Data Lake Gen2, processes and aggregates them using Spark, and publishes clean Gold-layer datasets back to the data lake for analytics and reporting.

# Tech Stack
Azure Data Lake Gen2
Lakehouse Architecture (Bronze / Silver / Gold)
Spark (PySpark)
Pipelines (Get Metadata, ForEach, Copy Data)
Power BI

# Pipeline Workflow

1.Get Metadata Activity
=>Reads all files from source folder in Azure Gen2
2.ForEach Activity
=>Iterates through each file dynamically
3.Copy Data Activity
=>Loads raw data into Lakehouse (Bronze layer)
4.Spark Notebook
=>Data cleaning & transformations
=>Aggregations and joins
=>Gold data written back to Azure Gen2

Spark Transformations
Customer
-------------------------------------------------------------------------------------
Email → lowercase

Name → capitalize

Gender → Male / Female

Date → standardized format

Location → cleaned

Dedup → customer_id

Drop nulls → customer_id, email

Orders
----------------------------------------------------------------------------------

Order date → correct format

Amount → double (< 0 → NULL)

Status → capitalize

Dedup → order_id

Drop nulls → customer_id, order_date

Payments
----------------------------------------------------------------------------

Payment date → correct format

Normalize values (credit card)

Capitalize method & status

Amount → double (< 0 → NULSupport

Ticket date → correct format

Issue & resolution → capitalize

Handle NA, empty → NULL

Dedup → ticket_id

Drop nulls → customer_id, ticket_date

Web Activity
-------------------------------------------------------------------------------
Session time → correct format
Page viewed → lowercase
Device type → capitalize
Dedup → session_id
Drop nulls → customer_id, session_time, page_viewed

-------------------------------------------------------------------------------
# Customer 360 (Gold Layer)

All datasets were joined to create a Customer 360 unified table for analytics.

# Power BI Dashboard
---------------------------------------------------------------------------

Total customers, orders & tickets

Total order amount

Revenue by location, gender, payment method

Ticket resolution analysis

Order trends by date

Device-wise customer behavior
Drop nulls → customer_id, session_time, page_viewedL)

Drop nulls → customer_id, payment_date, amount
