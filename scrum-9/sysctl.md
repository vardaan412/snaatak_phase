# SOP: Managing Kernel Parameters using sysctl (Performance & Security Tuning)

| Created     | Version | Author         | Comment | Reviewer |
|-------------|---------|----------------|---------|----------|
| 14-04-2025  | V1      | Vardaan Saxena |         | Pritam   |

## 📌 Objective
This SOP provides a step-by-step guide to **view, apply, and persist kernel parameter changes** using `sysctl` for system performance optimization and security hardening.

---

## 📚 Table of Contents

1. [What is sysctl?](#-what-is-sysctl)
2. [View Current Kernel Parameters](#-1-view-current-kernel-parameters)
3. [Temporary Changes (Until Reboot)](#-2-temporary-changes-until-reboot)
4. [Persisting Changes (After Reboot)](#-3-persisting-changes-after-reboot)
5. [Common Parameters for Tuning](#-4-common-parameters-for-tuning)
    - [Security Tuning](#-security-tuning-examples)
    - [Performance Tuning](#-performance-tuning-examples)
6. [Verify Changes](#-5-verify-changes)
7. [Best Practices](#-6-best-practices)
8. [Rollback Tips](#-7-rollback-tips)
9. [References](#-references)
10. [Contacts](#-contacts)

---

## 📖 What is sysctl?
`sysctl` is a powerful utility on Linux systems used to **view and modify kernel parameters** at runtime. It allows dynamic tuning of various system behaviors related to networking, memory, process limits, etc.

## 🔍 1. View Current Kernel Parameters
You can view a specific kernel parameter using:
```bash
sysctl <parameter_name>
```
**Example:**
```bash
sysctl net.ipv4.ip_forward
```
To list **all kernel parameters**:
```bash
sysctl -a
```

## ✍️ 2. Temporary Changes (Until Reboot)
To temporarily change a kernel parameter:
```bash
sudo sysctl -w <parameter_name>=<value>
```
**Example:**
```bash
sudo sysctl -w net.ipv4.ip_forward=1
```
> ⚠️ Temporary changes are lost after a reboot.

## 📝 3. Persisting Changes (After Reboot)
To make changes **permanent**, you need to update the config file:
1. Open `/etc/sysctl.conf` or create a custom file inside `/etc/sysctl.d/`.
```bash
sudo nano /etc/sysctl.conf
```
2. Add the parameter:
```conf
net.ipv4.ip_forward = 1
```
3. Apply the changes without reboot:
```bash
sudo sysctl -p
```
> 📝 Use `/etc/sysctl.d/custom.conf` for modular configuration if managing many systems.

## ⚙️ 4. Common Parameters for Tuning

### 🔐 Security Tuning Examples
```conf
# Disable IP source routing
net.ipv4.conf.all.accept_source_route = 0

# Disable packet redirects
net.ipv4.conf.all.accept_redirects = 0
net.ipv4.conf.all.send_redirects = 0
```

### 🚀 Performance Tuning Examples
```conf
# Increase max open files
fs.file-max = 100000

# Increase TCP buffer sizes
net.core.rmem_max = 16777216
net.core.wmem_max = 16777216
```

## ✅ 5. Verify Changes
To verify a specific parameter:
```bash
sysctl <parameter_name>
```
Or verify all:
```bash
sysctl -a | grep <parameter_name>
```
To check persisted values:
```bash
cat /etc/sysctl.conf
# or
cat /etc/sysctl.d/<file>.conf
```

## 🛡️ 6. Best Practices
- Always **test** changes in a non-production environment first.
- Keep a **backup** of original configuration files.
- Document why a parameter is being tuned.
- Use **modular files** in `/etc/sysctl.d/` for better organization.

## ♻️ 7. Rollback Tips
If a change causes issues:
1. Revert the value in the config file.
2. Apply using:
```bash
sudo sysctl -p
```
Or to reset only a specific parameter:
```bash
sudo sysctl -w <parameter_name>=<old_value>
```

## 📂 References
- [`man sysctl`](https://man7.org/linux/man-pages/man8/sysctl.8.html)
- [Red Hat Performance Tuning Guide](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/performance_tuning_guide/)
- [Kernel.org Documentation](https://www.kernel.org/doc/Documentation/sysctl/)

## 📇 Contacts

| Name           | Email Address                                 |
|----------------|-----------------------------------------------|
| Vardaan Saxena | vardaan.saxena.snaatak@mygurukulam.co         |
