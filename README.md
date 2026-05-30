# 🖥️ Active Directory Home Lab: Creation & Security Hardening

**Domain:** `mopetech.ai`  
**Environment:** Oracle VirtualBox  
**Operating Systems:** Windows Server 2022 (DC) · Windows 8.1 (Client)

---

## 📖 Overview

This project demonstrates the deployment of a Windows-based network infrastructure. The primary focus was implementing the **Principle of Least Privilege (PoLP)** through structured Organizational Units (OUs) and restrictive Group Policy Objects (GPOs).

---

## 🛠️ Step 1: Domain Controller & Forest Setup

Promoted a Windows Server 2022 instance to a primary domain controller for the `mopetech.ai` forest.

- **Role Installation:** Configured Active Directory Domain Services (AD DS) and DNS
- **Infrastructure:** Set up the server with 1000 MB Base Memory and VBoxSVGA graphics for stable virtualization

---

## 📂 Step 2: Directory Organization (OU Structure)

Moved away from a "flat" directory by creating regional Organisational Units to manage users and resources efficiently.

| Component | Details |
|---|---|
| **OUs Created** | Ogun, Osun, Oyo |
| **Security Groups** | Sales, HR, Consultation, Finance, Booking, Support |
| **Access Model** | Role-Based Access Control (RBAC) |

**Users provisioned:**
- Bamidele.Kurode
- Durojaiye.Bande
- Dayo Bankole
- Rasaq Lawal
- Dara Gbemi
- Kunle Sean
- Funmi Kosope

---

## 💻 Step 3: Client Integration

Successfully joined a Windows 8.1 workstation (`SALES WINDOW PC`) to the `mopetech.ai` domain.

- **Authentication:** Verified domain connectivity by logging in with a delegated user account (`Bamidele.sales@mopetech.ai`)
- **Verification:** Confirmed domain membership via the *"Welcome to the mopetech.ai domain"* notification in System Properties

---

## 🌐 Step 4: Network Configuration & Client Integration

Performed manual network alignment and domain join to establish a functional link between the DC and client.

### 4.1 IP Addressing Schema

Static IP addresses were assigned to ensure persistent connectivity within the virtual network:

| Machine | Role | IP Address | DNS Server |
|---|---|---|---|
| Windows Server | Domain Controller | `10.0.2.4` | `127.0.0.1` (Self) |
| Sales Window PC | Client Workstation | `10.0.2.5` | `10.0.2.4` (DC) |

**Active Directory Update:** On successful domain join, the `SALES WINDOW PC` object automatically appeared in the **Computers** container within the ADUC console on the server.

---

## 🛡️ Step 4 (Security): Hardening via Group Policy

Configured and deployed specific GPOs to enforce the Principle of Least Privilege.

### Key Policies Implemented

| # | Policy | Location |
|---|---|---|
| 1 | **Disable Shutdown Action** | Prevents non-admin users from shutting down or restarting via the Start Menu |
| 2 | **Remove Access to Shut Down/Restart** | `User Configuration > Administrative Templates > Start Menu and Taskbar` |
| 3 | **Firewall Management** | Inbound Rules active and monitored via Windows Firewall with Advanced Security |

---

## ⚙️ Step 5: Policy Enforcement

Forced immediate application of security settings across the domain using:

```cmd
gpupdate /force
```

Run on both the **Domain Controller** and the **client workstation** — both returned `Computer Policy update has completed successfully.`

---

## 🚫 Step 6: Proof of Principle (Least Privilege Validation)

To validate the security model, a restricted action was attempted from a standard user account.

| | |
|---|---|
| **Action attempted** | Access restricted system settings as a standard domain user |
| **Result** | ❌ Blocked — *"This operation has been cancelled due to restrictions in effect on this computer."* |
| **Conclusion** | ✅ PoLP is successfully preventing unauthorized configuration changes by domain users |

---

## 📋 Summary

| Phase | Status |
|---|---|
| Domain Controller & Forest Setup | ✅ Complete |
| OU Structure & RBAC Groups | ✅ Complete |
| Client Domain Join | ✅ Complete |
| Static IP / Network Config | ✅ Complete |
| GPO Security Hardening | ✅ Complete |
| Least Privilege Validation | ✅ Verified |

---

*Project by **Rukayat Mopelola Lawal***
