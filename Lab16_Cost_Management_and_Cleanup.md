## Day 13 – Cost Management & Cleanup

### Extended Description
This lab focused on Azure **Cost Management**, including analyzing spending, setting up a **budget alert**, and cleaning up unused resources to maximize free-tier credits.  
By using both the **Azure Portal** and **Cloud Shell CLI**, I learned how to manage cloud costs and maintain a healthy resource environment, just like a real enterprise engineer following FinOps best practices.

---

### 🪜 Steps Completed

#### Step 1 – Review Cost Analysis
- Navigated to **Cost Management + Billing → Reporting and Analysis → Cost Analysis (Preview)**.  
- Verified scope under **Free Trial subscription**.  
- Switched to **Daily Cost view** since “Cost by Service” had no billable usage yet.  
- Filtered by **Resource Group = LABNN** to visualize lab usage.  
- Adjusted the date range to **Last 30 days**.  

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/ab91f008-5d51-404f-813b-1ad98b898286" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/f19d93a4-82a7-40b2-bc81-40ea5d416d7d" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/beb8bbc6-65f2-46cf-b5bc-c7b6a5737fe4" />



---

#### Step 2 – Create Budget & Alert
- Opened **Budgets** under **Reporting and Analysis**.  
- Created new budget:  
  - **Name:** LAB-Monthly-Budget  
  - **Amount:** $10 per month  
  - **Reset period:** Monthly  
  - **Thresholds:** 50 %, 80 %, 100 %  
  - **Email Recipient:** Primary account  
- Verified alert thresholds and budget progress ring.

  <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/589d1713-7e1f-4adf-97e0-9042cb908266" />
  <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/3cf586ac-ebfb-4a03-aa65-d7c315158346" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/84422848-6802-46ad-bf2c-10742e3cb27c" />
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/fe523fda-d72c-4277-a6b9-36bc916679fa" />

---

#### Step 3 – Resource Audit & Deallocation
Used **Azure Cloud Shell (Bash)** to list and deallocate unused VMs:

```bash
# List all resources in LABNN
az resource list --resource-group LABNN -o table

# List VM power states
az vm list -d --query "[].{Name:name, PowerState:powerState}" -o table

# Stop and deallocate VM to save credits
az vm stop --name winlabvm02 --resource-group LABNN
az vm deallocate --name winlabvm02 --resource-group LABNN

```
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/26b160f7-155d-40cf-bd84-e442c72172b7" />

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/c54bcb67-96e5-4451-b78e-79d0caba55ce" />


💡 **Optional cleanup commands** (to practice later):  
```bash
az disk list --query "[?managedBy==null].{Name:name}" -o table
az snapshot list --query "[].{Name:name, SizeGB:diskSizeGb}" -o table
```

---

### 🧠 Notes & Reflection
> - Azure Cost Management tools help track and forecast cloud usage, even on free tiers.  
> - Budgets and alerts prevent overspending and enable proactive monitoring.  
> - Using Cloud Shell made the cleanup faster and introduced me to real-world Azure CLI automation.  
> - This lab builds the foundation for cost optimization in my future Healthcare POC project.

---

### 💻 CLI Practice Section
```bash
# List all resources in LABNN
az resource list --resource-group LABNN -o table

# List all VMs with power states
az vm list -d --query "[].{Name:name, PowerState:powerState}" -o table

# Show total number of resources in LABNN
az resource list --resource-group LABNN --query "length([])"

# Get subscription ID
az account show --query id -o tsv
```

---

