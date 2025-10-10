## 🧩 Day 12 – Azure Automation Runbook  
**Task:** Automate VM shutdowns to reduce cost and demonstrate PowerShell automation.  
**Resource:** Azure Automation Account + Runbook  
**Notes:** This lab automates VM shutdown to save credits and practice scripting with PowerShell in Azure.

---

### 🎯 Objective  
Create an Automation Account and PowerShell Runbook that automatically stops a virtual machine in the LABNN resource group.  
This lab demonstrates automation, cost optimization, and governance in Azure.

---

### 🪜 Step-by-Step Instructions  

#### **Step 1 – Create an Automation Account**  
1. In the Azure Portal, search **“Automation Accounts.”**  
2. Click **+ Create → Automation Account.**  
3. Configure the following:  
   - **Resource Group:** LABNN  
   - **Name:** `labnn-auto01`  
   - **Region:** same as your existing resources  
   - **Plan:** Default (Free Tier)  
4. Click **Review + Create → Create.**

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/e8fbcca3-3cfd-4862-b691-717a5b2ac37c" />


---

#### **Step 2 – Create a Runbook**  
1. In your Automation Account → **Process Automation → Runbooks.**  
2. Click **+ Create a runbook.**  
3. Enter the following:  
   - **Name:** `Stop-LabVM`  
   - **Runbook type:** PowerShell  
   - **Runtime version:** 5.1 (Windows PowerShell)  
4. Click **Create.**

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/07067c98-ca76-4d2e-9b94-48d22a859ca0" />


---

#### **Step 3 – Add PowerShell Code**  
1. After creation, click **Edit** to open the code editor.  
2. Paste the following script:  
   ```powershell
   param (
       [string]$ResourceGroupName = "LABNN",
       [string]$VMName = "labvm01"
   )

   Stop-AzVM -ResourceGroupName $ResourceGroupName -Name $VMName -Force

   ---

#### **Step 4 – Test the Runbook**  
1. In the Runbook **Overview** page, click **Start**.  
2. When the **Start Runbook** panel opens:  
   - Leave the default parameters, or enter your VM name if prompted.  
   - Click **OK** to execute.  
3. The job will open in a new tab and display its progress.  
   - Watch the **Job Status**: *Queued → Running → Completed*.  
4. Once completed, return to the **VM Overview** page in the Azure Portal.  
5. Confirm the VM now shows **Stopped (deallocated)**, proving the automation worked.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/9d996e02-03fe-4991-8561-84ac91f14e08" />


---

#### **Step 5 – Schedule the Runbook (Automation)**  
1. Return to the **Runbook Overview** page.  
2. At the top, click **Link to schedule → Create a new schedule.**  
3. Configure the schedule:  
   - **Name:** `DailyShutdown`  
   - **Recurrence:** Daily  
   - **Start time:** 11:00 PM (your time zone)  
   - **Time zone:** Local  
4. Click **Create → OK → Link schedule to Runbook.**  
5. Verify that the new schedule appears under **Run Settings → Schedules.**


<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/34d94aed-116c-4ba0-98b9-9edf6426b969" />

---

### 🧾 **Results**  
- Verified VM stopped successfully through the Runbook test.  
- Created and linked a **daily schedule** for automatic nightly shutdowns.  
- Confirmed automation job status = *Completed* and cost optimization in effect.

---

### 🧠 **What I Learned**  
> Scheduling Runbooks allows Azure resources to be managed automatically, ensuring consistent cost savings and operational efficiency.  
> The combination of PowerShell + Azure Automation delivers enterprise-grade control with minimal effort.

---

### 🖼️ **Screenshot Checklist (continued)**  
| # | Screenshot | Description |  
|---|-------------|--------------|  
| 4 | Job Output | Proof of successful execution |  
| 5 | Schedule | Shows daily recurrence setup |

---
