## 🧩 Day 13 – Azure Monitoring & Alerts  
**Task:** Configure Azure Monitor and create an alert rule.  
**Resource:** Azure Monitor + Alerts  
**Notes:** Track basic VM metrics and set up an automated alert for high CPU usage.

---

### 🎯 Objective  
Use **Azure Monitor** to visualize metrics from your VMs and build an **alert rule** that notifies you when CPU usage exceeds a defined threshold.

---

### 🪜 Steps Completed  

#### Step 1 – Open Azure Monitor  
1. In the Azure portal, search for **Monitor**.  
2. Open **Monitor → Overview** to review sections like *Metrics*, *Alerts*, and *Activity log*.


<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/29eebfee-4401-40da-9bc7-c37403bec78e" />

---

#### Step 2 – View VM Metrics  
1. Select **Metrics** from the left menu.  
2. Click **Select a scope → Virtual Machines**, then choose `winlabvm02` and `linuxlabvm01`.  
3. **Metric namespace:** *Virtual Machine Host*  
4. **Metric:** *Percentage CPU*  
5. **Aggregation:** Average     **Region:** (Global – default)  
6. Click **Apply** to display the chart.


<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/2016956e-bb0f-4604-978a-f989205a073e" />

---

#### Step 3 – Create an Alert Rule (for Windows VM)  
1. While viewing the metric chart, click **New alert rule**.  
2. **Scope:** Confirm `winlabvm02` is selected.  
3. **Condition:** Percentage CPU > 70 % for 5 minutes.  
4. **Action Group:** Create `LabAlertGroup` with email notification (to be tested later).  
5. **Alert Rule name:** `HighCPU_winlabvm02`    **Severity:** 3 (Informational)  
6. Click **Review + Create → Create.**


<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/c5fc3dcc-d767-48b0-a7c2-dde3b8828f7e" />

---

### 💾 Configuration Summary  
| Setting | Value |  
|----------|-------|  
| Resources | winlabvm02 & linuxlabvm01 |  
| Metric | Percentage CPU (Average) |  
| Threshold | > 70 % for 5 minutes |  
| Action Group | LabAlertGroup (Email) |  
| Severity | 3 – Informational |  

---

### 🧠 What I Learned  
> Azure Monitor provides centralized visibility into resource performance and enables automated alerts for proactive response.  
> This lab introduced metrics scopes, alert conditions, and action groups.

---

### 🖼️ Screenshot Checklist  
| # | Screenshot | Description |  
|---|-------------|--------------|  
| 1 | Monitor Overview | Shows entry to monitoring workspace |  
| 2 | VM Metrics Chart | CPU % graph for selected VMs |  
| 3 | Alert Rule Summary | Scope + Condition + Action Group details |  

---

**Lab Status:** ✅ Steps 1–3 Complete (Will revisit optional alert trigger and dashboard later.)
