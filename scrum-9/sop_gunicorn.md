# SOP: Gunicorn Installation Guide

| Created     | Version | Author         | Comment | Reviewer |
|-------------|---------|----------------|---------|----------|
| 14-04-2025  | V1      | Vardaan Saxena |         | Pritam   |

---

## 📚 Table of Contents

1. [Intro](#-intro)  
2. [Why Gunicorn?](#-why-gunicorn)  
3. [What is Gunicorn?](#-what-is-gunicorn)  
4. [Pre-requisites](#-1-pre-requisites)  
5. [Install Gunicorn](#-2-install-gunicorn)  
6. [Run Gunicorn with a Sample App](#-3-run-gunicorn-with-a-sample-app)  
7. [Create a Gunicorn Systemd Service](#-4-create-a-gunicorn-systemd-service)  
8. [Start and Enable the Service](#-5-start-and-enable-the-service)  
9. [Verify the Setup](#-6-verify-the-setup)  
10. [Best Practices](#-7-best-practices)  
11. [Troubleshooting](#-8-troubleshooting)  
12. [References](#-references)  
13. [Contacts](#-contacts)  
 

---

## 📌 Intro

This SOP provides a simple and clear **step-by-step installation guide** for setting up **Gunicorn** to serve Python applications in a production-like environment.

---

## ❓ Why Gunicorn?

- Lightweight and easy to use
- Perfect for serving Flask, Django, and FastAPI apps
- Can be integrated with Nginx for full production setups

---

## 📖 What is Gunicorn?

Gunicorn (Green Unicorn) is a **Python WSGI HTTP server** that helps run Python web applications over HTTP.

---

## 🧰 1. Pre-requisites

Make sure the following are installed:

- Python 3
- pip
- Flask (for demo)

```bash
sudo apt update
sudo apt install python3 python3-pip -y
pip3 install flask
```

---

## ⚙️ 2. Install Gunicorn

Use pip to install Gunicorn:

```bash
sudo pip3 install gunicorn
```

Check version to confirm installation:

```bash
gunicorn --version
```

---

## 🚀 3. Run Gunicorn with a Sample App

### Step 1: Create a sample app `app.py`

```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello from Gunicorn!"
```

### Step 2: Test app locally

```bash
python3 app.py
```

If it's working, stop it and move on.

### Step 3: Run with Gunicorn

```bash
gunicorn --bind 0.0.0.0:8000 app:app
```

> Syntax: `gunicorn --bind <IP>:<PORT> <file>:<app_object>`

---

## 🛠️ 4. Create a Gunicorn Systemd Service

Create the file:

```bash
sudo nano /etc/systemd/system/gunicorn.service
```

Paste this:

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

> Make sure the paths and usernames are correct for your environment!

---

## 🔁 5. Start and Enable the Service

```bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl start gunicorn
sudo systemctl enable gunicorn
```

---

## ✅ 6. Verify the Setup

Check service status:

```bash
sudo systemctl status gunicorn
```

Check if the app is running:

```bash
curl http://localhost:8000
```

You should see:  
`Hello from Gunicorn!`

---

## 📋 7. Best Practices

- Use `virtualenv` to isolate your Python environment.
- Use `--workers` based on CPU cores (usually 2 x core + 1).
- Always log stdout/stderr for debugging.

---

## 🧯 8. Troubleshooting

- **Permission denied**: Check file ownership and Gunicorn user.
- **Port already in use**: Use a different port (e.g. 8080).
- **Service not starting**: Check logs:
  ```bash
  journalctl -u gunicorn.service
  ```

---

## 🔗 References

- [Gunicorn Docs](https://docs.gunicorn.org)
- [Flask Docs](https://flask.palletsprojects.com)

---

## 📇 Contacts

| Name           | Email Address                                 |
|----------------|-----------------------------------------------|
| Vardaan Saxena | vardaan.saxena.snaatak@mygurukulam.co         |
