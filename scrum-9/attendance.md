
#    **Attendance API Documentation**


<div align="center">
  <img src="https://th.bing.com/th/id/R.63da76b44d7b83f701e38cd8f5af90cb?rik=j1X89wVk4PJb4Q&riu=http%3a%2f%2fattendancetimeclock.com%2fcdn%2fshop%2ffiles%2fAttendancetime_time_clock_logo_c4bdf57b-a3bc-4e65-835b-8e99cd5ab1fc.png%3fv%3d1716661528&ehk=uPHyG2ryKv8EW%2by6ZmMR2U49Eim%2fo0lz9R%2feZTvvq%2bI%3d&risl=&pid=ImgRaw&r=0" alt="Ansible Logo" width="40%"/>
</div>

| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 25-04-2025  | 28-04-2025 | V1.1  | Vardaan Saxena |     Internal Review    | Pritam    |



**Table of Contents**

-   [**Overview**](#overview)
-   [**Purpose**](#purpose)
-   **[Components](#components)**
    -   [PostgreSQL](#postgresql)[Redis](#redis)
    -   [Poetry](#poetry)
    -   [Liquibase](#liquibase)
    -   [Gunicorn](#gunicorn)
-   [**Conclusion**](#conclusion)
-   [**Contact Information**](#contact-information)
-   **[References](#references)**



# **Overview**

This project aims to develop an Attendance API that connects with a **PostgreSQL** database for data storage, utilizes **Redis** for fast caching, and handles database migrations using **Liquibase**. All Python dependencies are managed efficiently through **Poetry**.

**Tech Stack Used**

1. **PostgreSQL** – A powerful relational database used to store all the attendance-related information.

2. **Redis** – An in-memory key-value data store that helps with quick data access through caching.

3. **Poetry** – A modern Python dependency management tool used to maintain and install project packages.

4. **Liquibase** – A tool for managing database versioning and schema updates in a structured and reliable way.

5. **Gunicorn** – A Python WSGI HTTP server used to serve the application in production, enabling efficient request handling.


# **Purpose**

This document provides detailed information about the Attendance Microservices, which is a Python-based API designed to manage attendance efficiently.
#

### Related Resources
**For detailed information of system requirements, architecture, flow diagram, and installation steps, please refer to the following resources**
| Link         | Description         |
|--------------|------------------------|
| [Attendance API](https://github.com/snaatak-Downtime-Crew/Documentation/tree/SCRUMS-76-SHIVANI/ot-ms-understanding/attendance/poc) |POC of Attendance records and data flow.| 


# **Components**

-   [PostgreSQL](https://www.postgresql.org/)

-   [Redis](https://redis.io/)

-   [Poetry](https://python-poetry.org/)

-   [Liquibase](https://docs.liquibase.com/)

-   [Gunicorn](https://gunicorn.org/) 

## **PostgreSQL**

PostgreSQL is a great choice for managing attendance data because it handles organized data well, ensures the data is safe and correct through ACID (Atomicity, Consistency, Isolation, and Durability), and can grow as your project gets bigger.


**For detailed information, look at this PostgreSQL PoC:**

| Link         | Description         |
|--------------|---------------------|
| [PostgreSQL API](https://github.com/snaatak-Downtime-Crew/Documentation/tree/SCRUMS-86-Vardaan/ot-ms-understanding/postgressql/poc) | PostgreSQL POC for attendance data management. |

## **Redis**

Redis speeds up the app by storing data in memory, making it ideal for managing user sessions and real-time updates like attendance changes. It's faster than traditional databases for temporary data.

**For detailed information, look at this Redis PoC:**

| Link         | Description         |
|--------------|---------------------|
| [Redis API](https://github.com/snaatak-Downtime-Crew/Documentation/tree/SCRUMS-84-PRINCE/ot-ms-understanding/redis/poc) | Redis PoC for managing user sessions and real-time attendance updates.|



## **Poetry**

Poetry simplifies managing Python dependencies, ensuring libraries are in sync and making sharing or deploying the app easier, maintaining a smooth development flow.


**For detailed information, look at this Poetry PoC:**

| Link         | Description         |
|--------------|---------------------|
| [Poetry API](https://github.com/snaatak-Downtime-Crew/Documentation/blob/prince_scrums_16/common_stack/application/python/poetry/sop/README.md) | Poetry PoC for managing Python dependencies and ensuring consistent development.|



## 

## **Liquibase**

In this Attendance Application, Liquibase is used to handle all database changes in a clean and trackable way. It maintains a changelog file that logs every schema update — so the entire team stays in sync with the same database structure. Plus, if something breaks, it’s easy to roll back. Whenever new features are added, Liquibase ensures the database gets updated automatically without manual work.

**Why Liquibase?**

| **Feature**              | **How It Helps**                                                                                  |
|--------------------------|---------------------------------------------------------------------------------------------------|
| **Database Change Tracking** | Keeps a record of all database changes, so we know exactly what's been modified and when.         |
| **Version Control for DB**   | Just like Git tracks code, Liquibase tracks schema changes — keeping everyone on the same version. |
| **Smooth CI/CD Integration** | Fits well into the deployment pipeline — the database gets updated automatically with each release. |


## **Gunicorn**
 
Gunicorn is a Python WSGI HTTP server that serves Python web applications in production. It helps handle multiple requests at once, making web apps faster and more efficient by connecting the app to a web server.

**For detailed information, look at this Gunicorn  PoC:**

| Link         | Description         |
|--------------|---------------------|
| [Gunicorn  API](https://github.com/snaatak-Downtime-Crew/Documentation/tree/main/common_stack/application/python/gunicorm/sop) | Gunicorn PoC for serving Python web applications in production. |


# **Conclusion**

The Attendance uses PostgreSQL for secure data storage, Redis for fast data access, Liquibase for smooth database updates, and Poetry for managing dependencies, and **Gunicorn** for serving the application in production. These technologies work together to create a fast, scalable, and reliable system for managing attendance data. The API is designed to be efficient and easy to maintain, making it suitable for real-world use.

#  **Contact Information**


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Vardaan Saxena | vardaan.saxena.snaatak@mygurukulam.co    |



# **References**

| No. | Reference                                              | Description              |
|-----|--------------------------------------------------------|--------------------------|
| 1   | 🌐 [PostgreSQL Official Site](https://www.postgresql.org) | Visit official website   |
| 2   | 🌐 [Redis Official Site](https://redis.io)              | Visit official website   |
| 3   | 🌐 [Liquibase Official Site](https://www.liquibase.org) | Visit official website   |
| 4   | 🌐 [Gunicorn Official Site](https://gunicorn.org)       | Visit official website   |
