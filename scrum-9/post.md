
# **POSTGRES INSTALLATION POC**


<p align="center">
  <img width="415" alt="image" src="https://github.com/user-attachments/assets/9c8ecd07-97ce-492f-856c-9e5fc7b3a3f7" />
</p>



| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 25-04-2025  | 25-04-2025 | V1  | Vardaan Saxena |     Internal Review    | Pritam    |


# **Table of Contents**                         

-   [Introduction]( #introduction)        
-   [Prerequisite]( #prerequisite)
-   [Important Port](#important-port) 
-   [Step-by-Step Setup Guide](#step-by-step-setup-guide)
-   [Conclusion](#conclusion)
-   [Contact Information](#contact-information)  
-   [References](#references)                               



# **Introduction**

PostgreSQL is a relational SQL database, which means it stores data in rows and columns. It was developed in 1986 by the University of California, Berkeley. It is widely used by many companies such as Apple, Cisco, Fujitsu, Instagram, Spotify, Skype, etc.
**"Additionally, we are using PostgreSQL in our project for the Attendance API."**

# **Prerequisite**


| Dependency          | Description                                                       |
|---------------------|-------------------------------------------------------------------|
| Python              | Recommended  3.6 or later                  |


# **Important-Port**
 | 5432 |


## Step-by-Step Setup Guide 

### Install Postgres
We can install PostgreSQL in Window , Ubuntu and Mac etc. But As per our documentation we are moving forward with **ubuntu**.

#### STEP 1 : install from [official website](https://www.postgresql.org/download/)

To install postgres directly with apt command

```
sudo apt install postgresql postgresql-contrib -y
```



#### STEP 2 : To verify the installation and check the version of postgres

```
psql --version
```




#### STEP 3 :  To start, enable, and check the status of PostgreSQL
```
sudo systemctl start postgresql
```
```
sudo systemctl enable postgresql
```
```
sudo systemctl status postgresql
```





#### STEP 4 : for switching into postgres user
```
sudo -i -u postgres
```

#### STEP 5 : To go into postgres shell

```
psql
```




#### STEP 6 : To create a database we can do 

```
create database database_name
```
For example, if you want to create a database called `my_new_db`, you would run:
```
CREATE DATABASE my_new_db;

```


### To list the database 

```
\l
```



### To delete a particular database

```
drop database database_name
```



# **Conclusion**
PostgreSQL is an ideal database for microservices due to its reliability, scalability, and support for complex queries. It helps manage data efficiently across distributed services, ensuring consistency, high performance, and flexibility as the system grows. Its advanced features make it a powerful choice for handling large volumes of data in microservice architectures.

# **Contact Information**

| **Name**    | **Email address**         |
|-------------|---------------------------|
| Vardaan Saxena | vardaan.saxena.snaatak@mygurukulam.co    |


# **References**

| No. | Reference                                                                                           | Description                                 |
|-----|-----------------------------------------------------------------------------------------------------|---------------------------------------------|
| 1   | 🌐 [PostgreSQL Official](https://www.postgresql.org/download/linux/ubuntu/)                         | Visit official PostgreSQL website.          |



