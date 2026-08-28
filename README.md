# CyberHomeLab

A hands-on cybersecurity home lab built to explore network security, Active Directory, privileged access management, and security monitoring.

The lab is developed as a series of connected projects, with each project adding another layer to the same virtual environment.

---

## Projects

### 01 — Virtual Network

The foundation of the lab.

A virtual network security environment focused on network segmentation, firewall configuration, routing, and controlled communication between isolated networks.

**Main technologies:** OPNsense, VirtualBox, Windows, Linux

[View 01 — Virtual Network →](https://github.com/ValentinUdrea/01-virtual-network)

---

### 02 — Active Directory PAM Lab

The identity and access layer of the lab.

A hands-on Active Directory environment focused on users, groups, privileged accounts, service accounts, Group Policy, and least-privilege concepts.

**Main technologies:** Windows Server, Active Directory, Group Policy

[View 02 — Active Directory PAM Lab →](https://github.com/ValentinUdrea/02-active-directory-pam-lab)

---

### 03 — Wazuh SOC Lab

The defensive security layer of the lab.

A SOC environment focused on Windows security telemetry, endpoint monitoring, detection, alert investigation, and incident response using Wazuh.

**Main technologies:** Wazuh, Windows 11, Active Directory, Ubuntu Server

[View 03 — Wazuh SOC Lab →](https://github.com/ValentinUdrea/03-wazuh-soc-lab)

---

## Lab Architecture

```text
                    CyberHomeLab
                         │
                         ▼
              ┌─────────────────────┐
              │ 01 — Virtual Network│
              │                     │
              │ OPNsense / Firewall │
              │ Segmentation / NAT  │
              │ Routing / DNS / DHCP│
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │ 02 — Active         │
              │ Directory PAM Lab   │
              │                     │
              │ AD / Users / Groups │
              │ GPO / Privileged    │
              │ Access              │
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │ 03 — Wazuh SOC Lab  │
              │                     │
              │ Telemetry / Alerts  │
              │ Detection /         │
              │ Investigation       │
              └─────────────────────┘
```

---

## Current Environment

```text
ATTACK-LAN
10.10.50.0/24
        │
        │
     OPNsense
        │
        ▼
LAB-LAN
10.10.20.0/24
        │
        ├── DC01
        │   10.10.20.10
        │
        ├── CLT-WIN11-01
        │   10.10.20.120
        │
        └── Wazuh
            10.10.20.110
```

The environment is intentionally segmented so that network access, identity, and security monitoring can be tested in a controlled virtual lab.

---

## Overall Architecture

The lab is built in layers:

```text
Network
   ↓
Identity & Access
   ↓
Security Monitoring
   ↓
Detection & Investigation
```

Each project is independently documented while remaining part of the same overall environment.

---

## Status

| Project                       | Status         |
| ----------------------------- | -------------- |
| 01 — Virtual Network          | ✅ Completed    |
| 02 — Active Directory PAM Lab | ✅ Completed    |
| 03 — Wazuh SOC Lab            | 🚧 In Progress |
| 04 — Adversary Simulation Lab | 🔜 Future      |

---

## Future Expansion

Once the defensive side of the lab is completed, the environment will be extended with a separate **Adversary Simulation Lab**.

This future project will focus on the attacker perspective and controlled offensive-security scenarios against the existing infrastructure.

The long-term objective is to connect both perspectives:

```text
Adversary Simulation
        │
        ▼
CyberHomeLab Infrastructure
        │
        ▼
Security Telemetry
        │
        ▼
Wazuh SOC
        │
        ▼
Detection & Investigation
```
