#    **Attendance API Documentation**

| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 25-04-2025  | 25-04-2025 | V1  | Vardaan Saxena |     Internal Review    | Pritam    |



**Table of Contents**

-   [**Overview**](#overview)
-   [**Purpose**](#purpose)
-   [**System Requirements**](#related-resources)
-   [**Dependency**](#related-resources)
-   **[Architecture](#related-resources)**
-    [**Flow Diagram**](#related-resources)
-   **[Components](#components)**
    -   [PostgreSQL](#postgresql)[Redis](#redis)
    -   [Poetry](#poetry)
    -   [Liquibase](#liquibase)
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


# **Purpose**

This document provides detailed information about the Attendance Microservices, which is a Python-based API designed to manage attendance efficiently.
#

### Related Resources
**For detailed information of system requirements, architecture, flow diagram, and installation steps, please refer to the following resources**
| Link         | Description         |
|--------------|------------------------|
| [Attendance API]() |POC of Attendance records and data flow.| 


# **Components**

-   [PostgreSQL](https://www.postgresql.org/)

-   [Redis](https://redis.io/)

-   [Poetry](https://python-poetry.org/)

-   [Liquibase](https://docs.liquibase.com/)

## **PostgreSQL**

PostgreSQL is a great choice for managing attendance data because it handles organized data well, ensures the data is safe and correct through ACID (Atomicity, Consistency, Isolation, and Durability), and can grow as your project gets bigger. It also makes it easy to analyze attendance and create reports.

**Why?**

 | **Why It's Used**      | **Details**                                                                                              |
|------------------------|----------------------------------------------------------------------------------------------------------|
| Relational Database    | PostgreSQL is a free and safe database that keeps your data correct and organized.                        |
| Handling Attendance    | It works well for storing things like users, dates, and events, and can do complicated searches easily.    |
| Scalability            | It can grow with your project as more data comes in, making it perfect for big projects.                   |



## **Redis**

Redis (**RE**mote **DI**ctionary **S**erver) is good for this project because it keeps data in memory, making the app faster by not needing to fetch it from the database every time. It helps quickly manage user sessions and send real-time updates, like when an attendance record is changed. Unlike other databases, Redis is much faster for handling temporary data like sessions or cached records

**Why?**

| **Why It's Used**      | **Details**                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Caching**            | Stores frequently accessed data, like attendance records, in memory to make the app faster. |
| **Session Management** | Keeps track of user sessions quickly, so users stay logged in and their actions are stored. |
| **Real-Time Updates**  | Sends instant updates to users, like notifying them when their attendance record is updated. |




## **Poetry**

Poetry makes handling Python dependencies super simple and clean. It takes care of all the libraries your project needs, keeps everything in sync across different setups, and even makes it easier to share or deploy the app. For a project like this, it helps maintain a smooth and consistent development flow.


**Why Poetry Works Well**

| **Feature**              | **What It Helps With**                                                                 |
|--------------------------|----------------------------------------------------------------------------------------|
| **Clean Dependency Management** | Keeps track of all required Python packages and installs them in an organized way.      |
| **Easy Project Packaging**     | Simplifies the process of bundling the app so it’s ready to share or deploy.             |
| **Consistent Environments**    | Makes sure everyone working on the project uses the same versions, avoiding conflicts.    |


## 

## **Liquibase**

In this Attendance Application, Liquibase is used to handle all database changes in a clean and trackable way. It maintains a changelog file that logs every schema update — so the entire team stays in sync with the same database structure. Plus, if something breaks, it’s easy to roll back. Whenever new features are added, Liquibase ensures the database gets updated automatically without manual work.

**Why Liquibase?**

| **Feature**              | **How It Helps**                                                                                  |
|--------------------------|---------------------------------------------------------------------------------------------------|
| **Database Change Tracking** | Keeps a record of all database changes, so we know exactly what's been modified and when.         |
| **Version Control for DB**   | Just like Git tracks code, Liquibase tracks schema changes — keeping everyone on the same version. |
| **Smooth CI/CD Integration** | Fits well into the deployment pipeline — the database gets updated automatically with each release. |


# **Conclusion**

The Attendance uses PostgreSQL for secure data storage, Redis for fast data access, Liquibase for smooth database updates, and Poetry for managing dependencies. These technologies work together to create a fast, scalable, and reliable system for managing attendance data. The API is designed to be efficient and easy to maintain, making it suitable for real-world use.

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

