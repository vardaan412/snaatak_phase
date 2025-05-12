
# <img width="35" alt="image" src="https://github.com/user-attachments/assets/cd1cb06d-90e7-410e-bccc-3a4d645dd6c5"> Setup notification for Code commit


| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 12-05-2025  | 12-05-2025 | V1.0  | Vardaan Saxena |     Internal Review    | Pritam    |



# Table of Content 
1. [ Purpose](#-purpose)
2. [ Prerequisites](#-prerequisites)
3. [Steps to Set up Email Notificatin](#steps-to-set-up-email-notification)
4. [ Conclusion](#-conclusion)
5. [ References](#-references ) 
6. [ Contact Information ](#-contact-information )
   

     
#  Purpose 
This document provides a clear, step-by-step guide for setting up email notifications for code commits in GitHub. By following these instructions, users can stay informed about changes in their repositories without requiring any scripting or complex configurations. This enhances collaboration and keeps team members updated on project developments.
![codecommit drawio (2)](https://github.com/user-attachments/assets/93433a96-f1ff-45a3-b38d-a198555dcf9a)


##  Prerequisites
- A GitHub account.
- Access to the repository for which you want to receive notifications.

##  Steps to Set up Email Notification

### 1. **Sign in to GitHub**: Go to [GitHub](https://github.com) and log in to your account.
![codecommit drawio (2)](https://github.com/vardaan412/snaatak_phase/blob/9f297e6da5dd54ce6c73cca4781bfaed2f072ffc/commit-img/1.png)


### 2. Create a repository for which you want to configure notifications for code commits.

![Screenshot 2024-09-23 164450](https://github.com/vardaan412/snaatak_phase/blob/9f297e6da5dd54ce6c73cca4781bfaed2f072ffc/commit-img/2.png)

### 3. Now, click on the repository you created and navigate to the Settings tab at the top.

![Screenshot 2024-09-23 173912](https://github.com/vardaan412/snaatak_phase/blob/9f297e6da5dd54ce6c73cca4781bfaed2f072ffc/commit-img/3.png)

### 4. Generate an App Password for Gmail: If you are using Gmail, you'll need to generate an App Password for your Google account:

**Go to your Google Account.**

**Navigate to Security -> Signing in to Google -> App Passwords.**

**Choose Mail and select your device, then generate a password and copy it.**

![Screenshot 2024-09-23 200443](https://github.com/vardaan412/snaatak_phase/blob/9f297e6da5dd54ce6c73cca4781bfaed2f072ffc/commit-img/4.png)

### 5. Set up GitHub Action Workflow:

**Create a GitHub Actions workflow file in your repository to send an email when a code commit is made.**

**In your GitHub repository, create a workflow file in .github/workflows/ (e.g., send-email-on-codecommit.yml):**

![Screenshot 2024-09-23 200921](https://github.com/vardaan412/snaatak_phase/blob/9f297e6da5dd54ce6c73cca4781bfaed2f072ffc/commit-img/5.png)

### 6. Add Gmail Credentials to GitHub Secrets:

**Go to your GitHub repository.**

**Click on Settings -> Secrets -> Actions -> New repository secret.**

**Add two secrets:**

**EMAIL_USERNAME: Your Gmail address (e.g., your-email@gmail.com).**

**EMAIL_PASSWORD: The App Password you generated earlier from Gmail.**

![Screenshot 2024-09-23 200808](https://github.com/vardaan412/snaatak_phase/blob/9f297e6da5dd54ce6c73cca4781bfaed2f072ffc/commit-img/6.png)

### 7. Commit and Push the Workflow File:

**Once you add the workflow file, every time a commit is pushed to the specified repo (e.g., code-commit-demo), the GitHub Action will send an email with the details of the commit (message, author, and URL).**

![Screenshot 2024-09-23 235555](https://github.com/vardaan412/snaatak_phase/blob/9f297e6da5dd54ce6c73cca4781bfaed2f072ffc/commit-img/7.png)

![Screenshot 2024-09-23 235555](https://github.com/vardaan412/snaatak_phase/blob/9f297e6da5dd54ce6c73cca4781bfaed2f072ffc/commit-img/8.png)


##  Conclusion
The POC successfully demonstrates an automated email notification system for new code commits, in a GitHub repository. It uses GitHub Actions and a secure email integration via Gmail credentials. This solution ensures timely notifications for relevant code changes while filtering out unnecessary merge events.
 
##  References 
|links | Description |
|-------|------------|
|https://youtu.be/oMU9MUIXPyI?feature=shared|**Rainbow talks** |
|https://www.youtube.com/watch?v=qToZN5S67AM| **SDet Automation**|
|https://tinyurl.com/bdpf3ajc|**GIT**|

##  Contact Information 
|Name|Email Address|
|:---:|:---:|
|**Vardaan Saxena**|vardaan.saxena.snaatak@mygurukulam.co |
