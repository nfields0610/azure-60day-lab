## 🧩 Day 10 – Azure Policy Governance  
**Task:** Require a tag on all resources (Governance Enforcement)  
**Resource:** Azure Policy  
**Notes:** Enforce consistent tagging for cost management and compliance.

---

### 🎯 Objective  
Use Azure Policy to require that every resource in the **LABNN** resource group includes the tag  
`Environment = Lab`. This demonstrates real-world governance and tagging standards.

---

### 🪜 Step-by-Step Instructions

#### **Step 1 – Open Azure Policy**
- In the Azure Portal, search for **“Policy”**.  
- Click **Policy → Assignments → Assign Policy**.  

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/d178ac58-8179-41ac-b054-b1b07b08bace" />


---

#### **Step 2 – Select the Built-In Policy Definition**
- Under **Scope**, choose your **Subscription** and **Resource Group = LABNN**.  
- Under **Policy Definition**, click **Select** and choose **Require a tag on resources**.  

 <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/66afa475-efd1-42e7-babf-b508c7520c95" />


---

#### **Step 3 – Configure Parameters**
- Set **Tag Name = Environment**.  
- Leave **Tag Value** blank (policy only checks the tag exists).  
- Leave **Remediation** unchecked for this part.  
- Click **Review + Create → Create**.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/fb4119e9-17fe-456c-9fe5-e20f7c165629" />


---

#### **Step 4 – Verify Policy Assignment**
- Return to **Policy → Assignments**.  
- Confirm that your new assignment appears in the list as **Require a tag on resources**.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/203495e8-99f3-4643-9492-b9e6bd5546b0" />

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/1bfb3645-bee4-4b29-8306-847f6064d9e6" />

---

#### **Step 5 – Test Policy Enforcement (Without Tag)**
- Go to **Create a Resource → Storage Account**.  
- Use the following settings:  
  - **Performance:** Standard  
  - **Redundancy:** LRS  
  - **Access Tier:** Hot  
  - **Type:** Azure Blob Storage  
  - **Region:** Same as LABNN  
- Skip the **Tags** tab and try to **Review + Create → Create**.  
- You should receive an error: **RequestDisallowedByPolicy**.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/cdba1691-8c75-4f3d-909a-25931baefd13" />


---

#### **Step 6 – Create a Compliant Resource (With Tag)**
- Repeat the Storage Account creation.  
- On the **Tags** tab, add:  
  - **Name:** Environment  
  - **Value:** Lab  
- Click **Review + Create → Create**.  
- The deployment should succeed this time.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/2a446bdd-9fc7-430a-b04b-3bc7b1b6771b" />


---

### 💾 Storage Account Settings Used
| Setting | Value |
|----------|--------|
| Type | Azure Blob Storage |
| Performance | Standard |
| Redundancy | Locally Redundant (LRS) |
| Access Tier | Hot |
| Region | Same as LABNN |
| Tag | Environment = Lab |

---

### 🧾 Results
- Policy successfully blocked untagged resource creation.  
- Resource deployed normally after adding required tag.  
- Demonstrated effective governance enforcement in Azure.

---

### 🧠 What I Learned
> Azure Policy can enforce tagging rules to ensure cost tracking and resource consistency.  
> Missing tags cause deployment denial, while compliant resources deploy normally.

---
