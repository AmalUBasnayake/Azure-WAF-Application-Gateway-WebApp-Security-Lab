# Azure WAF + Application Gateway Web Application Security Lab


![Azure](https://img.shields.io/badge/Platform-Microsoft%20Azure-blue)
![Security](https://img.shields.io/badge/Focus-Cloud%20Security-red)
![WAF](https://img.shields.io/badge/Protection-Web%20Application%20Firewall-green)
![OWASP](https://img.shields.io/badge/Security-OWASP%20Top%2010-orange)
![AZ-500](https://img.shields.io/badge/Certification-AZ--500-purple)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)
![Maintained](https://img.shields.io/badge/Maintained-Yes-success)

![GitHub Repo stars](https://img.shields.io/github/stars/AmalUBasnayake/Azure-WAF-Application-Gateway-WebApp-Security-Lab?style=social)

Hands-on Azure Security Lab demonstrating how to protect cloud web applications using Application Gateway WAF and OWASP threat mitigation.

## Project Overview

This project demonstrates how to secure a cloud web application using **Azure Application Gateway with Web Application Firewall (WAF v2)**.

The lab simulates a real-world **Azure secure web architecture** where internet traffic passes through a Web Application Firewall before reaching the backend web application.

The WAF protects the application against common web attacks including:

- SQL Injection
- Cross-Site Scripting (XSS)
- Malicious HTTP requests
- OWASP Top 10 threats

This project aligns with **Microsoft Azure Security Engineer (AZ-500)** learning objectives.

---

# Architecture Diagram

*(Insert architecture diagram image here)*

Example architecture flow:

Internet  
↓  
Public IP  
↓  
Azure Application Gateway (WAF v2)  
↓  
Backend Pool  
↓  
Azure Web App

---

# Technologies Used

- Microsoft Azure
- Azure Application Gateway (WAF v2)
- Azure Web Application Firewall Policy
- Azure Virtual Network
- Azure App Service
- OWASP Core Rule Set
- Azure Application Insights

---

# Lab Environment

Resource Group:

AZ500-Security-Lab

Resources deployed in this lab:

- Azure Web App (Backend Application)
- Azure Application Gateway
- Web Application Firewall Policy
- Azure Virtual Network
- Public IP Address
- Application Insights

---

# Virtual Network Design

The lab uses **network segmentation** with multiple subnets to improve security.

| Subnet | Purpose |
|------|------|
| Default Subnet | General resources |
| Backend-Subnet | Web application backend |
| WAF-Subnet | Application Gateway deployment |

This architecture ensures that traffic must pass through the **WAF layer before reaching the backend application**.

---

# Step 1 — Create Resource Group

First, create a Resource Group to host all Azure resources used in the lab.

*(Insert screenshot: Resource Group creation)*

---

# Step 2 — Create Virtual Network

Create a Virtual Network with segmented subnets.

Example address space:

10.0.0.0/16

Subnets:

10.0.0.0/24 → Default  
10.0.1.0/24 → Backend-Subnet  
10.0.2.0/24 → WAF-Subnet

*(Insert screenshot: VNet with multiple subnets)*

---

# Step 3 — Deploy Azure Web App

A sample web application is deployed using **Azure App Service**.

Runtime example:

.NET / Node.js / PHP

This application acts as the **backend server behind the Application Gateway**.

*(Insert screenshot: Web App deployment)*

---

# Step 4 — Create Web Application Firewall Policy

Create a **WAF Policy** and configure security rules.

Configuration:

Mode: Prevention  
OWASP Core Rule Set enabled  
SQL Injection protection  
Cross-Site Scripting protection

*(Insert screenshot: WAF Policy creation)*

---

# Step 5 — Deploy Azure Application Gateway

Deploy **Azure Application Gateway (WAF v2)**.

Configuration:

Tier: WAF v2  
Autoscaling enabled  
Public IP attached

The Application Gateway acts as the **secure entry point for incoming web traffic**.

*(Insert screenshot: Application Gateway creation)*

---

# Step 6 — Configure Backend Pool

Create a Backend Pool that points to the **Azure Web App**.

This connects the Application Gateway to the backend application.

*(Insert screenshot: Backend Pool configuration)*

---

# Step 7 — Configure Backend Settings

Configure backend HTTP settings.

Protocol: HTTP  
Port: 80  
Cookie affinity disabled

*(Insert screenshot: Backend settings)*

---

# Step 8 — Configure Routing Rules

Create a routing rule to connect the listener, backend pool, and backend settings.

Protocol: HTTP  
Port: 80

*(Insert screenshot: Routing rule configuration)*

---

# Step 9 — Enable WAF Prevention Mode

Enable **Prevention Mode** to actively block malicious traffic.

*(Insert screenshot: WAF prevention mode)*

---

# Security Testing

The WAF was tested with simulated malicious requests.

Example SQL injection payload:

?id=' OR 1=1 --

Result:

403 Forbidden

This confirms that the **WAF successfully blocked malicious requests before reaching the backend web application**.

---

# Key Security Benefits

- Protects web applications from OWASP Top 10 attacks
- Filters malicious traffic before reaching backend services
- Improves overall cloud application security
- Provides centralized security control for web applications

---

# Learning Objectives

This lab helps understand:

- Azure Application Gateway architecture
- Web Application Firewall deployment
- Secure cloud web application design
- OWASP attack mitigation
- Azure network segmentation

---

# Author

Amal Udayanga Basnayake  

Cloud & Cybersecurity Engineer  
Azure Security Enthusiast  

GitHub  
https://github.com/AmalUBasnayake

Medium  
https://medium.com/@amalubasnayake

LinkedIn  
https://www.linkedin.com/in/amal-udayanga-basnayake
