## 🧩 Day 11 – Azure Key Vault Secrets  
**Task:** Store and retrieve secrets securely using Azure Key Vault  
**Resource:** Azure Key Vault  
**Notes:** Demonstrate secure secret storage, retrieval, and role-based access control (RBAC).

---

### 🎯 Objective  
Create a Key Vault in LABNN, store a secret, and retrieve it securely from the Azure Portal and PowerShell.  
This demonstrates secure credential management and identity-based access control in Azure.

---

### 🪜 Step-by-Step Instructions

#### **Step 1 – Create a Key Vault**
- In the Azure Portal, search **“Key Vaults” → Create**.  
- **Resource Group:** LABNN  
- **Key Vault Name:** `labnn-keyvault01`  
- **Region:** Same as LABNN  
- **Pricing Tier:** Standard  
- Click **Review + Create → Create**.  

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/e1583671-afdb-41e8-940a-aa18e1049d56" />


---

#### **Step 2 – Configure Access (RBAC Permissions)**
- In your Key Vault → **Access control (IAM)** → **Add role assignment**.  

- **Assign access to:** User, group, or service principal  
- **Members:** Your Azure account  
- Click **Review + Assign**.  
- Wait 1–2 minutes for permissions to apply.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/85bc3442-3fa7-49e6-a351-5929f405a4ce" />


---

#### **Step 3 – Add a Secret**
- Inside the vault → **Objects → Secrets → + Generate/Import**.  
- **Name:** `SQLPassword`  
- **Value:** `MySecurePassword123!` *(or any test value)*  
- Click **Create**.  

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/a167e053-2200-43eb-9d74-dd6d9b054155" />


---

#### **Step 4 – Retrieve the Secret (Portal)**
- In the Key Vault → **Secrets → SQLPassword → Current Version**.  
- Click **Show Secret Value** to display it.

<img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/d7126fa6-83c9-47ff-a7fd-2b4609524f91" />


---

#### **Step 5 – Retrieve the Secret (PowerShell)**
- Open **Cloud Shell (PowerShell)** in the top toolbar.  
- Run the following:
  ```powershell
  # Connect (if not already signed in)
  Connect-AzAccount

  # Retrieve the secret
  $secret = Get-AzKeyVaultSecret -VaultName "labnn-keyvault01" -Name "SQLPassword"
  $secret.SecretValueText
  
