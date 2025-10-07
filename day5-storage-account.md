# Day 5 – Azure Storage Account and Blob Upload Lab

**Goal:**  
Create and configure an Azure Storage Account, upload a blob, explore access tiers, and understand replication and cost trade-offs.

---

## 🧩 Step 1: Create a Storage Account
- **Name:** `labnnstorage01`  
- **Resource group:** `LABNN`  
- **Region:** Same as your VMs  
- **Performance:** Standard  
- **Redundancy:** Locally redundant (LRS)  
- **Access tier (account default):** Hot  

1. In the Azure Portal → search **Storage accounts** → click **+ Create**  
2. Enter the settings above  
3. Click **Review + Create → Create**  
4. Wait until deployment finishes

📸 *Screenshot 1: <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/dd4f31fe-7126-4447-82a9-4288494a8ffc" />


---

## 🧩 Step 2: Create a Blob Container
1. Go to **Storage Account → Containers**  
2. Click **+ Container**  
   - **Name:** `labfiles`  
   - **Public access level:** Private (or `Blob` if you want public access)  
3. Click **Create**

📸 *Screenshot 2: <img width="1366" height="1024" alt="image" src="https://github.com/user-attachments/assets/948bf35d-47fb-4f17-9519-40231de53b7b" />


---

## 🧩 Step 3: Upload a Test File
1. Open **Containers → labfiles**  
2. Click **Upload**  
3. Select a small test file (e.g., `labtest.txt`)  
4. Click **Upload**  
5. Verify the file appears in the container

📸 *Screenshot 3: ![image](https://github.com/user-attachments/assets/7c6d3de8-c117-4b56-bb41-507bfb4714b1)


---

## 🧩 Step 4: Set Blob Access Tier
1. Click the uploaded blob → **Change tier**  
2. **Initial tier:** Hot (for immediate testing)  
3. Optional: change tier to Cool → Cold → Archive to observe cost/performance

📸 *Screenshot 4: Blob properties showing tier selection*  

### **Blob Access Tier Table**

| Tier      | Storage Cost | Access/Read Cost | Retrieval Speed | Use Case |
|----------|-------------|----------------|----------------|---------|
| **Hot**  | Highest     | Lowest         | Immediate      | Frequently accessed data |
| **Cool** | Lower       | Higher than Hot| Seconds        | Infrequently accessed data, backups |
| **Cold** | Even lower  | Higher than Cool| Minutes       | Rarely accessed data, long-term storage |
| **Archive** | Lowest   | Highest        | Hours          | Compliance, archival, long-term retention |

---

## 🧩 Step 5: Configure Access Level and Public URL
1. Click **Access level** for the container → select:  
   - **Blob (anonymous read access for blobs only)** → allows public read for the blob only  
2. Click **OK / Save**  
3. Click your blob → https://labnnstorage01.blob.core.windows.net/labfiles/labtest.txt

Example URL (replace with your actual URL):  
