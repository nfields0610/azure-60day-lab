# 🧩 Day 6 – Connect Azure Storage Account to a Windows VM

**Lab Goal:**  
Integrate Azure **Storage** and **Compute** by connecting a File Share from your storage account (`labnnstorage01`) to your Windows VM (private IP: 10.0.0.4).  
This demonstrates how Azure resources communicate securely within a virtual network.

---

## 🪜 Steps

### **Step 1 – Create a File Share**
1. In **Azure Portal → Storage accounts → labnnstorage01**
2. Under **Data storage**, select **File shares → + File share**
3. Enter:
   - **Name:** `labshare`
   - **Tier:** `Transaction optimized`
4. Click **Create**

📸 **Screenshot #1:** <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/9052c754-52c2-4540-bcc9-b5a3c9369879" />


---

### **Step 2 – Generate Connection Script**
1. Inside `labnnstorage01` → **File shares → labshare**
2. Click **Connect** 
menu bar)
3. Under “Select your OS,” choose **Windows**
4. Copy the generated PowerShell script

📸 **Screenshot 

---<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/e8f1a7fd-4200-4455-a424-6bed0186f102" />


### **Step 3 – Retrieve Storage Account Key**
1. In the same storage account → **Security + networking → Access keys**
2. Click **Show keys** → copy **Key1** (used to authenticate)

📸 **Screenshot #3:** Access keys screen (blur or hide the actual key for GitHub).

---
<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/bd0297ac-cf72-4a3c-bd27-0c2e03979595" />

### **Step 4 – Verify Connectivity from VM**
1. RDP into your **Windows VM**
2. Open **PowerShell as Administrator**
3. Test network connection to Azure Storage:

   ```powershell
   Test-NetConnection -ComputerName labnnstorage01.file.core.windows.net -Port 445
   net use Z: \\labnnstorage01.file.core.windows.net\labshare /user:Azure\labnnstorage01 <key>
   The command completed successfully.
