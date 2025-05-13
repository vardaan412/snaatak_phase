
#  POC of AMI

A Proof of Concept (POC) to demonstrate how to use a Golden AMI for creating pre-configured, production-ready environments with standardized application setup.

---

##  Table of Contents

- [Purpose](#purpose)
- [Pre-requisites](#pre-requisites)
- [Architecture](#architecture)
- [Step-by-Step Installation Guide](#step-by-step-installation-guide)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

---

##  Purpose

This POC showcases how to:

- Set up an EC2 instance with a working application
- Convert that EC2 instance into a Golden AMI
- Use that AMI to launch new instances with the application pre-installed
- Reduce setup time, ensure consistency, and improve security across deployments

---

##  Pre-requisites

You must have the following:

- AWS account with EC2 access
- A sample application or codebase to deploy
- Basic knowledge of EC2, AMIs, and Linux commands
- IAM permissions to create AMIs and launch EC2 instances
- SSH key pair for connecting to instances

---

##  Architecture

```

\[ Developer ]
|
\| 1. Pushes code to repo or brings app code
v
\[ EC2 Instance (Manual Setup) ]
|
\| 2. App installed and verified
v
\[ Golden AMI Created ]
|
\| 3. New EC2 launched from Golden AMI
v
\[ Application Ready Out-of-the-Box ]

````

*This flow ensures the new EC2 is instantly ready with the full app environment.*

---

##  Step-by-Step Installation Guide

###  Step 1: Launch EC2 and Set Up Application

- Launch an EC2 instance (Amazon Linux 2 preferred)
- Connect to EC2 via SSH
- Install required dependencies and your application


* Start application and ensure it runs (you can access it via browser or curl depending on setup)

###  Step 2: Create Golden AMI

* Go to AWS EC2 Console
* Select the instance → Actions → Image → Create Image
* Provide:

  * Name: `Name_AMI`
  * Description (optional)
  * No reboot (optional if you’re okay with running services stopping)
* Note the AMI ID once it is created

###  Step 3: Launch New EC2 Using Golden AMI

* Go to EC2 → AMIs → Select your AMI → Launch Instance

* Select instance type, security group, key pair as required

* Once launched, the instance will already have:

  * All dependencies
  * Pre-installed application
  * Ready-to-use environment

* Connect via SSH and verify application is up and running

---

##  Conclusion

* Golden AMIs help you avoid repetitive setup steps.
* Ensures fast, consistent, and reliable infrastructure deployments.
* Reduces patching and human error.
* This POC verifies the value of AMI-based application packaging.

---

##  Contact Information

* Name: Your Name
* Email: [your.email@example.com](mailto:your.email@example.com)
* GitHub: [your-github](https://github.com/your-github)

---

##  References

* [AWS AMI Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html)
* [How to Create AMI in AWS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami.html)
* [Amazon EC2 Getting Started](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html)

---


