
# **Feature of VCS (Conclusion Documentation)**

# **Author**


| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 26-04-2025  | 26-04-2025 | V1  | Vardaan Saxena |     Internal Review    | Pritam    |


# **Table Of Content**
- [Introduction](#introduction)
- [Why we need VCS](#why-we-need-vcs)
- [Comparison](#comparison)
- [Conclusion](#conclusion)
- [References](#references)
- [Contacts](#contacts)


# **Introduction**

### [GitHub](https://github.com/avengers-p11/Documentation/blob/main/VCS%20Design%20%2B%20POC/Features%20of%20VCS/GitHub%20features/README.md)
- Best for collaborative development with a large, active community.  
- Simplifies workflows with features like GitHub Actions (CI/CD) and GitHub Copilot.  

### [Bitbucket](https://github.com/avengers-p11/Documentation/blob/main/VCS%20Design%20+%20POC/Features%20of%20VCS/BitBucket_features/README.md)
- Focused on integration with Atlassian products like Jira.  
- Popular among teams using other Atlassian tools.  

### [GitLab](https://github.com/avengers-p11/Documentation/blob/main/VCS%20Design%20+%20POC/Features%20of%20VCS/Gitlab%20Features/README.md)
- Offers CI/CD pipelines natively and extensive DevOps features.  
- Provides an open-source self-hosted option.  

---
# **Why we need VCS**
We need a Version Control System (VCS) like Git for our project to track changes, manage multiple developers working on the code, and keep everything organized. It allows us to safely make updates without affecting the main codebase, and if something goes wrong, we can easily revert to a previous version. VCS also helps with code reviews, ensures better quality, and integrates with CI/CD tools for automated testing and deployment. Overall, it improves collaboration, makes development smoother, and helps maintain code integrity

---

# **Comparison**

## VCS Platform Comparison: Bitbucket, GitLab, and GitHub


| Criteria                  | GitHub                          | GitLab                          | Bitbucket                         |
|---------------------------|----------------------------------|----------------------------------|------------------------------------|
| Supported VCS             | Git only                        | Git only                        | Git (Mercurial support removed)   |
| Repository Hosting        | Cloud + Enterprise              | Cloud + Self-managed            | Cloud + Bitbucket Server          |
| Merge/Pull Requests       | Pull Requests                   | Merge Requests                  | Pull Requests                     |
| Code Collaboration        | Reviews, Discussions            | In-line commenting, Reviews     | Basic review tools                |
| Issue Tracking            | GitHub Issues                   | Built-in issue tracker          | Jira integration                  |
| CI/CD Integration         | GitHub Actions                  | GitLab CI/CD (native)           | Bitbucket Pipelines               |
| Container Registry        | GitHub Packages                 | GitLab Registry                 | Supports via integration          |
| DevOps Features           | Good (via Actions & Marketplace)| Full DevOps Platform            | Basic DevOps tools                |
| Kubernetes Support        | via integrations                | Built-in                        | Supported                         |
| Security Tools            | Code/Secret/Dependency Scanning | Full security suite             | Basic security features           |
| Compliance & Governance   | Enterprise tier only            | Available in free/self-managed  | Limited features                  |
| API/Extensibility         | REST & GraphQL APIs             | Full API Access                 | REST API                          |
| User Limits (Free Tier)   | Unlimited collaborators         | 5 users                         | 5 users                           |
| Best For                  | Community and Open Source       | Full DevOps Lifecycle           | Teams using Atlassian ecosystem   |



---

# **Cost** 
GitHub offers competitive pricing with a **free tier for public and private repositories**, making it accessible to individuals and small teams. For enterprises, the pricing aligns with its robust feature set, including GitHub Enterprise with advanced security, compliance, and performance tools.

| Plan                 | GitHub              | GitLab              | Bitbucket           |
|----------------------|---------------------|---------------------|---------------------|
| **Free Tier**         | Yes (unlimited repos)| Yes (limited features)| Yes (limited repos) |
| **Pro Plans**         | Starts at $4/user/mo| Starts at $5/user/mo| Starts at $3/user/mo|
| **Enterprise**        | Advanced features   | Advanced features   | Limited enterprise options|

---

# **Conclusion**

### Which one is Best?
GitHub stands out from Bitbucket and GitLab with its unmatched developer community, seamless third-party integrations, and user-friendly interface. Unlike **Bitbucket, which focuses on Atlassian tools**, and **GitLab, which can be overwhelming for smaller teams**, **GitHub provides a balanced, intuitive platform suitable for all project sizes**. In our microservice project, we use GitHub because it offers a lot of features and is easy to understand. GitHub helps us manage individual microservices, and collaborate efficiently, making it the suitable tool for our project.

---

#  **Contact Information**


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Vardaan Saxena | vardaan.saxena.snaatak@mygurukulam.co    |




# **References**

| No. | Reference                                                                                         | Description                    |
|-----|---------------------------------------------------------------------------------------------------|--------------------------------|
| 1   |  [Bitbucket Intro - GeeksforGeeks](https://www.geeksforgeeks.org/introduction-to-bitbucket/?ref=ml_lbp) | For understanding Bitbucket.  |
| 2   |  [GitHub Intro - GeeksforGeeks](https://www.geeksforgeeks.org/introduction-to-github/?ref=ml_lbp)       | For understanding GitHub.     |
| 3   |  [GitLab Intro - TutorialsPoint](https://www.tutorialspoint.com/gitlab/gitlab_introduction.htm)         | For understanding GitLab.     |




`
