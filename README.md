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
        
  ![image](https://user-images.githubusercontent.com/43326618/58909199-6971d000-870a-11e9-92bf-bdc3e8f09a28.png)
  
  
    2. Launch Redshift Cluster:

        ◦ Sign in to AWS Management console.

        ◦ Within Database service of AWS, select Amazon Redshift.

        ◦ Select Launch Cluster

        ◦ Create Cluster by setting the following details: Cluster identifier name,Database name (if left blank, by default it takes “dev” as database name), port number (by default it takes the empty port of your system i.e. 5439), Master Username and Password Continue.

    • Select Node Type (from options: dc2.large, dc2.8xlarge, dc1.large, dc1.8xlarge, ds2.xlarge, ds2.8xlarge). For 2 months free trial, you can use dc2.large.

    • After selecting node type according to you requirement, you will be able to see the size of CPU, Memory, and Storage.

    • Set IO performance as Moderate.

    • We can select Cluster type as Multi Node or Single Node depending on your requirement. (For free trial choose single node)

    • Select the no of compute nodes and Continue.
    
   
![image](https://user-images.githubusercontent.com/43326618/58909449-10566c00-870b-11e9-9c18-b87ff03140cd.png)

    • For free trial keep VPC, cluster subnet group, publically accessible: Yes, IP address enhanced VPC routing etc. as default value.

    • Select an Available IAM role that has been created within IAM service of Amazon.

    • Launch Cluster.
    
 ![image](https://user-images.githubusercontent.com/43326618/58909493-2bc17700-870b-11e9-8217-b52275fedc9f.png)
   
   
    3. Now create S3 bucket within S3 storage section of AWS and then connect it to S3 browser by using the Access key and its corresponding automatically generated password. Upload file or data in S3 bucket.
    
![image](https://user-images.githubusercontent.com/43326618/58909558-54e20780-870b-11e9-90e1-ee4b50bfb19f.png)


    4. Download SQL Workbench. Connect it to Amazon Redshift (Download Amazon Redshift JDBC or ODBC driver).

    5. Create table with particular column and create database in S3 and use specific “copy command” to copy table to database.
    Eg: copy table_name from 's3://cloudproject010203/Gapminder_All_Time.csv' CREDENTIALS 'aws_iam_role=arn:aws:iam::59727314111:role/dev' delimiter ',' IGNOREHEADER 1
    
![image](https://user-images.githubusercontent.com/43326618/58909663-91156800-870b-11e9-8633-1a2e39eb38d0.png)


    6. Various queries can be performed on database and generate data analysis reports for enterprise.

##### Execution Time: Table creation= 10sec,Copying Records= 20sec for 13000 rows of data.

### Azure Process for Databases and Data warehousing



#### Azure Portal - https://portal.azure.com



1.  Creating SQL Server


    • Created a SQL Server “cloudproject-674”.

    • Resource group name “DCU” to select the storage subscriptions and options as – blob/Table. Resource group lists all the services selected for the particular project.
    
![image](https://user-images.githubusercontent.com/43326618/58909868-0da84680-870c-11e9-86e1-bf1c803f1688.png)
![image](https://user-images.githubusercontent.com/43326618/58909907-257fca80-870c-11e9-8df7-b6e6c7b79d88.png)

Created database with price tier as basic, Data warehouse Gen1DW400 and Data warehouse of Gen2:DW1000c.

![image](https://user-images.githubusercontent.com/43326618/58910011-6546b200-870c-11e9-93c4-1b355a8e710f.png)

There are only Microsoft platform-based tools available on azure to perform different tasks on Azure Datawarehouse.

![image](https://user-images.githubusercontent.com/43326618/58910073-91623300-870c-11e9-941a-6017b88cb065.png)

2.  Razor SQL

    • Used 30-days trial RazorSQL to connect to Azure Databases and Data warehouse from local desktop.
    o  Enabled local IP address to access the azure portal.
    o Gave Azure SQL Server name “cloudproject-674.database.windows.net”. 
    o Provided the required drivers class and driver URL.
 ![image](https://user-images.githubusercontent.com/43326618/58910166-bd7db400-870c-11e9-9891-09e7313fab1a.png)
 
     • Imported the csv file into the database, created a table and generated scripts for inserts.

     • Checked the data types, handled constrains and null values.
     
![image](https://user-images.githubusercontent.com/43326618/58910286-0afa2100-870d-11e9-8fe2-e475266efa23.png)

3.  Azure SQL Querying on Portal
	checked on Azure portal and confirmed successful import.
    • Queried the database and it returned 7191 rows in 6s
 
![image](https://user-images.githubusercontent.com/43326618/58910412-5a405180-870d-11e9-89e9-328504b71e5e.png)

#### COMPARISON AND CONCLUSION:

##### PRICING:

On Comparison it was found that Microsoft Azure is cheaper from Amazon Redshift in terms services offered.

##### SPEED:

It was found that query execution in Microsoft Azure is faster when compared to Amazon Redshift. For 10000 rows, a load query in Microsoft Azure takes 10 seconds whereas Amazon Redshift takes 35 seconds for the same.

##### CROSS PLATFORM DEPENDANCY:

It can be concluded that Amazon Redshift is better in terms of Cross Platform Dependency. As mentioned earlier that working on Azure on an IOS Based Operating System proved to be challenging whereas Amazon Redshift has no such limitations.

  
