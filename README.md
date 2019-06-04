# Data-Warehousing_with_AWS-Redshift_and_Azure

## INTRODUCTION:

### Amazon Redshift Data Warehouse:

Amazon Redshift data warehouse is a feature that is fully managed, fast, petabyte scale which makes this product cost-effective and simple to insight all our data and information with the use of the existing enterprise business intelligence tools.

#### Features of Amazon Redshift:

    1. Scalable: In just a few clicks on the AWS Management Console or API calls, one can easily change the type or the number of nodes in our data warehouse whenever there is a change in requirement, capacity or performance. DS (Dense Storage) nodes are used to allow users to create big data warehouses using HDDs (Hard Disk Drives) for a minimalistic cost. There is also DC (Dense Compute) nodes that allows customers to create very efficient and high-performance data warehouse using fast and large amounts of RAM, CPUs and SSDs (Solid State Disks).

    2. Fast an Optimised Data Warehousing: AWS Redshift uses efficient techniques with variety of innovations to obtain a very high level in terms of query performance on large datasets which range from hundred gigabytes to petabytes and sometimes maybe more. It is not possible for traditional data warehouses to process an optimized query with such large volumes of data. It also has a MPP(Massive Parallel Processing) architecture, distributing SQL operations and parallelizing techniques to take maximum advantage of all available resources.

    3. Installed in Minutes: With some simple API calls or few clicks on the console, the user can easily create a cluster, specifying the underlying node, type, size and security profile. It also has the feature to provision your nodes and handle connections between them.

    4. Fault Tolerant: There are a wide range of features that improve the reliability of customer’s data warehouse cluster. Whatever written to a node in any cluster is automatically replicated to other nodes and the data gets continuously backed up to Amazon S3 cluster.

#### Why to choose Amazon Redshift in an Enterprise?

There are several factors which help in choosing Amazon Redshift as your product. It is based on a SQL data warehouse which also uses standard JDBC and ODBC connections. The drivers are easy to download though the Connect Client tab of its Console. The Redshift could also be integrated with other services of the AWS and it also has some build-in commands in order to load data and information in parallel to each node from DynamoDB, Amazon S2 or EC2.

### Microsoft Azure SQL Data Warehouse

Microsoft Azure SQL Data Warehouse is an enterprise-level database which is capable of handling large amounts of all kinds of data be it relational, big data etc. It is Microsoft’s first cloud data warehouse which has SQL features including the capacity to decrease or increase within seconds. Due to the inclusion of SQL into Azure, it is quick to deploy. Also, this feature is fully managed and doesn’t bother us to spend times on issues such as software back-ups, maintenance and patching.

#### Features of Microsoft Azure:

This SQL data warehouse uses MPP (massive parallel processing) architecture of Microsoft which is exclusively designed to process highly required on-premise organization data warehouses. Azure data warehouse architecture breaks this up in three main components which are mentioned as follows:

    1. Storage: It uses Azure Blob storage for storing of Data. Compute Nodes interact with information and data, and read and write data directly from Blobs. The limitless storage ability allows us to scale storage automatically and expand transparently without computation.

    2. Compute Nodes: These are same as control node. This feature of Azure is powered using SQL. The main task of these compute nodes is to act as the computing power for the service. Whenever some data is loaded into the SQL data warehouse, it will be equally distributed across the service nodes. Then these nodes receive a command and the  architecture  breaks  the  data  into  fragments  for  each  node,  and  finally  these compute nodes operate over their relevant fragmented data.

    3. Data Movement Service: This is the final component for keeping everything together in the data warehouse. Data Movement Service allows to communicate, process and transfer data to all the nodes with the help of control compute nodes.

#### Why choose Azure Data Warehouse:

    1. Azure being an enterprise-level SQL data warehouse increases the massive scale APS (Analytics Platform System) into the cloud that helps in extending the SQL Server family of products and services.

    2. This Data Warehouse can scale storage and compute by itself, so the clients have to pay only for the query performance they need. Some other data warehouses take hours or days to scale in terms of additional computing power. It is much easier to forecast the costs as compared to other offerings.

    3. Microsoft Azure also offers a dynamic pause feature which enables the users to efficiently optimize the utilization of resources and computing infrastructure by doing the ramping down while persisting the data. When compared to other warehouses, they need to back up the existing data, delete the existing cluster and generate a new cluster upon resume and restore the data as well.


## CREATION OF DATAWAREHOUSE IN AWS REDSHIFT

The dataset in Redshift ranges from 100s of gigabytes to petabytes. The process of creating a data warehouse in AWS Redshift includes launching of the compute resources called nodes and when these nodes are organised into groups called cluster. After that you can process your queries.

Following are the steps performed to setup Amazon Redshift:

    1. Create IAM Role and User within Identity Access Management service of Amazon.

        ◦ Create Access key within IAM User and its automatically generated password.
