# **POC: Java Static Code Anaylysis**

<div align="center">
  <img src="https://github.com/user-attachments/assets/aa106778-c90e-4e17-9d03-7f61bdf672a2" alt="Ansible Logo" width="40%"/>
</div>

| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 12-05-2025  |  | V1.0  | Vardaan Saxena |     Internal Review    | Pritam    |

# Table of Contents
- [Introduction](#introduction)
- [Pre-requisites](#pre-requisites)
- [Security ports](#Security-ports)
- [Step-by-step Installation](#step-by-step-installation)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [ References](#references)


# Introduction 
This document will guide you through a Proof of Concept (PoC) for setting up Static Code Analysis. We will cover the necessary prerequisites, build time and run time dependency, as well as the how to resolve the error.


# Pre-requisites 


| **Specification**      | **Details**         |
|-------------------------|---------------------|
| **Operating System**    | Ubuntu 22.04      |
| **CPU**                | 2 vCPU             |
| **Hard Disk**             | 20 GB              |
| **RAM**                | 4 GB               |



# Security ports

| **Port** | **Protocol** | **Source Side**    | **Destination Side** | **Use Case**                     |
|----------|--------------|--------------------|-----------------------|-----------------------------------|
| 22       | TCP          | Any                | Server               | SSH Access for remote login      |
| 5432     | TCP          | Application Server | Database Server      | PostgreSQL database access       |
| 9000     | TCP          | Any                | Server               |  SonarQube |



# **Step-by-step Installation**


## **Step 1. Update System Packages**

>
>  **Update system**  
> 👉 **Follow Step 3 here**: [System update Commands](https://github.com/snaatak-Downtime-Crew/Documentation/blob/main/common_stack/operating_system/ubuntu/sop/commoncommands/README.md#1-basic-system-commands)
>
> 

## **Step 2. Java installation**

>
>  **Java installation**  
> 👉 **Follow Steps here**: [Java installation Commands](https://github.com/snaatak-Downtime-Crew/Documentation/blob/main/common_stack/application/java/installation/script/README.md#bash-script)
>
> 

## **Step 3. Install and configure PostgreSQL**


#### 1. Install and start the Postgresql.

>
>  **Install and start  Postgresql**  
> 👉 **Follow Steps here**: [Postgresql Commands](https://github.com/snaatak-Downtime-Crew/Documentation/tree/main/common_stack/software/postgresql/installation#step-by-step-setup-guide)
>
> 

#### 2. Create a new database user to manage the sqube database
```
createuser sona
```


#### 3. Log in to the PostgreSQL database to proceed with database operations.
```
psql
```

![image](https://github.com/user-attachments/assets/9b2fb362-3a73-4009-b827-3fef92f2886b)


 
#### 4. Set a strong password for the “sona” user. Use a password

```
ALTER USER sona WITH ENCRYPTED password 'Sona#123';
```

#### 5. Create a sqube database and assign the ownership to the “sona” user.
```
CREATE DATABASE sqube OWNER sona;
```
Grant all privileges on the “sqube” database to the “sona” user

```
GRANT ALL PRIVILEGES ON DATABASE sqube to sona;
```
![image](https://github.com/user-attachments/assets/43a19949-613c-48ea-958f-aa41c4e644af)

#### 6. To verify the creation of the database, use the following command
```
\l
```
To verify the creation of the database user, use the following command:
```
\du
```
![image](https://github.com/user-attachments/assets/0bea53d0-ed81-48ec-a55e-d99ca1ed0f26)

#### 7. To exit the PostgreSQL command-line interface, use the following command:
```
\q
```
#### 8.  To return to your non-root sudo user account, use the following command:
```
exit
```
![image](https://github.com/user-attachments/assets/7abfa498-bd09-49af-8879-12b3437aed30)



## **Step 4. Downloading and Installing SonarQube**

Install the zip utility, required for extracting the SonarQube files
```
sudo apt install zip -y
```
![image](https://github.com/user-attachments/assets/b7a5db7b-9b05-487e-9092-0eff78c47532)



## **Step 5. installing the latest version of SonarQube 10.4 Community Edition (free version)**

```
sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-10.4.1.88267.zip
```

![image](https://github.com/user-attachments/assets/e8c2fd40-6589-4f0c-950e-da10bbf989bb)


## **Step 6. Move the unzipped files to the /opt/sonarqube directory**

```
sudo unzip sonarqube-10.4.1.88267.zip
sudo mv sonarqube-10.4.1.88267 sonarqube
sudo mv sonarqube /opt/
```

## **Step 7. Setting Up SonarQube: Adding Group and User**

```
sudo groupadd sona
sudo useradd -d /opt/sonarqube -g sona sona
```
![image](https://github.com/user-attachments/assets/ca173ef6-0730-4100-a8b6-8a1a59e59b02)



## **Step 8. Grant the “sona” user access to the /opt/sonarqube directory**

```
sudo chown -R sona:sona /opt/sonarqube
```

![image](https://github.com/user-attachments/assets/61b774fd-6e27-42e0-bb35-c4ebd6a03aa4)



## **Step 9. Edit the SonarQube configuration file located**

```
sudo nano /opt/sonarqube/conf/sonar.properties
```


## **Step 10. Uncomment the following lines in the SonarQube configuration file**

```
sonar.jdbc.username=sona
sonar.jdbc.password=password
sonar.jdbc.url=jdbc:postgresql://localhost:5432/sqube
```
![image](https://github.com/user-attachments/assets/2d051074-3552-45fd-8e2b-5d13b8d45b27)


## **Step 11. To edit the SonarQube script file**
```
sudo nano /opt/sonarqube/bin/linux-x86-64/sonar.sh
```


## **Step 12. Select the branch you want to merge**

```
RUN_AS_USER=sona
```
![image](https://github.com/user-attachments/assets/d74ff63b-e3c0-495b-8f83-5fe514fc4929)


## **Step 13. Create a new service file using a text editor**
```
sudo nano /etc/systemd/system/sonar.service
```


## **Step 14. Check for merge conflicts after creating the pull request, It’s now ready for review**

```
[Unit]
Description=SonarQube service
After=syslog.target network.target
[Service]
Type=forking
ExecStart=/opt/sonarqube/bin/linux-x86-64/sonar.sh start
ExecStop=/opt/sonarqube/bin/linux-x86-64/sonar.sh stop
User=sona
Group=sona
Restart=always
LimitNOFILE=65536
LimitNPROC=4096
[Install]
WantedBy=multi-user.target
```

![image](https://github.com/user-attachments/assets/af10bcfb-cfdc-4bf1-8015-0304377c063a)


## **Step 15. Enable the SonarQube service to start at boot**

```
sudo systemctl enable sonar
```


## **Step 16. start the SonarQube service**

```
sudo systemctl start sonar
```

```
sudo systemctl status sonar
```
![image](https://github.com/user-attachments/assets/4f138b22-9d7b-460e-a7fb-50a4b8285a97)



## **Step 17. To edit the sysctl configuration file**

```
sudo nano /etc/sysctl.conf
```


## **Step 18. Add the following lines to the sysctl configuration file (/etc/sysctl.conf)**

```
vm.max_map_count=262144
fs.file-max=65536
ulimit -n 65536
ulimit -u 4096
```

![image](https://github.com/user-attachments/assets/7cfcf710-2856-4438-9e13-bcc278d37d63)


## **Step 19. To apply the changes, reboot the system**
```
sudo reboot
```


## **Step 20. Access SonarQube in a web browser by entering your server’s IP address followed by port 9000**

```
http://100.26.240.39:9000
```
## **Step 21. Log in to SonarQube using the username “admin” and password “admin”**
![image](https://github.com/user-attachments/assets/aceb6217-a3e7-474d-a903-3f9d3bfbba08)

Once logged in, SonarQube will prompt you to change your password. Enter the current password “admin” and then enter your new password twice as prompted.

![image](https://github.com/user-attachments/assets/658677aa-d66c-4b3d-8876-0e11ebf9bc6b)

## **Step 22. Go to SonarQube and select the project**

![image](https://github.com/user-attachments/assets/170adf86-92c9-48a0-b5b5-af15d1502929)

## **Step 23. Create a Local Project: Set up a new or existing project on your machine**

![image](https://github.com/user-attachments/assets/0b49d923-61a7-4120-ae5f-7558dc8c0d3c)

## **Step 24. Configure the Project: Prepare your project for analysis by configuring the necessary files**
![image](https://github.com/user-attachments/assets/76d79553-2d6a-41ab-852a-b4ee40d505be)

## **Step 25. Analysis your project which you want**

![image](https://github.com/user-attachments/assets/1da40957-0508-43c9-89e7-3916c6dd4feb)

## **Step 26. Generate Token: Create an authentication token in SonarQube**

![image](https://github.com/user-attachments/assets/8a2cc014-c67c-437c-b045-509adb3a0765)

## **Step 27. Copy the Token: Copy the generated SonarQube token to use for authentication when running the SonarScanner**

![image](https://github.com/user-attachments/assets/90fde3fa-0b9e-46bc-9f9f-8e474637e604)

## **Step 28. Analyze your project** 

![image](https://github.com/user-attachments/assets/8b835153-c969-4c89-b066-5789850c98ea)

## **Step 29.Run Analyze on your project**
![image](https://github.com/user-attachments/assets/5ac3feea-4186-4935-a3a7-e41c2dd8eecb)

## **Step 30.Paste the scan command**

![image](https://github.com/user-attachments/assets/2f271634-5d44-421f-b3f3-c6dc526932e3)

## **Step 31. After sucessfully run command**

![image](https://github.com/user-attachments/assets/900d6aa0-946d-41cf-bb16-4ba997ca5039)

## **Step 32. Result**
![image](https://github.com/user-attachments/assets/abcbbf30-ba80-4076-a239-17bf858ef516)



# **Conclusion**

Static code analysis tools in Java help identify issues early, improving code quality, security, and maintainability, which reduces long-term costs. However, they should be paired with dynamic analysis and other testing methods for comprehensive code quality.

#  **Contact Information**

| Name           | Email Address                                                                         |
| -------------- | ------------------------------------------------------------------------------------- |
| Vardaan Saxena | [vardaan.saxena.snaatak@mygurukulam.co](mailto:vardaan.saxena.snaatak@mygurukulam.co) |


# **References**

| **Description**                   | **Link**                                                                 |
|----------------------------------|--------------------------------------------------------------------------|
| Static Code Analysis Overview     | [BairesDev Blog](https://www.bairesdev.com/blog/java-static-code-analysis-tools/) |
| Static Code Analysis Tutorial     | [Baeldung Guide](https://www.baeldung.com/java-static-code-analysis-tutorial)      |



