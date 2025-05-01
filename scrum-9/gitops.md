
# Understanding of GitOps as concept

<div align="center">
  <img src="https://github.com/user-attachments/assets/8eb01d4d-b625-4c44-977c-9148800ee17f" alt="Ansible Logo" width="40%"/>
</div>


| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 01-05-2025  | 01-05-2025 | V1.0  | Vardaan Saxena |     Internal Review    | Pritam    |


## Table of Contents
1. [Introduction](#introduction)
2. [Why GitOps](#why-gitops)
3. [GitOps Principles](#gitops-principles)
4. [GitOps Tools](#gitops-tools)
5. [GitOps Workflows and Procedures](#gitops-workflows-and-procedures)
6. [Benefits of GitOps](#benefits-of-gitops)
7. [Drawbacks of GitOps](#drawbacks-of-gitops)
8. [GitOps Best Practices](#gitops-best-practices)
11. [Contact Information](#contact-information)
12. [References](#references)

## Introduction

GitOps is a modern approach to managing infrastructure and applications using Git as the single source of truth, combining version control, collaboration, and CI/CD to enable automated, reliable, and auditable workflows for faster, more secure software delivery.

## Why GitOps

|Aspect	| Details |
|----------|------------|
| Auditability  | Git tracks all changes, providing a clear history for debugging and compliance. |
| Automation	| Reduces human errors by automating deployment and configuration processes. |
| Consistency	| Ensures infrastructure always matches the desired state defined in the Git repository. |
| Collaboration	| Simplifies collaboration by using Git workflows that developers are already familiar with. | 
| Scalability	| Handles large and complex systems effortlessly, enabling reliable scaling. |

## GitOps Principles

| Principle	| Explanation |
|-------------|--------|
| Declarative Configuration |	System state is defined using declarative manifests stored in Git. |
| Git as a Single Source of Truth | 	Git stores all configurations, enabling version control and rollback capabilities. | 
| Automated Reconciliation |	Automation tools ensure the actual state matches the desired state by continuously reconciling changes. | 
| Pull-based Deployment | 	Deployments are triggered through pull requests, ensuring thorough review and security. |

## GitOps Tools

| Tool |	Description|
|----|------|
| ArgoCD	| Kubernetes-native GitOps tool with a user-friendly GUI. |
|Flux	| Lightweight, CLI-based GitOps operator for Kubernetes.|
|Jenkins X | 	CI/CD tool that integrates GitOps principles with Kubernetes. |
|Rancher Fleet	| Multi-cluster Kubernetes GitOps solution. |
|Spinnaker |	Multi-cloud continuous delivery platform, supporting GitOps workflows. |


## GitOps Workflows and Procedures
Implementing GitOps involves several key workflows:
![workflow](https://github.com/user-attachments/assets/4bf68ccb-dbce-4a90-81f5-acc242b2bfe4)
### 1. Create Pull/Merge Request

- **Action**: A developer makes code changes in their feature branch.
- **Details**: The code includes Terraform configuration files that define infrastructure changes (e.g., resource creation, updates).
- **PR Creation**: The developer creates a Pull Request (PR) to merge their feature branch into the main branch.

### 2. Change/Change (CI Pipeline)

- **Trigger**: The CI (Continuous Integration) Pipeline is triggered when the PR is opened.
- **Pipeline Steps**:
  - **Linting**: Check that Terraform code adheres to proper syntax and formatting conventions.
  - **Unit Tests**: Execute tests to ensure the correctness of the Terraform configuration.
  - **Terraform Plan**: Simulate the changes to preview the resources that will be added, modified, or destroyed. Review the output to ensure the changes are accurate and safe.
- **Feedback Loop**: The changes may go through another round of validation if feedback is provided, either automatically or manually.

### 3. Approved Changes

- **Review**: Changes are reviewed and approved by either automated systems or human reviewers.
- **Action**: Once approved, the PR is marked as Approved.
- **Merge**: The PR is merged into the main branch, signifying that the changes are ready for deployment.

### 4. CD Pipeline (Continuous Deployment)

- **Trigger**: The CD (Continuous Deployment) Pipeline is initiated after the merge.
- **Pipeline Steps**:
  - **Terraform Plan**: Run another Terraform Plan to confirm the final changes based on the merged code.
  - **Terraform Apply**: Apply the changes to the infrastructure in AWS according to the approved plan.

### 5. AWS Deployment

- **Outcome**: Upon successful execution of Terraform Apply, the infrastructure changes are applied in AWS.
- **Result**: AWS resources (e.g., EC2 instances, RDS databases, VPCs) are created, updated, or destroyed as specified in the Terraform configuration.

## Benefits of GitOps

|Benefit	|Details|
|---------|--------|
|Consistency	|Prevents configuration drift across environments.|
|Speed	|Enables faster deployments, updates, and rollbacks.|
|Transparency	|Provides a clear audit trail of all changes through Git.|
|Security|	Git’s access control and review processes enhance operational security.|
|Scalability	|Efficiently manages multi-cluster or complex system environments.|

## Drawbacks of GitOps

|Drawback|	Details|
|------|-------|
|Learning Curve	|Requires knowledge of Git, declarative syntax, and GitOps tools.|
|Tool Complexity	|Managing multiple GitOps tools can be overwhelming.|
|Environment Limitations	|Challenging to implement in legacy or non-cloud-native environments.|
|Resource Overhead	|Continuous reconciliation loops may increase resource usage in large-scale deployments.|

## GitOps Best Practices

|Best Practice|	Details|
|--------|--------|
|Use Branching Models	|Adopt Git workflows like GitFlow or trunk-based development for better collaboration.|
|Encrypt Secrets	|Use tools like Sealed Secrets to secure sensitive data.|
|Automate Testing	|Validate changes through automated CI pipelines before deployment.|
|Monitor and Analyze	|Implement monitoring tools like Prometheus and Grafana for insights and issue detection.|
|Maintain Documentation	|Document GitOps processes and configurations to ensure ease of use and onboarding.|


#  **Contact Information**


| **Name**    | **Email address**         |
|-------------|---------------------------|
| Vardaan Saxena | vardaan.saxena.snaatak@mygurukulam.co    |


## References

|Reference |	Description|
|----|----|
| [GitOps](https://www.gitops.tech) |GitOps Principles|
|[Gitops](https://github.com/avengers-p11/Documentation/blob/main/VCS%20Design%20+%20POC/GitOps/Tools%20evaluation/README.md) | GitOps Tool evolution|
| [ArgoCD](https://argo-cd.readthedocs.io) |ArgoCD Documentation|
| [Flux](https://fluxcd.io) |Flux GitOps|
|[Jenkins X](https://jenkins-x.io) |Jenkins X|
|[Spinnaker](https://spinnaker.io) |Spinnaker Documentation|
