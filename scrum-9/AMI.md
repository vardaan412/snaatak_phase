
#  **POC of AMI**

A Proof of Concept (POC) to demonstrate how to use a Golden AMI for creating pre-configured, production-ready environments with standardized application setup.



#  **Table of Contents**

- [Purpose](#purpose)
- [Pre-requisites](#pre-requisites)
- [Step-by-Step Installation Guide](#step-by-step-installation-guide)
- [Conclusion](#conclusion)
- [References](#references)
- [Contact Information](#contact-information)



#  **Purpose**

This POC showcases how to:

- Set up an EC2 instance with a working application
- Convert that EC2 instance into a Golden AMI
- Use that AMI to launch new instances with the application pre-installed
- Reduce setup time, ensure consistency, and improve security across deployments



#  **Pre-requisites**


To perform this POC, you should have:

- An AWS Account with permission to create EC2 instances and AMIs
- At least one EC2 instance running (recommended OS: Ubuntu, or any Linux EC2 of your choice)
- The EC2 instance must have internet access (either via public subnet or NAT)
- You should know how to set up a basic application on the EC2 instance  
  - This could be any app (your own or public), or even basic services like Nginx or Apache
- If it's a web application, your EC2 must have a Public IP or Elastic IP to make it accessible externally






##  **Step-by-Step Installation Guide**

#  **Step 1: Launch EC2 and Set Up Application**

- Launch an EC2 instance
- Connect to EC2 via SSH
- Install required dependencies and your application
* Start application and ensure it runs (you can access it via browser or curl depending on setup)

> **NOTE:**  
> We are using the Attendance API for this setup.  
> Refer to its [Attendance API official GitHub repository](https://github.com/your-org/attendance-api) for installation and usage instructions.

#  **Step 2: Create Golden AMI**

* Go to AWS EC2 Console
* Select the instance → Actions → Image → Create Image
* Provide:

  * Name: `Name_AMI`
  * Description (optional)
  * No reboot (optional if you’re okay with running services stopping)
* Note the AMI ID once it is created

#  **Step 3: Launch New EC2 Using Golden AMI**

* Go to EC2 → AMIs → Select your AMI → Launch Instance

* Select instance type, security group, key pair as required

* Once launched, the instance will already have:

  * All dependencies
  * Pre-installed application
  * Ready-to-use environment

* Connect via SSH and verify application is up and running



#  **Conclusion**

* Golden AMIs help you avoid repetitive setup steps.
* Ensures fast, consistent, and reliable infrastructure deployments.
* Reduces patching and human error.
* This POC verifies the value of AMI-based application packaging.







# **References**

| Description                  | Link                                                                 |
|-----------------------------|----------------------------------------------------------------------|
| **AWS AMI Documentation**       | [AWS AMI Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html) |
| **How to Create AMI in AWS**    | [How to Create AMI in AWS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami.html) |
| **Amazon EC2 Getting Started**  | [Amazon EC2 Getting Started](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html) |


#  **Contact Information** 
|Name|Email Address|
|:---:|:---:|
|**Vardaan Saxena**|vardaan.saxena.snaatak@mygurukulam.co |


