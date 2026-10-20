

## 📸 Hands-On Lab Proof: Tier 1 Password Reset & Account Recovery
* **Scenario:** A corporate user (`support.test`) contacted the help desk locked out of their local workstation after multiple incorrect login attempts.
* **Action Taken:** Accessed Windows Local Users and Groups (`lusrmgr.msc`), bypassed stale lockout attributes by performing an administrative credential reset, and provided temporary access.
* **Proof of Work:**
passwordreset.png

---

## 📸 Hands-On Lab Proof: System Stability & Crash Diagnostics
* **Scenario:** A user reports intermittent system performance issues and software instability on a Windows workstation.
* **Action Taken:** Launched Windows Reliability Monitor (`perfmon /rel`) to analyze historical system stability, review application/Windows failures, and trace warning event logs.
* **Proof of Work:**
  Reliability Monitor.png

  ---

## 📸 Hands-On Lab Proof: Network DNS Cache Flushing (`ipconfig /flushdns`)
* **Scenario:** A user reported being unable to access an internal company web portal due to stale network routing records.
* **Action Taken:** Opened an elevated command prompt, executed `ipconfig /flushdns` to clear out corrupted DNS resolver records, and re-established clean name resolution.
* **Proof of Work:**
  ipconfig-flushdns.png
* 
