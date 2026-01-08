📖Project Overview


This project demonstrates the end-to-end configuration of a Windows-based enterprise environment within a virtualized lab. The primary focus was implementing the Principle of Least Privilege (PoLP) through structured Organizational Units (OUs) and restrictive Group Policy Objects (GPOs) to minimize the internal attack surface.

📂This document covers:
Domain controller setup, DNS configuration, Active Directory structure (OUs, users, groups), Security controls and least privilege implementation.

🛠️ Troubleshooting & Lessons Learned
Input Focus: Resolved an issue where the VM stopped responding to the keyboard by using the Host Key (Right Ctrl) + Delete combination to trigger the logon screen.
UI Restoration: Recovered the hidden VirtualBox menu bar by toggling Scaled Mode (Right Ctrl + C).
Connectivity: Identified that the client must point exclusively to the DC for DNS to successfully resolve the mopetech.ai domain.
