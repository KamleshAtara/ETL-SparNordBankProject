# ETL-SparNordBankProject
Project to build a batch ETL pipeline to read transactional data from Amazon RDS, transform it to a usable format and then load it into an Amazon S3 bucket. The data is then further loaded into Redshift Tables and analysis is done to find valuable insight.

The project uses below listed tools, services and concepts

AWS EMR: cloud-based big data platform that simplifies the processing and analysis of vast datasets using popular open-source frameworks like Hadoop and Spark.

AWS RDS (MySQL): Managed database service that simplifies database administration, scaling, and high availability for MySQL applications in the cloud.

Hadoop: open-source framework for distributed storage and processing of large datasets, providing a scalable and fault-tolerant platform for big data analytics.

Apache Scoop: tool used for transferring bulk data between Apache Hadoop and structured data stores such as relational databases.

Apache PySpark: Data from RDS is transformed into required schema using PySpark

AWS RedShift: Fully managed, petabyte-scale data warehousing service that allows businesses to analyze large volumes of data with high performance and scalability, making it well-suited for data analytics and business intelligence applications.

AWS S3: Amazon S3 sto move transformed data from RDS and then send it further to RDS.

# Problem Statement
Spar Nord Bank aims to study the transaction data and better manage the ATM cash.The ATM cash fill depends on various attributes uch as ATM activity, geographical location, weather conditions, and the day of the week.
Bank wants to use the dataset and derive insight to better understand the refill frequency for its ATMs. Below questions has been used to get insight on dataset

1. Top 10 ATMs where most transactions are in the ’inactive’ state
2. Number of ATM failures corresponding to the different weather conditions recorded at the time of the transactions
3. Top 10 ATMs with the most number of transactions throughout the year
4. Number of overall ATM transactions going inactive per month for each month
5. Top 10 ATMs with the highest total amount withdrawn throughout the year
6. Number of failed ATM transactions across various card types
7. Top 10 records with the number of transactions ordered by the ATM_number, ATM_manufacturer, location, weekend_flag and then total_transaction_count, on weekdays and on weekends throughout the year
8. Most active day in each ATMs from location "Vejgaard"

# Approach

Below task has been performed as part of this project

1. Extracting the transactional data from a given MySQL RDS server to HDFS(EC2) instance using Sqoop.
2. Transforming the transactional data according to the given target schema using PySpark. 
3. This transformed data is to be loaded to an S3 bucket.
4. Creating the Redshift tables according to the given schema.
5. Loading the data from Amazon S3 to Redshift tables.
6. Performing the analysis queries.

