# ⚙️ Day 9 – Serverless & Automation (Function App + Logic App)

**Goal:**  
Understand how Azure serverless services automate tasks and run code without managing servers.  
In this lab, you created an **Azure Function App** and **Logic App** to explore serverless automation concepts and deployment options within the free tier.

---

## 🔧 Resources

| Resource | Type | Purpose |
|-----------|------|----------|
| Function App | Serverless compute | Host code or functions triggered by events |
| Logic App | Automation workflow | Connect and automate cloud-based actions |
| Storage Account | Required by Function App | Automatically managed by Azure |

💰 **Cost:** Free-tier — no credits used.

---

## 🧱 Task 1 – Create Function App

**Purpose:** Create a serverless app that can respond to triggers or events.

### Steps
1. In the [Azure Portal](https://portal.azure.com), select **+ Create a resource → Function App → Create.**
2. Under **Basics:**
   - **Subscription:** Azure Free Trial  
   - **Resource Group:** `LABNN`  
   - **Function App Name:** `labnn-func01`  
   - **Runtime stack:** `.NET 8 (LTS)`  
   - **Operating System:** Windows  
   - **Region:** Same as previous labs (e.g., East US)  
   - **Hosting Plan Type:** **Consumption (Serverless)** ✅  
3. Skip storage selection (Azure automatically creates and assigns one).  
4. Click **Review + Create → Create.**

📸 *Screenshot:* <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/0c39d73c-9140-4cb0-b50a-ff14d072960e" />

> Function App overview showing runtime stack, region, and hosting plan.

---

## 🧩 Task 2 – Review Deployment Options

**Purpose:** Understand how Azure’s new Function App model supports multiple creation methods.

### Observations:
- The Function App deployed successfully and is in the **Running** state.  
- The new Azure experience (for .NET 8) no longer supports in-portal function creation.  
- Function code must now be deployed using:
  - **Visual Studio Code**
  - **Visual Studio**
  - **Azure CLI**
  - or **GitHub Actions** for CI/CD  

💡 *In this lab, the focus is on infrastructure setup and understanding deployment options rather than coding.*

📸 *Screenshot:* <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/81bee92d-d37f-42ae-8f37-578f1cba8225" />

> Confirm Function App is active and using the Consumption (Serverless) plan.

---

## 🧠 What You Learned (Function App)
- Created a **Function App** using the Consumption (Serverless) model.  
- Learned that Azure automatically provisions required storage for serverless apps.  
- Explored modern deployment paths (VS Code, CLI, CI/CD).  
- Understood how serverless architecture removes the need to manage servers.

---

## 🧾 Task 3 – Logic App (Optional for Automation)

**Purpose:** Automate cloud workflows without writing code.  
(*This task can be completed in a future lab.*)

Example future steps:
1. Create a Logic App using the **Recurrence** trigger.  
2. Add an **HTTP** or **Email** action.  
3. Test automation workflows to simulate real enterprise scenarios.

📸 *Placeholder Screenshot:* `Day9_LogicApp_Create.png`

---

## 🧩 Summary

✅ Created Function App using serverless compute  
✅ Verified automatic storage and deployment options  
☑️ (Optional) Next: Add Logic App or trigger automation later

---


