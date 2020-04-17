# ETL (Extract, Transform, and Load) Process

What is ETL?
ETL is a process that extracts the data from different source systems, then transforms the data (like applying calculations, concatenations, etc.) and finally loads the data into the Data Warehouse system. Full form of ETL is Extract, Transform and Load.

It's tempting to think a creating a Data warehouse is simply extracting data from multiple sources and loading into database of a Data warehouse. This is far from the truth and requires a complex ETL process. The ETL process requires active inputs from various stakeholders including developers, analysts, testers, top executives and is technically challenging.

In order to maintain its value as a tool for decision-makers, Data warehouse system needs to change with business changes. ETL is a recurring activity (daily, weekly, monthly) of a Data warehouse system and needs to be agile, automated, and well documented.

In this tutorial, you will learn-

What is ETL?
Why do you need ETL?
ETL Process in Data Warehouses
Step 1) Extraction
Step 2) Transformation
Step 3) Loading
ETL tools
Best practices ETL process
# Why do you need ETL?

There are many reasons for adopting ETL in the organization:

It helps companies to analyze their business data for taking critical business decisions.
Transactional databases cannot answer complex business questions that can be answered by ETL.
A Data Warehouse provides a common data repository
ETL provides a method of moving the data from various sources into a data warehouse.
As data sources change, the Data Warehouse will automatically update.
Well-designed and documented ETL system is almost essential to the success of a Data Warehouse project.
Allow verification of data transformation, aggregation and calculations rules.
ETL process allows sample data comparison between the source and the target system.
ETL process can perform complex transformations and requires the extra area to store the data.
ETL helps to Migrate data into a Data Warehouse. Convert to the various formats and types to adhere to one consistent system.
ETL is a predefined process for accessing and manipulating source data into the target database.
ETL offers deep historical context for the business.
It helps to improve productivity because it codifies and reuses without a need for technical skills.

# ETL Process in Data Warehouses
ETL is a 3-step process

![Image of ETLExtract1](https://www.guru99.com/images/1/022218_0848_ETLExtractT1.png)

# Step 1) Extraction
In this step, data is extracted from the source system into the staging area. Transformations if any are done in staging area so that performance of source system in not degraded. Also, if corrupted data is copied directly from the source into Data warehouse database, rollback will be a challenge. Staging area gives an opportunity to validate extracted data before it moves into the Data warehouse.

Data warehouse needs to integrate systems that have different

DBMS, Hardware, Operating Systems and Communication Protocols. Sources could include legacy applications like Mainframes, customized applications, Point of contact devices like ATM, Call switches, text files, spreadsheets, ERP, data from vendors, partners amongst others.

Hence one needs a logical data map before data is extracted and loaded physically. This data map describes the relationship between sources and target data.

Three Data Extraction methods:

Full Extraction
Partial Extraction- without update notification.
Partial Extraction- with update notification
Irrespective of the method used, extraction should not affect performance and response time of the source systems. These source systems are live production databases. Any slow down or locking could effect company's bottom line.

Some validations are done during Extraction:

Reconcile records with the source data
Make sure that no spam/unwanted data loaded
Data type check
Remove all types of duplicate/fragmented data
Check whether all the keys are in place or not

# Step 2) Transformation

Data extracted from source server is raw and not usable in its original form. Therefore it needs to be cleansed, mapped and transformed. In fact, this is the key step where ETL process adds value and changes data such that insightful BI reports can be generated.

In this step, you apply a set of functions on extracted data. Data that does not require any transformation is called as direct move or pass through data.

In transformation step, you can perform customized operations on data. For instance, if the user wants sum-of-sales revenue which is not in the database. Or if the first name and the last name in a table is in different columns. It is possible to concatenate them before loading.

![Image of ETLExtract2](https://www.guru99.com/images/1/022218_0848_ETLExtractT2.png)

Following are Data Integrity Problems:

Different spelling of the same person like Jon, John, etc.
There are multiple ways to denote company name like Google, Google Inc.
Use of different names like Cleaveland, Cleveland.
There may be a case that different account numbers are generated by various applications for the same customer.
In some data required files remains blank
Invalid product collected at POS as manual entry can lead to mistakes.
Validations are done during this stage

Filtering – Select only certain columns to load
Using rules and lookup tables for Data standardization
Character Set Conversion and encoding handling
Conversion of Units of Measurements like Date Time Conversion, currency conversions, numerical conversions, etc.
Data threshold validation check. For example, age cannot be more than two digits.
Data flow validation from the staging area to the intermediate tables.
Required fields should not be left blank.
Cleaning ( for example, mapping NULL to 0 or Gender Male to "M" and Female to "F" etc.)
Split a column into multiples and merging multiple columns into a single column.
Transposing rows and columns,
Use lookups to merge data
Using any complex data validation (e.g., if the first two columns in a row are empty then it automatically reject the row from processing)

# Step 3) Loading

Loading data into the target datawarehouse database is the last step of the ETL process. In a typical Data warehouse, huge volume of data needs to be loaded in a relatively short period (nights). Hence, load process should be optimized for performance.

In case of load failure, recover mechanisms should be configured to restart from the point of failure without data integrity loss. Data Warehouse admins need to monitor, resume, cancel loads as per prevailing server performance.

# Types of Loading:

Initial Load — populating all the Data Warehouse tables
Incremental Load — applying ongoing changes as when needed periodically.
Full Refresh —erasing the contents of one or more tables and reloading with fresh data.
Load verification
Ensure that the key field data is neither missing nor null.
Test modeling views based on the target tables.
Check that combined values and calculated measures.
Data checks in dimension table as well as history table.
Check the BI reports on the loaded fact and dimension table.

# ETL tools

There are many Data Warehousing tools are available in the market. Here, are some most prominent one:

1. MarkLogic:

MarkLogic is a data warehousing solution which makes data integration easier and faster using an array of enterprise features. It can query different types of data like documents, relationships, and metadata.

https://developer.marklogic.com/products/

2. Oracle:

Oracle is the industry-leading database. It offers a wide range of choice of Data Warehouse solutions for both on-premises and in the cloud. It helps to optimize customer experiences by increasing operational efficiency.

https://www.oracle.com/index.html

3. Amazon RedShift:

Amazon Redshift is Datawarehouse tool. It is a simple and cost-effective tool to analyze all types of data using standard SQL and existing BI tools. It also allows running complex queries against petabytes of structured data.

https://aws.amazon.com/redshift/?nc2=h_m1

Here is a complete list of useful Data warehouse Tools.

Best practices ETL process
Never try to cleanse all the data:

Every organization would like to have all the data clean, but most of them are not ready to pay to wait or not ready to wait. To clean it all would simply take too long, so it is better not to try to cleanse all the data.

Never cleanse Anything:

Always plan to clean something because the biggest reason for building the Data Warehouse is to offer cleaner and more reliable data.

Determine the cost of cleansing the data:

Before cleansing all the dirty data, it is important for you to determine the cleansing cost for every dirty data element.

To speed up query processing, have auxiliary views and indexes:

To reduce storage costs, store summarized data into disk tapes. Also, the trade-off between the volume of data to be stored and its detailed usage is required. Trade-off at the level of granularity of data to decrease the storage costs.

# Summary:

ETLstands for Extract, Transform and Load.
ETL provides a method of moving the data from various sources into a data warehouse.
In the first step extraction, data is extracted from the source system into the staging area.
In the transformation step, the data extracted from source is cleansed and transformed .
Loading data into the target datawarehouse is the last step of the ETL process.

Source:https://www.guru99.com/etl-extract-load-process.html
