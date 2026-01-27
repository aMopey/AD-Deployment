
#Active Directory Home Lab: Creation & Security Hardening
##🛡️ Project Overview
This project documents the end-to-end creation, configuration, and security hardening of a Windows-based Active Directory (AD) environment. The lab was designed to simulate an enterprise infrastructure, incorporating professional administrative workflows and strict adherence to international security frameworks including ISO 27001, NIST CSF, and CIS Controls.

Core Objectives

Infrastructure Deployment: Installation and configuration of Windows Server 2022 as a Primary Domain Controller.


Identity Governance: Implementation of a "Least Privilege" and "Zero Trust" model for user and group management.


Security Hardening: Applying enterprise-grade defensive configurations to protect the directory database and compute resources.


🏗️ Technical Architecture
1. Domain Configuration

Domain Controller: Deployed Windows Server 2022 for the forest root domain.


FSMO Role Management: Strategic placement of Flexible Single Master Operation roles to ensure domain stability.


DNS/DHCP: Integrated network services for seamless client-to-DC communication.

2. Logical Structure & RBAC

OU Hierarchy: Organized objects using a departmental structure (e.g., HR, IT, Finance) to enable granular Group Policy application.


Role-Based Access Control (RBAC): Created functional IAM groups to enforce Separation of Duties.


🛠️ Troubleshooting & Lessons Learned
Input Focus: Resolved an issue where the VM stopped responding to the keyboard by using the Host Key (Right Ctrl) + Delete combination to trigger the logon screen.
UI Restoration: Recovered the hidden VirtualBox menu bar by toggling Scaled Mode (Right Ctrl + C).
Connectivity: Identified that the client must point exclusively to the DC for DNS to successfully resolve the mopetech.ai domain.
