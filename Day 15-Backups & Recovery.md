# 💾 Day 12 – Backups & Recovery  

**Objective:**  
Implement Azure snapshot and backup strategies to protect `winlabvm02` and simulate a real-world restore scenario.

---

## 🧩 Step 1 – Create a Snapshot  

1. From the Azure Portal, search **“Snapshots.”**  
2. Click **+ Create** and complete the form:  
   - **Name:** `winlabvm02-snapshot01`  
   - **Resource Group:** `LABNN`  
   - **Source Type:** Disk → select VM OS disk  
   - **Snapshot Type:** Full  
   - **Storage Type:** Standard HDD  
3. **Review + Create → Create**.
   
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/3c0ab6f0-b97b-4ae8-a551-287e5b9b98b1" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/41983b13-61de-41e9-aee3-46475b6da891" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/3b8b9bb4-7d56-448a-8c38-e85d381ae28d" />


**Result:** A point-in-time image of the VM’s OS disk is now available for restore or cloning.

---

## 🧩 Step 2 – Configure Azure Backup  

1. Search **“Recovery Services Vaults.”**  
2. **+ Create Vault** →  
   - **Name:** `labvault01`  
   - **Resource Group:** `LABNN`  
   - **Region:** same as VM  
   - **Backup Storage Redundancy:** **Locally Redundant (LRS)** *(for cost savings)*  
3. After deployment → **Go to Resource → Backup → + Backup**  
4. **Backup Goal:** Azure → Virtual Machine → Backup  
5. **Backup Policy:** DefaultPolicy (Daily + 30 Days)  
   - **Add VM:** `winlabvm02` → **Enable Backup**  
6. In the vault → **Backup Items → Azure Virtual Machine → winlabvm02 → Backup Now**  
7. Confirm 30-day retention → OK  
8. Monitor under **Backup Jobs** until status = *Completed Successfully.*
   
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/62ca00a3-fbd2-41c1-9823-031975a6d94a" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/0d507b66-ba76-4ce5-8530-66dac7347474" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/c6c3a340-5794-49f6-9d3b-feea8c0c060d" />



**Observation:** Initial status may show “Initial Backup Pending.” Use “Backup Now” to trigger the first backup immediately.  

**Result:** `winlabvm02` is now protected by automated daily backups stored in `labvault01`.

---

## 🧩 Step 3 – Restore / Redeploy from Snapshot  

1. Search **“Snapshots.”** → open `winlabvm02-snapshot01`.  
2. Click **+ Create Disk** →  
   - **Name:** `winlabvm02-restore-disk`  
   - **Resource Group:** `LABNN`  
   - **Region:** same as snapshot  
   - **Performance Type:** Standard HDD → **Create**.  
3. From the new disk page → **+ Create VM**  
   - **Name:** `winlabvm02-restored`  
   - **Availability Options:** **No infrastructure redundancy required**  
   - **Size:** B1s (same as original)  
   - **Auth Type:** Password → use lab credentials  
   - **Network:** same VNet / Subnet as original  
   - **Public IP:** create new (default) → **Review + Create → Create**.
     
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/a3367a54-9fcc-4540-950e-8c998f85b317" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/0c06957c-3dbe-4617-9119-f14d49ad5e02" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/bc18da26-35fe-4e54-a9de-08b51b0ef5eb" />


**Result:** A fully bootable clone `winlabvm02-restored` was deployed from the snapshot, confirming successful disaster-recovery validation.

---

## 🧠 Notes & Key Takeaways  

- **Snapshots** = manual point-in-time copies; great for quick rollbacks.  
- **Recovery Services Vault** = automated scheduled backups + retention management.  
- **LRS vs GRS:** LRS chosen to conserve Azure credits in lab testing.  
- **Restore Test:** Validates that disks and snapshots can re-instantiate VMs when needed.  

✅ **Outcome:** Backup and recovery procedures successfully validated for `winlabvm02` within resource group `LABNN`.

---

