# Windows Enterprise Operations Lab

## Overview

This repository documents the development and operation of a virtual Windows enterprise environment designed to build practical experience for Help Desk, IT Support, systems administration, networking, and security operations roles.

Rather than presenting isolated configuration exercises, the lab is operated through realistic support tickets. Each ticket begins with a user or business problem and documents the full troubleshooting lifecycle:

- Initial symptoms
- Known facts
- Investigation plan
- Evidence collection
- Findings
- Root-cause analysis
- Resolution
- Verification
- Lessons learned
- Administrator reflection

The primary goal is to develop disciplined troubleshooting, clear technical documentation, and an understanding of how identity, permissions, networking, Windows services, and security controls interact inside an organization.

---

## Lab Environment

The environment is hosted in Oracle VirtualBox and currently includes:

| System | Purpose | Status |
|---|---|---|
| DC01 | Windows Server 2022 Domain Controller | Operational |
| FS01 | Future dedicated file server | Available for expansion |
| WIN11 | Windows 11 workstation | Available for future client testing |
| Ubuntu Log Machine | Centralized logging and monitoring | Available for future integration |
| Kali Linux | Controlled attack and security-testing system | Available for future security scenarios |

The environment uses the internal Active Directory domain:

```text
blackbox.local
