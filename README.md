# Hybrid-IAM-AD-Lab
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
