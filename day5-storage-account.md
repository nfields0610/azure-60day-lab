# Day 5 – Azure Storage Account and Blob Upload Lab

**Goal:**  
Create and configure an Azure Storage Account, upload a blob, and understand access tiers and redundancy.

---

## 🧩 Step 1: Create a Storage Account
- **Name:** `labnnstorage01`
- **Region:** same as your VMs
- **Performance:** Standard
- **Redundancy:** Locally redundant (LRS)
- **Access tier:** Hot

1. In the Azure Portal → “Storage Accounts” → **Create**
2. Choose your existing **resource group (LABNN)**
3. Enter the settings above and click **Review + Create**
4. Wait until the deployment finishes.

---

## 🧩 Step 2: Create a Blob Container
1. Open the new storage account → **Containers**
2. Click **+ Container**
3. **Name:** `labfiles`
4. **Public access level:** Private
5. Click **Create**

---

## 🧩 Step 3: Upload a File
1. Go to **Containers → labfiles**
2. Click **Upload**
3. Choose a small text file (e.g., `labtest.txt`)
4. Confirm it appears in the container.

---

## 🧩 Step 4: Experiment with Access Tiers
1. In the blob properties, change the tier: Hot → Cool → Archive  
2. Observe pricing/availability changes in the right panel.

---

## ✅ Validation
- Blob successfully uploaded  
- Able to view metadata  
- Understand the cost/performance trade-offs between tiers  

---

**Next:**  
Prepare to integrate this storage account with your VMs for Day 6.
