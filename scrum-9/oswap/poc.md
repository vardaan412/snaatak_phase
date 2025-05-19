
# POC on Dynamic Application Security Testing (DAST)

<div align="center">
  <img src="https://tse3.mm.bing.net/th?id=OIP.JZTdq1uihQQbGQg1QhDiGQHaD5&pid=Api&P=0&h=180" width="40%"/>
</div>

| Last updated | Version | Author         | Comment | Reviewer |
|-----------|---------|----------------|---------|----------|
| 19-05-2025 | V1.0  | Vardaan Saxena |     Internal Review    | Pritam    |

# **Table of Content:** 
- [Introduction](#introduction)
- [Pre-requisites](#pre-requisites)
- [Step-by-Step setup Guide](#step-by-step-setup-guide)
- [Conclusion](#conclusion)
- [Contacts](#contacts)
- [Reference](#reference)

# **Introduction**
This proof of concept (POC) offers a detailed walkthrough for conducting Dynamic Application Security Testing (DAST) with OWASP ZAP.


# **Pre-requisites**
- Minimum Java-17
- A Running Application(Attendance API Python) to Perform DAST.
> **NOTE:**  
> We are using the Attendance API for this setup.  
> Refer to its [Attendance API official GitHub repository](https://github.com/your-org/attendance-api) for installation and usage instructions.

![image](https://github.com/user-attachments/assets/98359f43-cbdc-4617-bbc5-2b6ed9f73405)


# **Step-by-Step Setup Guide**

**Step 1**: To install OWASP ZAP please look this POC 

> **Install OWASP ZAP**  
> Before proceeding, it's **highly recommended** to follow the OWASP ZAPinstructions from the official documentation.  
> 👉 **Follow Step 3 here**: [Install OWASP ZAP Commands](https://github.com/snaatak-Downtime-Crew/Documentation/blob/durgesh_scrums_3/common_stack/operating_system/ubuntu/sop/commoncommands/README.md#1-basic-system-commands)
>
> ---


**Step 2**: Click on the **Automated scan** option a interface will come out on which provide the URL of the application and click on **attack**. 

![image](https://github.com/user-attachments/assets/4a96a933-3907-47c1-8ecb-0589308ebaea)



OWASP ZAP will start  scanning  your application for  vulnerabilities .

![image](https://github.com/user-attachments/assets/61510b82-ae54-4fba-be6b-0580355b3b44)


**Step 3** : Analyze Results

 After the scan, navigate to the Alerts tab to see the list of identified vulnerabilities. Click on each **alert** to see details .

 ![image](https://github.com/user-attachments/assets/a11c4743-8635-416e-b142-2da9ef0ebdb8)


![image](https://github.com/user-attachments/assets/11ec0321-2756-456f-94f4-92f8540dd41b)


 **Step 4** : Report Generation: 

You can also Generate the Report of the analysis by click on the **Report** option and generate it in desired format (HTML, PDF,JSON etc.) for future References. 

![image](https://github.com/user-attachments/assets/e5199663-5308-4390-bb87-a58d107018b5)



After selecting the format,click on **Generate Report**. Your Report will be generated in your desired directory. 

# **Conclusion**

Using OWASP ZAP for DAST is a powerful way to identify and mitigate security vulnerabilities in your web applications. By following the steps above, you can create a comprehensive POC demonstrating its capabilities and integration into your security workflow.

# **Contacts**

|Name|Email Address|
|:---:|:---:|
|**Vardaan Saxena**|vardaan.saxena.snaatak@mygurukulam.co |


# **Reference**

| Links | Description |
|-------|-------------|
| [How to install OWASP ZAP](https://techofide.com/blogs/how-to-install-owasp-zap-on-windows-and-linux/) | Step-by-step OWASP ZAP installation guide for Windows and Linux. |
| [OWASP ZAP Official Site](https://www.zaproxy.org/) | Official OWASP ZAP site with docs, downloads, and support. |
