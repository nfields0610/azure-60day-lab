# 🧩 Day 7 – Identity & Access (Azure AD + RBAC)

**Goal:**  
Strengthen your understanding of Azure Identity by creating users, assigning roles, and reviewing activity logs using Microsoft Entra ID.  
This lab demonstrates how Azure manages authentication, authorization, and activity tracking — all free within your $200 credit plan.

---

## 🔧 Resources
| Resource | Type | Purpose |
|-----------|------|----------|
| Microsoft Entra ID | Azure Service | Identity and Access Management |
| Users | Directory Objects | Test accounts for permissions |
| Roles | RBAC | Assign least-privilege access |
| Logs | Monitoring | Track user activity and sign-in behavior |

💰 **Cost:** Free-tier only (no credit used)

---

## 🧠 Learning Objectives
- Create new Azure AD users  
- Assign and verify Azure RBAC roles  
- Test sign-in and password reset  
- Review sign-in and audit logs  

---

## 🪜 Step-by-Step Tasks

### 🧱 Task 1 – Create Azure AD Users
**Purpose:** Build your lab identity environment.

**Steps:**
1. Open the [Azure Portal](https://portal.azure.com).  
2. Navigate to **Microsoft Entra ID → Users → + New user → Create user**.  
3. Fill in details:  
   - **User name:** `labuser1@<yourtenant>.onmicrosoft.com`  
   - **Name:** `Lab User 1`  
   - **Password:** Auto-generate  
4. Click **Review + Create → Create.**

📸 *Screenshot:
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/916178ae-7c8f-42ed-b3c1-029d65f250f8" />

---

### 🧩 Task 2 – Assign Roles (RBAC)
**Purpose:** Give your user limited read-only access for security testing.

**Steps:**
1. In Entra ID, select **Lab User 1 → Assigned roles → + Add assignment.**  
2. Search and choose **Global Reader** (read-only role).  
3. Click **Add** to assign.

📸 *Screenshot:* 
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/94737c05-db2b-47d1-bd79-c52e08d1a2ea" />


---

### 🔐 Task 3 – Test Sign-In
**Purpose:** Validate the user account works as expected.

**Steps:**
1. Open a private browser window.  
2. Go to [https://portal.azure.com](https://portal.azure.com).  
3. Log in as **Lab User 1** using the temporary password.  
4. When prompted, reset the password.  
5. Note the MFA setup prompt — this confirms **Security Defaults** are active.  


---

### 🧾 Task 4 – Review Logs
**Purpose:** View activity and confirm the user’s sign-in was logged.

**Steps:**
1. Go to **Entra ID → Monitoring → Sign-in logs.**  
2. Filter by **Lab User 1**.  
3. Observe:
   - Sign-in time  
   - Application accessed  
   - Status (Interrupted = MFA prompt)  
4. Open **Audit logs** and verify:
   - User creation  
   - Role assignment  

📸 *<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/995554ba-5531-4491-b645-6768c1c4e487" />

---

## 🧩 Summary
✅ Created and tested Azure AD users  
✅ Assigned Global Reader role for least privilege  
✅ Tested MFA behavior during sign-in  
✅ Reviewed sign-in and audit logs  

---

