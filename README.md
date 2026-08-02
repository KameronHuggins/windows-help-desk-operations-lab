# Windows Enterprise Operations Lab

## Overview

This repository documents a virtual Windows enterprise environment built to develop practical experience for Help Desk, IT Support, systems administration, networking, and security operations roles.

The environment began as an Active Directory administration lab and is now being operated through realistic support tickets. Each ticket documents the complete troubleshooting lifecycle rather than presenting only the final solution.

Ticket documentation includes:

- User-reported symptoms
- Known facts
- Investigation plan
- Evidence collection
- Findings
- Root-cause analysis
- Resolution
- Verification
- Lessons learned
- Administrator reflection

The goal is to develop disciplined troubleshooting, practical Windows administration skills, and documentation habits that would support escalation or handoff to another technician.

---

## Lab Environment

The environment is hosted in Oracle VirtualBox and currently includes:

| System | Purpose | Current Status |
|---|---|---|
| DC01 | Windows Server 2022 Domain Controller, DNS, and departmental shares | Operational |
| FS01 | Windows Server 2022 system intended for a dedicated file-server role | Available for future expansion |
| WIN11 | Windows 11 Enterprise workstation | Installed; domain connectivity remains under investigation |
| Ubuntu Log Machine | Centralized logging and monitoring system | Available for future integration |
| Kali Linux | Controlled security-testing system | Available for future scenarios |

Active Directory domain:

```text
blackbox.local
```

Detailed infrastructure documentation and baseline screenshots are available in the [environment directory](environment/README.md).

---

## Technologies Used

- Windows Server 2022
- Windows 11 Enterprise
- Active Directory Domain Services
- Active Directory Users and Computers
- Microsoft DNS
- Organizational Units
- Active Directory security groups
- Role-based access control
- NTFS permissions
- SMB share permissions
- Windows Effective Access
- Server Manager
- Oracle VirtualBox
- GitHub
- PowerShell planned for future administrative automation

---

## Skills Demonstrated

### Active Directory Administration

- Deployed Active Directory Domain Services
- Promoted a Windows Server to a Domain Controller
- Created and organized departmental Organizational Units
- Created and managed domain user accounts
- Created Global Security Groups
- Managed user group memberships
- Organized disabled users and service accounts
- Configured account and lockout policies

### Identity and Access Management

- Applied role-based access control through security groups
- Avoided assigning departmental permissions directly to individual users
- Reviewed account status and group membership
- Compared affected and unaffected users
- Traced access from user identity to resource permissions

### File and Permission Administration

- Created departmental shared folders
- Configured NTFS permissions
- Configured SMB share permissions
- Applied least-privilege access
- Disabled and converted inherited permissions
- Evaluated permissions through Windows Effective Access
- Troubleshot incomplete Modify access

### Troubleshooting and Documentation

- Separated known facts from assumptions
- Developed and tested troubleshooting hypotheses
- Investigated before making configuration changes
- Collected before-and-after evidence
- Documented root causes and resolutions
- Recorded verification limitations honestly
- Created notes suitable for escalation or technician handoff

---

## Ticket Queue

| Ticket | Description | Status |
|---|---|---|
| [HD-001 — Finance User Cannot Modify Department Share](tickets/HD-001-Finance-User-Cannot-Modify-Department-Share) | Investigated a Finance user who could read departmental files but could not modify or save them because the required security group was missing from the folder’s NTFS ACL. | Resolved |
| [HD-002 — Finance User Cannot Sign In](tickets/HD-002-Finance-User-Cannot-Sign-In) | Investigated a locked domain account by reviewing account restrictions and correlating Security Event IDs 4625 and 4740 before unlocking the account and resetting the password. | Resolved |
| [HD-008 — Onboard Ethernet Has No Link](tickets/HD-008-onboard-ethernet-no-link) | Diagnosed a workstation network issue involving the onboard Ethernet adapter, reviewed adapter and driver status, and restored network connectivity. | Resolved |

Additional tickets will be added as they are investigated and completed.

Planned ticket areas include:

- Password resets
- Account lockouts
- User onboarding and offboarding
- Group-membership requests
- Shared-folder access
- Mapped drives
- DNS troubleshooting
- DHCP
- Group Policy
- Printer issues
- Windows profiles
- Windows Update
- Windows services
- Event Viewer
- PowerShell administration
- Domain connectivity
- Security monitoring
- SOC investigations

---

## Troubleshooting Methodology

Tickets generally follow this process:

```text
Receive ticket
      ↓
Clarify the problem
      ↓
Record known facts
      ↓
Develop hypotheses
      ↓
Gather evidence
      ↓
Test hypotheses
      ↓
Identify the root cause
      ↓
Apply the smallest justified change
      ↓
Verify functionality
      ↓
Document and close
```

The project emphasizes investigation before remediation. Configuration changes are made only after the available evidence supports the proposed cause.

---

## Repository Structure

```text
windows-help-desk-operations-lab/
│
├── README.md
│
├── environment/
│   ├── README.md
│   └── baseline screenshots
│
├── scripts/
│   └── future PowerShell automation
│
├── templates/
│   └── ticket-template.md
│
└── tickets/
    └── HD-001-Finance-User-Cannot-Modify-Department-Share/
        ├── README.md
        └── images/
```

Ticket prefixes identify the category of work:

| Prefix | Category |
|---|---|
| `HD` | Help Desk and end-user support |
| `SA` | Systems administration |
| `NET` | Networking |
| `SOC` | Security operations |

---

## Current Project Status

Completed:

- Windows Server 2022 Domain Controller
- Active Directory Domain Services
- DNS
- Departmental Organizational Units
- User and service-account organization
- Security groups
- Departmental folders
- NTFS permissions
- SMB share permissions
- Account and lockout policies
- Baseline snapshot
- First documented Help Desk investigation

Current limitation:

- The Windows 11 and FS01 systems are not yet functioning as domain-joined clients because of an unresolved virtual-network communication issue.
- Tickets that depend on client authentication may initially use server-side tools such as Active Directory Users and Computers, NTFS permissions, and Effective Access for verification.
- Verification limitations are documented inside each affected ticket rather than being hidden.

---

## Future Expansion

Planned additions include:

- Dedicated file-server configuration
- Functioning domain-joined Windows client
- DHCP services
- Group Policy administration
- Mapped-drive deployment
- Printer deployment and troubleshooting
- Windows profile troubleshooting
- PowerShell automation
- Windows Event Forwarding
- Sysmon
- Centralized logging
- Vulnerability management
- Controlled Active Directory attack-and-defense scenarios
- SOC investigation tickets

---

## Project Purpose

This project is intended to demonstrate that practical IT experience can be developed through disciplined lab operations before obtaining a formal Help Desk title.

The repository focuses not only on what was changed, but also on:

- Why each investigative step was selected
- What evidence supported the conclusion
- Which alternatives were ruled out
- How the resolution was verified
- What another technician would need for follow-up
