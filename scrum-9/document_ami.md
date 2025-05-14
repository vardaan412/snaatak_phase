
# **Documentation: Amazon Machine Image (AMI)**

<div align="center">
  <img src="https://tse4.mm.bing.net/th?id=OIP.MbxexNZdw7lRXyq4o8WoZgHaDJ&pid=Api&P=0&h=180" alt="Ansible Logo" width="40%"/>
</div>

| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 12-05-2025  |  | V1.0  | Vardaan Saxena |     Internal Review    | Pritam    |


## **Table of Contents**
- [Introduction](#introduction)
- [What is an AMI?](#what-is-an-ami)
- [Why use AMIs?](#why-use-amis)
- [Workflow Diagram](#workflow-diagram)
- [Advantages](#advantages)
- [POC](#poc)
- [Best Practices](#best-practices)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)



## **Introduction**
Amazon Machine Image (AMI) is a fundamental building block in AWS EC2 provisioning. It allows users to package the operating system, application code, libraries, and dependencies into a reusable template for launching instances.



## **What is an AMI?**
An AMI is a snapshot of an EC2 instance that can be used to launch multiple instances with identical configurations. It provides a scalable, secure, and repeatable deployment approach for applications and environments.



## **Why use AMIs?**
Using AMIs eliminates repetitive setup steps and ensures:

- Consistent environments across multiple EC2 instances
- Faster provisioning
- Improved security and compliance
- Reduced manual errors in deployments



## **Workflow Diagram**

<div align="center">
  <img src="https://github.com/vardaan412/snaatak_phase/blob/a1282171d06b68d76c18f2b5c6f997c160dc2391/AMI/ChatGPT%20Image%20May%2013%2C%202025%2C%2009_20_41%20PM.png" width="70%"/>
</div>


## **Advantages**

* **Speed:** Faster provisioning of identical environments
* **Consistency:** Reduced configuration drift
* **Automation:** Easier to integrate into CI/CD pipelines
* **Rollback:** Quickly revert to a known good state



## **POC**

> **NOTE:**  
> We have fully set up the Attendance API on the EC2 instance and created its Golden AMI as per the official process.  
> Refer to the official POC documentation for complete steps: [Attendance AMI Official POC](https://github.com/vardaan412/snaatak_phase/blob/main/scrum-9/AMI.md?plain=1) 



## **Best Practices**

* Always create AMIs from clean, updated, and tested instances.
* Remove temporary files, credentials, and cache before creating the image.
* Use proper tagging and versioning for each AMI.
* Automate AMI creation as part of your CI/CD pipeline when possible.
* Regularly review and delete outdated or unused AMIs to save cost.



## **Conclusion**

Amazon Machine Images offer a scalable and efficient way to provision cloud infrastructure. By encapsulating your entire environment into an AMI, you ensure faster deployments, consistent configurations, and simplified rollbacks. This documentation and POC together demonstrate how to implement and benefit from AMIs in real-world scenarios.



## **Contact Information**

| Name           | Email Address                                                                         |
| -------------- | ------------------------------------------------------------------------------------- |
| Vardaan Saxena | [vardaan.saxena.snaatak@mygurukulam.co](mailto:vardaan.saxena.snaatak@mygurukulam.co) |



## **References**

| Description                | Link                                                                                      |
|---------------------------|-------------------------------------------------------------------------------------------|
| **AWS AMI Documentation**      | [AWS AMI Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html)            |
| **Create AMI in AWS**          | [Create AMI in AWS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami.html)     |
| **Amazon EC2 Getting Started** | [Amazon EC2 Getting Started](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html) |



