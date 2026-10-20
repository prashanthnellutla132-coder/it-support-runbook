# IT Support & Help Desk Troubleshooting Runbook

## 📌 Overview
A structured reference guide and troubleshooting runbook designed for IT Support and Help Desk professionals. This repository documents standard operating procedures (SOPs) for resolving Tier 1 and Tier 2 workstation, network, and identity management issues.

---

## 🛠️ Core Diagnostic Procedures (SOPs)

### 1. Network & Connectivity Troubleshooting
When a user reports *"I have no internet / Can't connect to the network"*
* **Step 1: Check Physical/Link State**
  * Verify Ethernet cable connection or Wi-Fi status.
* **Step 2: Run IP Diagnostics (Command Prompt / PowerShell)**
  * `ipconfig /all` -> Verify IP address, subnet mask, and default gateway.
  * `ipconfig /release` followed by `ipconfig /renew` -> Refresh DHCP lease.
  * `ipconfig /flushdns` -> Clear local DNS resolver cache to fix stale records.
* **Step 3: Test Connectivity**
  * `ping 8.8.8.8` -> Test basic internet routing / external gateway.
  * `ping google.com` -> Test DNS name resolution.
  * `tracert google.com` -> Identify where network traffic drops (hop-by-hop).

### 2. User Authentication & Account Lockouts (Entra ID / Active Directory)
When a user reports *"I am locked out of my account / Password not working"*
* **Step 1: Verify Account Status**
  * Check Microsoft Entra ID / Active Directory portal to verify if the account is `Enabled` or `Locked out`.
* **Step 2: Check Sign-In Logs**
  * Review Entra ID Sign-In logs to determine failure reason (e.g., *Error 50126: Invalid username or password* or *MFA challenge required*).
* **Step 3: Remediation**
  * Initiate a temporary password reset, enforce *Require password change on next sign-in*, and verify MFA registration status.

### 3. Windows Workstation Performance & Crash Diagnostics
When a user reports *"My computer is freezing / Application is crashing"*
* **Step 1: Check Resource Utilization**
  * Open **Task Manager** (`Ctrl + Shift + Esc`) to check CPU, Memory, and Disk spikes.
* **Step 2: Review Event Viewer Logs (`eventvwr.msc`)**
  * **System Logs:** Look for hardware/driver warnings (Kernel-Power, disk errors).
  * **Application Logs:** Look for Event IDs associated with application crashes (e.g., .NET runtime or application fault errors).
* **Step 3: System File Integrity Check**
  * Run elevated Command Prompt (`cmd` as Admin) and execute:
    * `sfc /scannow` (Scans and repairs corrupted Windows system files).
    * `DISM /Online /Cleanup-Image /RestoreHealth` (Repairs Windows system image).

---

## 📋 Sample Help Desk Ticket Lifecycle

| Ticket ID | Issue Category | User / Asset | Description | Resolution Steps | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **INC-1042** | Identity / Auth | Jane Doe (`jdoe`) | Account locked out after multiple incorrect password attempts. | Verified account in Entra ID, reset temporary credentials, and forced password reset on next login. | **Resolved** |
| **INC-1043** | Network | John Smith (`jsmith`) | Unable to resolve internal company web portal URL. | Flushed local DNS cache (`ipconfig /flushdns`) and renewed IP lease via DHCP. | **Resolved** |

---

## 💼 Skills & Competencies Demonstrated
* **Incident Management:** Following ITIL-aligned troubleshooting frameworks.
* **OS Administration:** Command-line diagnostics, Event Viewer analysis, and system file repair (`sfc`, `DISM`).
* **Network Troubleshooting:** DNS flushing, DHCP renewal, and gateway verification.
* **Identity Management:** User lockout resolution and credential resets.
