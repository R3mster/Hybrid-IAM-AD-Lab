# Hybrid IAM Active Directory Lab

## Project Overview
This lab documents the setup of a foundational Windows Server Active Directory environment for IAM, hybrid identity, and future Entra ID/Okta integration projects.

The goal of this lab is to simulate a small enterprise identity environment using Windows Server, Active Directory Domain Services, DNS, and later hybrid cloud identity services.

## Lab Objectives
- Create a Windows Server virtual machine
- Configure server networking
- Install Active Directory Domain Services
- Install DNS Server role
- Promote the server to a Domain Controller
- Create a new AD forest and domain
- Prepare the environment for future IAM labs

## Lab Environment

| Component | Configuration |
|---|---|
| Host Machine | Windows 10 Pro Desktop |
| Hypervisor | VMware Workstation Pro |
| VM Name | REMI-DC01 |
| Server OS | Windows Server 2022 Evaluation |
| Domain | corp.remilab.local |
| NetBIOS Name | CORP |
| Server Role | Domain Controller, DNS Server |

## Work Completed

### 1. Verified Host Virtualization Support
Confirmed the host machine supports virtualization.

Key findings:
- Virtualization enabled in firmware
- Windows 10 Pro host
- 24 GB physical memory
- Hyper-V capable hardware

### 2. Created Windows Server VM
Created a new VMware virtual machine for the domain controller.

VM Name:

```text
REMI-DC01
```
## Active Directory Structure Configuration

### Organizational Units Created
- Admins
- Users
- Workstations
- Servers
- Service Accounts
- Groups
- Disabled Users

### Security Groups Created
- GG_IT_Admins
- GG_Helpdesk
- GG_HR_Users
- GG_Finance_Users
- GG_Remote_Users
- GG_Workstation_Admins

### Test User Accounts Created
- remi.admin
- john.smith
- sarah.jones
- helpdesk.user

### IAM Concepts Practiced
- Role-Based Access Control (RBAC)
- Organizational Unit design
- Security group management
- Administrative privilege separation
- Active Directory identity management
## RBAC and Identity Management

### User-to-Role Assignments
| User | Assigned Groups |
|---|---|
| remi.admin | Domain Admins, GG_IT_Admins |
| helpdesk.user | GG_Helpdesk |
| sarah.jones | GG_HR_Users |
| john.smith | GG_Finance_Users |

### IAM Concepts Implemented
- Role-Based Access Control (RBAC)
- Least Privilege Access
- Group-Based Permission Management
- Administrative Role Separation
- Active Directory Identity Provisioning

## Group Policy Objects (GPOs)

### Configured Policies
- Finance drive mapping (F:)
- HR drive mapping (H:)
- Item-level targeting using security groups
- Group-based access control

### GPO Features Used
- User Configuration
- Preferences
- Drive Maps
- Security Group Targeting

## Troubleshooting and Lessons Learned

### Issues Resolved
- DNS misconfiguration preventing domain join
- Broken trust relationship between client and domain
- VMware NAT networking conflicts
- Duplicate IPv4 addressing
- GPO not applying due to missing domain link
- Incorrect SMB share path configuration

### Key Takeaways
- Active Directory heavily depends on DNS
- Clients must use the Domain Controller as their DNS server
- GPOs must be linked to domains/OUs to apply
- Share permissions and NTFS permissions must align
