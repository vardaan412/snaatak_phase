
#  Ansible Roles CI Workflow Guide

<div align="center">
  <img src="https://technovids.com/wp-content/uploads/2020/04/Ansible-DevOps-Automation.jpg.webp" alt="Ansible Logo" width="40%"/>
</div>


|  Created     |  Version |  Author         |  Comment |  Reviewer |
|----------------|------------|------------------|------------|-------------|
| 18-04-2025     | V1         | Vardaan Saxena   |     Internal Review       | Pritam      |

---

##  Table of Contents

1. [ Intro](#intro)  
2. [ Why CI for Ansible Roles?](#why-ci-for-ansible-roles)  
3. [ What is the CI Workflow?](#what-is-the-ci-workflow)  
4. [ Pre-requisites](#pre-requisites)  
5. [ Folder Structure](#folder-structure)  
6. [ CI Workflow Explanation](#ci-workflow-explanation)  
7. [ Sample `.gitlab-ci.yml`](#sample-gitlab-ci-yml)  
8. [ Best Practices](#best-practices)  
9. [ Troubleshooting](#troubleshooting)  
10. [ References](#references)  
11. [ Contacts](#contacts)  
12. [ Conclusion](#conclusion)

---

##  Intro <a id="intro"></a>

This file outlines the **Continuous Integration (CI) workflow** for automating testing and validation of **Ansible roles** in a CI/CD environment such as GitLab CI.

---

##  Why CI for Ansible Roles? <a id="why-ci-for-ansible-roles"></a>

- 🔹 Ensures every role is tested before merging  
- 🔹 Detects syntax errors, failed tasks early  
- 🔹 Improves code quality and reduces manual testing  
- 🔹 Automates linting, molecule testing, and deployment steps  

---

##  What is the CI Workflow? <a id="what-is-the-ci-workflow"></a>

A CI workflow for Ansible roles typically includes:

- ✅ Linting (using `ansible-lint`)  
- ✅ Syntax check (`ansible-playbook --syntax-check`)  
- ✅ Molecule testing (using Docker/Podman)  
- ✅ Test scenarios (default, idempotence, etc.)  
- ✅ Reporting and artifacts generation  

---

##  Pre-requisites <a id="pre-requisites"></a>

Ensure the following are set up:

- ✅ GitLab/GitHub/Bitbucket CI runner  
- ✅ Docker or Podman installed on runner  
- ✅ `molecule`, `ansible`, and `ansible-lint` installed  
- ✅ Role follows standard Ansible Galaxy structure

---

##  Folder Structure <a id="folder-structure"></a>

```bash
your-ansible-role/
├── defaults/
│   └── main.yml
├── handlers/
│   └── main.yml
├── tasks/
│   └── main.yml
├── molecule/
│   └── default/
│       ├── converge.yml
│       └── molecule.yml
├── meta/
│   └── main.yml
├── tests/
├── .gitlab-ci.yml
└── README.md
```

---

##  CI Workflow Explanation <a id="ci-workflow-explanation"></a>

### ✅ **Step-by-step CI Workflow:**

1. **Install Dependencies:**
   - Set up Python, Ansible, molecule, and docker inside CI runner.

2. **Lint Check:**
   - Runs `ansible-lint` on the role.

3. **Syntax Check:**
   - Validates role syntax using `ansible-playbook --syntax-check`.

4. **Molecule Test:**
   - Spins up Docker container and runs converge playbook.

5. **Idempotence Check:**
   - Ensures role is idempotent on re-runs.

6. **Cleanup:**
   - Cleans up test containers and networks.

---

##  Sample `.gitlab-ci.yml` <a id="sample-gitlab-ci-yml"></a>

```yaml
stages:
  - lint
  - syntax
  - test

variables:
  ANSIBLE_FORCE_COLOR: "true"

before_script:
  - pip install ansible ansible-lint molecule docker

lint:
  stage: lint
  script:
    - ansible-lint .

syntax-check:
  stage: syntax
  script:
    - ansible-playbook -i localhost, -c local molecule/default/converge.yml --syntax-check

molecule-test:
  stage: test
  script:
    - molecule test
```

---

##  Best Practices <a id="best-practices"></a>

- 🔸 Keep `molecule` scenarios minimal and effective  
- 🔸 Always include `idempotence` check  
- 🔸 Maintain `README.md` for each role  
- 🔸 Version control each role separately  
- 🔸 Use Galaxy naming conventions  

---

##  Troubleshooting <a id="troubleshooting"></a>

- 🔧 **Docker permission errors** — Ensure runner has Docker socket access  
- 🔧 **Molecule fails on cleanup** — Use `--destroy=never` for debug  
- 🔧 **Lint issues** — Check for hardcoded values and untagged tasks  
- 🔧 **CI Job Timeout** — Use optimized images, reduce external downloads  

---

##  References <a id="references"></a>

- 🌐 [Ansible Lint](https://ansible-lint.readthedocs.io)  
- 🌐 [Molecule](https://molecule.readthedocs.io)  
- 🌐 [GitLab CI Docs](https://docs.gitlab.com/ee/ci/)

---

##  Contacts <a id="contacts"></a>

| 👤 Name           | 📧 Email Address                                |
|------------------|--------------------------------------------------|
| Vardaan Saxena   | vardaan.saxena.snaatak@mygurukulam.co           |

---

##  Conclusion <a id="conclusion"></a>

Implementing CI workflows for Ansible roles ensures quality, reliability, and rapid feedback during role development. This SOP provides a comprehensive guide to setting up CI with `ansible-lint`, `molecule`, and GitLab pipelines to streamline the role testing process. By following these best practices, teams can maintain high standards across infrastructure codebases.

