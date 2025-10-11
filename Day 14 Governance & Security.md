## 🧩 Day 11 – Governance & Security  
**Task:** Explore Microsoft Purview (Free Tier) and Microsoft Sentinel (Free Tier)  
**Resource:** Purview + Sentinel  
**Notes:** Test data-governance and security-monitoring features in Azure.

---

### 🎯 Objective  
Learn how Azure provides **data governance** and **security analytics** through Microsoft Purview and Microsoft Sentinel.

---

## ☁️ Section 1 – Microsoft Purview (Data Governance)

### Step 1 – Create Purview Account  
1. Search **“Purview”** → select **Microsoft Purview Accounts**.  
2. Click **+ Create** → fill in:  
   - **Name:** `labpurview01`  
   - **Subscription:** Free Trial  
   - **Resource group:** LABNN  
   - **Region:** same region as existing labs  
   - **Pricing tier:** *Free*  
3. Click **Review + Create → Create**.  

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/9ecee6db-be01-43ce-a553-3511cf376b0c" />


---

### Step 2 – Open Purview Studio  
1. After deployment → **Go to resource → Open Microsoft Purview Studio**.  
2. Portal opens at `https://web.purview.azure.com`.  
3. Review panels → **Data Map, Data Catalog, Insights.**

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/5eafa821-2339-40ac-844e-ecd0c31abccb" />


---

### Step 3 – Register Azure Blob Storage & Create Scan Rule Set  
1. In **Data Map**, click **Register → Azure Blob Storage**.  
2. Choose:  
   - **Subscription:** Free Trial  
   - **Storage account:** `labnnstorage01`  
   - **Name:** `labblobstorage`  
3. Under *Scan rule set*, click **+ New scan rule set** and fill in:  
   - **Data source type:** Azure Blob Storage  
   - **Scan rule set name:** `LabBlobScanRule`  
   - **Description:** `Default data classification scan for lab storage.`  
4. Click **Create**, then select `LabBlobScanRule` and click **Finish**.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/a4d86beb-3770-4f6b-862b-ee5b84cc7d16" />


---

### Step 4 – Review Insights  
1. Open **Insights** panel.  
2. Free tier shows *“No data available.”*  
3. Note that full Insights require Data Map capacity.  

> **Observation:** Purview successfully registered resources but shows no visual Insights on the free tier – expected behavior.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/1a38fcad-734b-408e-b2cc-2d0fb91ede29" />


---

## 🔐 Section 2 – Microsoft Sentinel (Security Analytics)

### Step 5A – Create Log Analytics Workspace  
1. Search **“Log Analytics workspaces.”**  
2. Click **+ Create** → enter:  
   - **Name:** `lablog01`  
   - **Resource group:** LABNN  
   - **Region:** same as Purview  
3. Click **Review + Create → Create**.  

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/6887ad55-ac87-40d1-b1e9-eee399edebcd" />


---

### Step 5B – Add Microsoft Sentinel  
1. Search **“Microsoft Sentinel.”**  
2. Click **+ Create** → select workspace `lablog01`.  
3. Ignore “Pay-As-You-Go Pricing” notice → safe under free trial.  
4. Click **Review + Create → Create.**

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/2da89fd6-6d09-4207-b448-d8c4738b0bac" />


---

### Step 5C – Explore Sentinel Overview (New UI)  
1. Open `lablog01` workspace.  
2. Top tabs show **Overview | Logs | Guides | Search | Query Hub**.  
3. Explore each briefly to understand layout.


<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/34be76bd-c79c-4345-9920-7179f71a0131" />

---

### Step 5D – Connect Azure Activity Logs (Modern Method)  
1. Go to **Monitor → Activity Log → Export Activity Logs**.  
2. Click **+ Add diagnostic setting → Name:** `SendToSentinel`.  
3. Select categories: Administrative, Security, ServiceHealth, Policy.  
4. Choose **Send to Log Analytics workspace → lablog01 → Save.**  
5. Wait 15–30 min for events to appear.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/6fef64d0-c0b1-4ae6-b6dd-766147aba4ad" />


---

### Step 5E – Use Query Hub to Confirm Logs  
1. In Sentinel → **Query Hub**.  
2. Review tabs: All queries, Applications, Audit, Networking, Security, Storage, Workloads.  
3. Select **Audit** category.  
4. Run sample query or paste:  

   ```kql
   AzureActivity
   | sort by TimeGenerated desc
   | take 10
