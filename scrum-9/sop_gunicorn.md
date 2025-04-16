# 📘 SOP: Gunicorn Installation Guide

| 🗓️ Created     | 🔖 Version | ✍️ Author         | 💬 Comment | 👀 Reviewer |
|----------------|------------|------------------|------------|-------------|
| 14-04-2025     | V1         | Vardaan Saxena   |            | Pritam      |

---

## 📚 Table of Contents

1. [📌 Intro](#intro)  
2. [❓ Why Gunicorn?](#why-gunicorn)  
3. [📖 What is Gunicorn?](#what-is-gunicorn)  
4. [🧰 Pre-requisites](#pre-requisites)  
5. [⚙️ Install Gunicorn](#install-gunicorn)  
6. [🚀 Run Gunicorn with a Sample App](#run-gunicorn-with-a-sample-app)  
7. [🛠️ Create a Gunicorn Systemd Service](#create-a-gunicorn-systemd-service)  
8. [🔁 Start and Enable the Service](#start-and-enable-the-service)  
9. [✅ Verify the Setup](#verify-the-setup)  
10. [📋 Best Practices](#best-practices)  
11. [🧯 Troubleshooting](#troubleshooting)  
12. [🔗 References](#references)  
13. [📇 Contacts](#contacts)  

---

## 📌 Intro <a id="intro"></a>

This SOP provides a **step-by-step installation guide** for setting up **Gunicorn** to serve Python applications in a production-ready environment.

---

## ❓ Why Gunicorn? <a id="why-gunicorn"></a>

- 🔹 Lightweight and easy to configure  
- 🔹 Ideal for Flask, Django, and FastAPI apps  
- 🔹 Can be paired with Nginx for full-stack deployments  

---

## 📖 What is Gunicorn? <a id="what-is-gunicorn"></a>

Gunicorn (Green Unicorn) is a **Python WSGI HTTP server** designed to serve web applications written in Python over HTTP.

---

## 🧰 Pre-requisites <a id="pre-requisites"></a>

Ensure the following are installed:

- ✅ Python 3  
- ✅ pip  
- ✅ Flask (for demo)

```bash
sudo apt update
sudo apt install python3 python3-pip -y
pip3 install flask
```

---

## ⚙️ Install Gunicorn <a id="install-gunicorn"></a>

Install using pip:

```bash
sudo pip3 install gunicorn
```

Check version:

```bash
gunicorn --version
```

---

## 🚀 Run Gunicorn with a Sample App <a id="run-gunicorn-with-a-sample-app"></a>

### 1️⃣ Create a file named `app.py`:

```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello from Gunicorn!"
```

### 2️⃣ Run it locally:

```bash
python3 app.py
```

(If it works, stop it and move on)

### 3️⃣ Run with Gunicorn:

```bash
gunicorn --bind 0.0.0.0:8000 app:app
```

> Format: `gunicorn --bind <IP>:<PORT> <filename>:<Flask app object>`

---

## 🛠️ Create a Gunicorn Systemd Service <a id="create-a-gunicorn-systemd-service"></a>

Create service file:

```bash
sudo nano /etc/systemd/system/gunicorn.service
```

Paste this content:

```ini
[Unit]
Description=Gunicorn instance to serve Flask app
After=network.target

[Service]
User=ubuntu
Group=www-data
WorkingDirectory=/home/ubuntu/myapp
ExecStart=/usr/local/bin/gunicorn --workers 3 --bind 0.0.0.0:8000 app:app

[Install]
WantedBy=multi-user.target
```

> ⚠️ Make sure to update username, working directory, and app path according to your setup!

---

## 🔁 Start and Enable the Service <a id="start-and-enable-the-service"></a>

```bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl start gunicorn
sudo systemctl enable gunicorn
```

---

## ✅ Verify the Setup <a id="verify-the-setup"></a>

Check status:

```bash
sudo systemctl status gunicorn
```

Test locally:

```bash
curl http://localhost:8000
```

Expected Output:  
`Hello from Gunicorn!`

---

## 📋 Best Practices <a id="best-practices"></a>

- 🔸 Use `virtualenv` for isolated environments  
- 🔸 Set `--workers` = `(2 x CPU cores) + 1`  
- 🔸 Log both stdout and stderr for troubleshooting  

---

## 🧯 Troubleshooting <a id="troubleshooting"></a>

- 🔧 **Permission Denied** — Check file ownership and systemd user  
- 🔧 **Port Already in Use** — Try another port, like `8080`  
- 🔧 **Service Not Starting** — View logs:

```bash
journalctl -u gunicorn.service
```

---

## 🔗 References <a id="references"></a>

- 🌐 [Gunicorn Docs](https://docs.gunicorn.org)
- 🌐 [Flask Docs](https://flask.palletsprojects.com)

---

## 📇 Contacts <a id="contacts"></a>

| 👤 Name           | 📧 Email Address                                |
|------------------|--------------------------------------------------|
| Vardaan Saxena   | vardaan.saxena.snaatak@mygurukulam.co           |
