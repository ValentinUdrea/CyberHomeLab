# CyberHomeLab

A hands-on cybersecurity home lab built progressively to explore **network security, Active Directory, privileged access management, security monitoring, detection, investigation, and incident response**.

The lab is divided into multiple connected projects. Each project adds another layer to the same virtual security environment.

---

## Lab Overview

The CyberHomeLab is built progressively:

```text
01 - Virtual Network
        ↓
Network Infrastructure & Segmentation
        ↓
02 - Active Directory PAM Lab
        ↓
Identity & Privileged Access
        ↓
03 - Wazuh SOC Lab
        ↓
Security Monitoring & Detection
        ↓
04 - Adversary Simulation Lab
        ↓
Offensive Security & Attack Simulation
```

The projects are designed to work together rather than being isolated exercises.

---

# Projects

## 01 - Virtual Network

**Repository:** `01-virtual-network`

A hands-on virtual network security lab focused on building the underlying network infrastructure.

### Focus

* Virtual machine networking
* Network segmentation
* OPNsense firewall
* LAB-LAN / ATTACK-LAN separation
* Routing
* NAT
* DHCP
* DNS
* Firewall rules
* Traffic control

This project provides the network foundation used by the following CyberHomeLab projects.

---

## 02 - Active Directory PAM Lab

**Repository:** `02-active-directory-pam-lab`

A hands-on Active Directory and privileged access management lab focused on identity and access control.

### Focus

* Active Directory
* Domain Controller
* Organizational Units
* Users and groups
* Administrative accounts
* Service accounts
* Group Policy
* Least privilege
* Privileged access
* PAM concepts
* Windows security auditing

This project builds the identity and Windows environment that is later monitored by the SOC infrastructure.

---

## 03 - Wazuh SOC Lab

**Repository:** `03-wazuh-soc-lab`

A hands-on Security Operations Center lab focused on monitoring and investigating security activity within the CyberHomeLab environment.

### Focus

* Wazuh
* Windows security events
* Advanced Audit Policy
* Endpoint monitoring
* Security event collection
* Detection
* Alert investigation
* SOC workflows
* Incident response
* Detection engineering

This project uses the network and Active Directory infrastructure created in Projects 01 and 02.

---

# Lab Architecture

```text
                           CyberHomeLab

                         ┌───────────────┐
                         │    Kali       │
                         │ 10.10.50.10   │
                         │ ATTACK-LAN    │
                         └───────┬───────┘
                                 │
                                 ▼
                         ┌───────────────┐
                         │   OPNsense    │
                         │   Firewall    │
                         └───────┬───────┘
                                 │
                         LAB-LAN 10.10.20.0/24
                                 │
             ┌───────────────────┼───────────────────┐
             │                   │                   │
             ▼                   ▼                   ▼
        ┌─────────┐       ┌──────────────┐     ┌────────────┐
        │  DC01   │       │ CLT-WIN11-01 │     │   Wazuh    │
        │ .20.10  │       │   .20.120    │     │  .20.110   │
        │   AD    │       │  Windows 11  │     │   Ubuntu   │
        └─────────┘       └──────────────┘     └────────────┘
```

---

# How the Projects Connect

The projects form a single security environment.

### Network Layer

**01 - Virtual Network**

Provides:

```text
Network
Segmentation
Firewall
Routing
Traffic Control
```

↓

### Identity Layer

**02 - Active Directory PAM Lab**

Provides:

```text
Users
Groups
Authentication
Authorization
Privileged Accounts
Windows Domain
```

↓

### Security Monitoring Layer

**03 - Wazuh SOC Lab**

Provides:

```text
Telemetry
Monitoring
Detection
Alerting
Investigation
Incident Response
```

---

# Security Workflow

The overall lab is designed to support the following defensive workflow:

```text
Activity
   ↓
Windows / Network Event
   ↓
Wazuh Collection
   ↓
Detection
   ↓
Alert
   ↓
SOC Triage
   ↓
Investigation
   ↓
Incident Response
   ↓
Detection Improvement
```

The objective is to understand how security events move through the environment and how a SOC analyst can investigate them.

---

# Current Status

| Project                       | Status         |
| ----------------------------- | -------------- |
| 01 - Virtual Network          | ✅ Completed    |
| 02 - Active Directory PAM Lab | ✅ Completed    |
| 03 - Wazuh SOC Lab            | 🚧 In Progress |
| 04 - Adversary Simulation Lab | 🔜 Planned     |

---

# Future Expansion

After completing the defensive side of the CyberHomeLab, a separate project will be developed for the attacker perspective:

## 04 - Adversary Simulation Lab

The future project will focus on controlled offensive-security scenarios and attack-path development.

The purpose will be to simulate attacker behavior against the existing CyberHomeLab environment and provide a complementary perspective to the defensive SOC project.

```text
Adversary Simulation
        ↓
CyberHomeLab Infrastructure
        ↓
Security Telemetry
        ↓
Wazuh SOC
        ↓
Detection & Investigation
```

This keeps the offensive and defensive work separated into dedicated projects while allowing them to interact through the same lab environment.

---

# Overall Goal

The long-term goal of CyberHomeLab is to build a practical cybersecurity environment that combines:

* Network Security
* Active Directory
* Identity & Access Management
* Privileged Access Management
* Security Monitoring
* Detection
* SOC Investigation
* Incident Response
* Adversary Simulation

The lab is built incrementally, with each project extending the capabilities of the previous one.
