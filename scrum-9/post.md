


# **POSTGRESQL INSTALLATION POC**


<p align="center">
  <img width="415" alt="image" src="https://github.com/user-attachments/assets/9c8ecd07-97ce-492f-856c-9e5fc7b3a3f7" />
</p>



| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 25-04-2025  | 28-04-2025 | V1.1  | Vardaan Saxena |     Internal Review    | Pritam    |


# **Table of Contents**                         

-   [Introduction]( #introduction)
-   [System Requirements](#system-requirements)     
-   [Important Port](#important-port) 
-   [Step-by-Step Setup Guide](#step-by-step-setup-guide)
-   [Conclusion](#conclusion)
-   [Contact Information](#contact-information)  
-   [References](#references)                               



# **Introduction**

PostgreSQL is a relational SQL database, which means it stores data in rows and columns. It was developed in 1986 by the University of California, Berkeley. It is widely used by many companies such as Apple, Cisco, Fujitsu, Instagram, Spotify, Skype, etc.
**"Additionally, we are using PostgreSQL in our project for the Attendance API."**


# **System Requirements**

| Component        | Minimum Requirement                           |
|------------------|-----------------------------------------------|
| OS               | Ubuntu (preferred) or Linux-based             |
| Disk Space       | 8 GB                                          |
| RAM              | 2 GB                                          |
| Processor        | 1 GHz Single-core  |
| Instance Type    | t2.medium or higher       |


# **Important-Port**

| Port | Description           |
|------|------------------------|
| 5432 | PostgreSQL Database Port |



## Step-by-Step Setup Guide 

### Install Postgres
We can install PostgreSQL in Window , Ubuntu and Mac etc. But As per our documentation we are moving forward with **ubuntu**.

#### STEP 1 : install from [official website](https://www.postgresql.org/download/)

To install postgres directly with apt command

> Before proceeding, it's **highly recommended** to follow the update instructions from the official documentation.  
> 👉 **Follow Step 1 here**: [Software Install Commands](https://github.com/snaatak-Downtime-Crew/Documentation/tree/main/common_stack/operating_system/ubuntu/sop/softwaremanagement#3-Install-a-Software)
>
> ---
```
sudo apt install postgresql postgresql-contrib -y
```
<p align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/7904da0391e4b897f110188cfc770f0130876e63/Postgre/1.png" alt="CI Workflow" />
</p>

---



#### STEP 2 : To verify the installation and check the version of postgres

```
psql --version
```

<p align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/7904da0391e4b897f110188cfc770f0130876e63/Postgre/2.png" alt="CI Workflow" />
</p>

---


#### STEP 3 :  To start, enable, and check the status of PostgreSQL

> 👉 **Follow all here**: [Software Start Enable Status etc Commands](https://github.com/snaatak-Downtime-Crew/Documentation/tree/main/common_stack/operating_system/ubuntu/sop/services#systemctl-commands-explained)
>
> ---


```
sudo systemctl status postgresql
```


<p align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/7904da0391e4b897f110188cfc770f0130876e63/Postgre/3.png" alt="CI Workflow" />
</p>

---


#### STEP 4 : for switching into postgres user
```
sudo -i -u postgres
```

<p align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/7904da0391e4b897f110188cfc770f0130876e63/Postgre/4.png" alt="CI Workflow" />
</p>

---


#### STEP 5 : To go into postgres shell

```
psql
```

<p align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/7904da0391e4b897f110188cfc770f0130876e63/Postgre/5.png" alt="CI Workflow" />
</p>

---


#### STEP 6 : To create a database we can do 

```
create database database_name
```
For example, if you want to create a database called `my_new_db`, you would run:
```
CREATE DATABASE my_new_db;

```
<p align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/7904da0391e4b897f110188cfc770f0130876e63/Postgre/6.png" alt="CI Workflow" />
</p>

---

### To list the database 

```
\l
```

<p align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/7904da0391e4b897f110188cfc770f0130876e63/Postgre/7.png" alt="CI Workflow" />
</p>

---

### To delete a particular database

```
drop database database_name
```

<p align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/7904da0391e4b897f110188cfc770f0130876e63/Postgre/8.png" alt="CI Workflow" />
</p>

---

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
