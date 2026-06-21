"# SafeLine-Web-Application-Firewall" 
# 🛡️ SafeLine Web Application Firewall (WAF) Deployment Project

## Overview

This project demonstrates the deployment and configuration of **SafeLine Web Application Firewall (WAF)** in a virtualized lab environment using **Ubuntu **, **Kali Linux**, **Docker**, and **Oracle VirtualBox**.

The objective of this project is to protect a web application hosted on Ubuntu from common web-based attacks such as:

* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)

SafeLine WAF was positioned between the attacker and the target web application to inspect, filter, and block malicious HTTP requests.

---

## Project Objectives

* Deploy SafeLine WAF using Docker.
* Configure WAF protection rules.
* Host a web application on Ubuntu Server.
* Simulate attacks from Kali Linux.
* Detect and block SQL Injection attacks.
* Detect and block XSS attacks.
* Monitor and analyze security events.

---

## Technologies Used

| Technology        | Purpose                  |
| ----------------- | ------------------------ |
| SafeLine WAF      | Web Application Firewall |
| Ubuntu            | Web Server               |
| Kali Linux        | Attack Simulation        |
| Docker            | SafeLine Deployment      |
| Oracle VirtualBox | Virtual Environment      |

---

# Architecture Diagram

### Network Flow

Kali Linux (Attacker)

⬇

SafeLine WAF

⬇

Ubuntu Web Server

⬇

Protected Web Application

---

## Lab Setup

### Machine 1: Ubuntu Server

| Configuration | Value                     |
| ------------- | ------------------------- |
| OS            | Ubuntu                    |
| Role          | Web Server + SafeLine WAF |
| IP Address    | YOUR_IP                   |

### Machine 2: Kali Linux

| Configuration | Value            |
| ------------- | ---------------- |
| OS            | Kali Linux       |
| Role          | Attacker Machine |
| IP Address    | YOUR_IP          |

---

# SafeLine Installation

## Update System

```bash
sudo apt update
sudo apt upgrade -y
```

## Install Docker

```bash
sudo apt install docker.io -y
```

Verify Docker:

```bash
docker --version
```

---

## Deploy SafeLine

```bash
bash -c "$(curl -fsSL https://waf.chaitin.com/release/latest/setup.sh)"
```

After installation:

```bash
docker ps
```

Access SafeLine Dashboard:

```text
http://SERVER_IP:9443
```

---

# Web Application Setup

Install Apache:

```bash
sudo apt install apache2 -y
```

Verify:

```bash
sudo systemctl status apache2
```

Access:

```text
http://SERVER_IP
```

---

# WAF Configuration

1. Login to SafeLine Dashboard.
2. Add Web Application.
3. Configure Backend Server.
4. Enable Protection Policies.
5. Enable Attack Detection Rules.
6. Save Configuration.

---

# Security Testing

## SQL Injection Test

### Payload

```sql
' OR '1'='1
```

### Test Procedure

From Kali Linux:

```text
http://TARGET_IP/index.php?id=' OR '1'='1
```

### Result

✅ SafeLine detected and blocked the SQL Injection attempt.

---

## SQL Injection Screenshot

---

## XSS Attack Test

### Payload

```html
<script>alert('XSS')</script>
```

### Test Procedure

Submit the payload through a vulnerable input field.

### Result

✅ SafeLine blocked the malicious script.

---

## XSS Screenshot

---

# Monitoring and Logs

SafeLine provides:

* Attack Logs
* Source IP Tracking
* Request Analysis
* Event Monitoring
* Traffic Statistics

---

## Dashboard Screenshot

---

# Results

The deployment was successfully completed.

### Achievements

* SafeLine WAF installed successfully.
* Web application protected behind WAF.
* SQL Injection attacks detected and blocked.
* XSS attacks detected and blocked.
* Security logs generated successfully.
* Traffic monitored in real time.

---

# Project Directory Structure

```text
SafeLine-WAF-Project/
│
├── README.md
│
├── screenshots/
│   ├── architecture.png
│   ├── dashboard.png
│   ├── sqli-blocked.png
│   ├── xss-blocked.png
│   ├── safeline-login.png
│   └── traffic-monitoring.png
│
├── docs/
│   ├── installation-guide.pdf
│   └── project-report.pdf
│
└── configs/
    └── waf-config.txt
```

---

# Future Enhancements

* Implement custom WAF rules.
* Configure rate limiting.
* Integrate SIEM solutions.
* Enable email alerts.
* Perform advanced penetration testing.
* Protect multiple web applications.

---

# Learning Outcomes

Through this project, I gained practical experience in:

* Web Application Security
* Web Application Firewalls
* Docker Deployment
* Linux Administration
* Security Monitoring
* SQL Injection Detection
* Cross-Site Scripting Prevention

---

## Author

### Pranathi Palapala

Cybersecurity Enthusiast | SOC Analyst Aspirant

GitHub: https://github.com/YOUR_USERNAME

LinkedIn: https://linkedin.com/in/YOUR_PROFILE

