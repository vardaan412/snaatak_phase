# 🛠️ SOP: Managing Kernel Parameters using sysctl (Performance & Security Tuning)

| Created     | Version | Author         | Comment | Reviewer |
|-------------|---------|----------------|---------|----------|
| 14-04-2025  | V1.1     | Vardaan Saxena |         | Pritam   |

---

## 📚 Table of Contents
1. [📌 Introduction](#introduction)
2. [❓ Why sysctl?](#why-sysctl)
3. [📖 What is sysctl?](#what-is-sysctl)
4. [🔍 View Current Kernel Parameters](#view-current-kernel-parameters)
5. [✍️ Temporary Changes (Until Reboot)](#temporary-changes-until-reboot)
6. [📝 Persisting Changes (After Reboot)](#persisting-changes-after-reboot)
7. [⚙️ Common Parameters for Tuning](#common-parameters-for-tuning)
   - [🔐 Security Tuning Examples](#security-tuning-examples)
   - [🚀 Performance Tuning Examples](#performance-tuning-examples)
8. [✅ Verify Changes](#verify-changes)
9. [🛡️ Best Practices](#best-practices)
10. [♻️ Rollback Tips](#rollback-tips)
11. [📂 References](#references)
12. [📇 Contacts](#contacts)
13. [📌 Conclusion](#📌-conclusion)
---

## 📌 Introduction <a id="introduction"></a>
This SOP provides a step-by-step guide to **view, apply, and persist kernel parameter changes** using `sysctl` for system performance optimization and security hardening.

---

## ❓ Why sysctl? <a id="why-sysctl"></a>
Linux systems offer a flexible way to tune kernel parameters on the fly without rebooting. The `sysctl` utility allows administrators to adjust performance, security, and behavior of the system dynamically — making it an essential part of system hardening and fine-tuning.

---

## 📖 What is sysctl? <a id="what-is-sysctl"></a>
`sysctl` is a powerful utility on Linux systems used to **view and modify kernel parameters** at runtime. It allows dynamic tuning of various system behaviors related to networking, memory, process limits, etc.

---

## 🔍 View Current Kernel Parameters <a id="view-current-kernel-parameters"></a>
To view a specific kernel parameter:
```bash
sysctl <parameter_name>
```

**Example:**
```bash
sysctl net.ipv4.ip_forward
```

To list all kernel parameters:
```bash
sysctl -a
```

---

✍️ Temporary Changes (Until Reboot) <a id="temporary-changes-until-reboot"></a>
To temporarily change a kernel parameter:
```bash
sudo sysctl -w <parameter_name>=<value>
```

**Example:**
```bash
sudo sysctl -w net.ipv4.ip_forward=1
```

> ⚠️ Temporary changes are lost after a reboot.

---

📝 Persisting Changes (After Reboot) <a id="persisting-changes-after-reboot"></a>

To make changes permanent:

1. Open the configuration file:
   ```bash
   sudo nano /etc/sysctl.conf
   ```

2. Add the parameter:
   ```bash
   net.ipv4.ip_forward = 1
   ```

3. Apply changes without rebooting:
   ```bash
   sudo sysctl -p
   ```

> 📝 You can also use `/etc/sysctl.d/custom.conf` for modular configuration if managing many systems.

---

⚙️ Common Parameters for Tuning <a id="common-parameters-for-tuning"></a>

🔐 Security Tuning Examples <a id="security-tuning-examples"></a>
```bash
# Disable IP source routing
net.ipv4.conf.all.accept_source_route = 0

# Disable packet redirects
net.ipv4.conf.all.accept_redirects = 0
net.ipv4.conf.all.send_redirects = 0
```

🚀 Performance Tuning Examples <a id="performance-tuning-examples"></a>
```bash
# Increase max open files
fs.file-max = 100000

# Increase TCP buffer sizes
net.core.rmem_max = 16777216
net.core.wmem_max = 16777216
```

---

✅ Verify Changes <a id="verify-changes"></a>

To verify a specific parameter:
```bash
sysctl <parameter_name>
```

To verify via grep:
```bash
sysctl -a | grep <parameter_name>
```

To check persisted values:
```bash
cat /etc/sysctl.conf
# or
cat /etc/sysctl.d/<file>.conf
```

---

🛡️ Best Practices <a id="best-practices"></a>
- ✅ Always **test** changes in a non-production environment first.
- 🔒 Keep a **backup** of original configuration files.
- 📝 Document why a parameter is being tuned.
- 🗂️ Use modular files in `/etc/sysctl.d/` for better organization.

---
♻️ Rollback Tips <a id="rollback-tips"></a>

If a change causes issues:

1. Revert the value in the config file.
2. Re-apply using:
   ```bash
   sudo sysctl -p
   ```

Or reset only a specific parameter:
```bash
sudo sysctl -w <parameter_name>=<old_value>
```

---

📂 References <a id="references"></a>

- [man sysctl](https://man7.org/linux/man-pages/man8/sysctl.8.html)
- [Red Hat Performance Tuning Guide](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/performance_tuning_guide/)
- [Kernel.org Documentation](https://www.kernel.org/doc/Documentation/sysctl/)


---

📇 Contacts <a id="contacts"></a>

| Name           | Email Address                          |
|----------------|----------------------------------------|
| Vardaan Saxena | vardaan.saxena.snaatak@mygurukulam.co  |

---

## 📌 Conclusion <a id="📌-conclusion"></a>

Managing kernel parameters through `sysctl` is a critical skill for system administrators seeking to optimize system performance and harden security configurations. This SOP provided the foundational steps for viewing, modifying, persisting, and verifying kernel settings effectively. Always ensure testing in a controlled environment before deploying to production and maintain proper documentation for audit and rollback purposes.

---
