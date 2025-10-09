# 🌐 Day 8 – App Service (Web App Deployment & Monitoring)

**Goal:**  
Deploy and manage a simple web application using Azure App Service.  
This lab demonstrates how to host a web app on the Azure platform, connect it to an App Service Plan, and monitor its activity — all on the free tier to preserve credits.

---

## 🔧 Resources

| Resource | Type | Purpose |
|-----------|------|----------|
| App Service Plan | Compute | Defines the compute resources for the web app |
| Web App | Platform | Hosts your web application |
| Log Stream / Diagnostic Logs | Monitoring | View app performance and activity in real time |

💰 **Cost:** Free-tier (F1) — no credits used.

---

## 🧱 Task 1 – Create App Service Plan

**Purpose:** Define the compute environment that your web app will run on.

### Steps:
1. In the [Azure Portal](https://portal.azure.com), select **+ Create a resource**.  
2. Search for **App Service Plan** and click **Create**.  
3. Under **Basics**:
   - **Subscription:** Azure Free Trial  
   - **Resource Group:** `LABNN`  
   - **Name:** `labnn-appplan`  
   - **Operating System:** Windows  
   - **Region:** (same as your other resources)  
   - **Pricing Plan:** Free (F1)  
4. Click **Review + Create → Create.**

📸 *Screenshot:* <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/0072c0f4-b079-4af6-8bc6-24a6cbbca685" />

> App Service Plan overview showing Free (F1) plan.

---

## 🧩 Task 2 – Create a Web App

**Purpose:** Deploy your first Azure-hosted web app.

### Steps:
1. From Azure Portal home, click **+ Create a resource → Web App → Create.**  
2. Fill out the basics:
   - **Resource Group:** `LABNN`  
   - **Name:** `labnnwebapp01` *(must be globally unique)*  
   - **Publish:** Code  
   - **Runtime stack:** `.NET 8 (LTS)`  
   - **Operating System:** Windows  
   - **Region:** same as App Service Plan  
   - **App Service Plan:** Select your existing plan (`labnn-appplan`)  
3. Click **Review + Create → Create.**

📸 *Screenshot:* <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/56b4d95d-15a5-4c29-9b68-26b851145713" />

> Web App creation summary before deployment.

---

## 🌍 Task 3 – Test the Web App

**Purpose:** Verify that your web app deployed successfully.

### Steps:
1. After deployment, click **Go to Resource.**  
2. On the overview page, click the **default domain URL** to open your site.  
3. The page should display: *“Your web app is up and running!”*

📸 *Screenshot:* <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/c4183a72-ff48-4281-b126-8acf87843177" />

> Browser showing the default Azure Web App welcome page.

---

## 🧾 Task 4 – Enable Diagnostic Logs

**Purpose:** Capture live events and monitor web app activity.

### Steps:
1. In your Web App, go to **Monitoring → App Service Logs.**  
2. Enable:
   - **Application Logging (Filesystem):** On  
   - **Level:** Information  
3. Click **Save.**  
4. Navigate to **Log Stream** to view real-time app logs.

📸 *Screenshot:*  <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/b6fb8883-2634-4cf4-90f7-3df757f406c7" />

> Live log stream showing activity for your web app.

---

## ⚙️ Task 5 – Explore Scaling (Optional)

**Purpose:** Learn how App Service Plans scale as workloads increase.

### Steps:
1. Open your **App Service Plan.**  
2. Select **Scale Up (App Service Plan).**  
3. Observe the different tiers (B1, S1, etc.) — but do **not upgrade.**  
4. Note differences in CPU, RAM, and features per tier.

📸 *Screenshot:*  <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/114e1a60-c957-4b7e-ab6c-7b49be91fa3e" />

> View of available App Service pricing tiers.

---

## 🧠 What You Learned

- How to create and configure an App Service Plan  
- How to deploy a web app in Azure  
- How to monitor app activity with Log Stream  
- How scaling options affect cost and performance  

---

