# 🧩 Day 17– Review & Final Lab Test

---

### 🎯 Goal
Validate all components created in previous Azure labs, ensuring compute, networking, storage, monitoring, and governance are fully operational within the **LABNN** environment.

---

### 🧱 Step 1 – Review All Azure Resources in LABNN
**Task:** Review all deployed resources  
**Resource:** LABNN Resource Group  
**Notes:** Run the Azure CLI command below to confirm your environment’s resources and organization.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/eb1e4635-7133-4080-a226-4c24b2cb8841" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/5efd6ce4-b4c5-45f3-acd6-60db17f69854" />


### 🧱 Step 2 – Review Cost and Redundancy Decisions
**Task:** Analyze current Azure spend and storage redundancy settings  
**Resource:** Cost Management + Billing  
**Notes:**
- Open **Cost Management → Cost Analysis** in the Azure Portal  
- Compare **LRS** (Locally Redundant Storage) vs **GRS** (Geo-Redundant Storage)  
- Identify cost-optimization opportunities and review any budget alerts  
- Confirm that tagging (e.g., `Phase=FinalLab`, `Owner=Nichelle`) helps track costs

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/5a8dda36-867d-45fc-8966-b1e905ae908c" />

---

### 🧱 Step 3 – Verify VM Health via Azure CLI
**Task:** Confirm that VMs are running and healthy or deallocated to preserve cost
**Resource:** Virtual Machines (winlabvm02 / linuxlabvm01)  
**Notes:** Check the PowerState of both VMs to ensure they’re 

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/c979ab7f-6427-4a29-97c6-d560bed967c3" />

---

### 🧱 Step 4 – Cross-check Networking via Azure CLI
**Task:** Validate NIC and NSG configurations for connectivity and security compliance  
**Resource:** Network Interface + Network Security Group  
**Notes:** Ensure inbound RDP (3389) and SSH (22) rules are configured correctly

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/9ce38a29-47a7-4e93-a1fa-c277ce6067e2" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/04fc8c59-c1b0-48cf-ac1d-765b6eacdd58" />

---

### 🧱 Step 5 – Validate Monitoring & Alerts
**Task:** Confirm that Azure Monitor alerts and metrics are active  
**Resource:** Azure Monitor + Activity Log  
**Notes:** Review alert rules and recent events

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/287bb950-3cce-4f2a-8eee-4949bc61ceba" />


---

### 🧠 Key Takeaways
- Verified all Azure resources and connectivity  
- Reviewed cost analysis and redundancy options  
- Confirmed monitoring, alerting, and tagging operations  
- Demonstrated efficiency using Azure CLI  
- Completed end-to-end validation and documentation

--- 


📘 *Created by Nichelle Fields – Azure Lab Series*



