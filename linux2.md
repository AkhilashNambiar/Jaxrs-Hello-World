## **Linux Administration Mini-Project Assignment**  
**Title:** *Setting Up a User Management & Storage System in Linux*  

### **Objective:**  
Students will apply their knowledge of Linux commands to **create users, manage groups, set permissions, work with filesystems, and handle processes** in a real-world scenario.  

---

### **Scenario:**  
You have been hired as a **Linux System Administrator** for a small company. Your manager has given you the following tasks to set up a **basic user management system, configure file storage, and manage processes** on a newly installed Linux server.  

---

### **Tasks:**  

#### **📌 Task 1: User & Group Management (20 Marks)**  
🔹 **Create three users**: `dev_user`, `admin_user`, and `test_user`.  
🔹 **Create two groups**: `developers` and `admins`.  
🔹 Assign `dev_user` to the `developers` group and `admin_user` to the `admins` group.  
🔹 Set a password for each user.  
🔹 Verify the users and groups created.  

📌 **Commands to Use:**  
- `useradd`, `passwd`, `groupadd`, `usermod`, `id`, `cat /etc/passwd`, `cat /etc/group`  

✅ **Deliverable:** A text file (`users_groups_setup.txt`) containing the commands used and verification outputs.  

---

#### **📌 Task 2: File & Directory Permissions (20 Marks)**  
🔹 Create a directory `/project_files` and set the following permissions:  
   - Only `admin_user` should have full access (`rwx`).  
   - `dev_user` should have read (`r--`) access.  
   - `test_user` should have no access.  
🔹 Create a text file `confidential.txt` inside `/project_files` and make it **read-only** for all users except `admin_user`.  

📌 **Commands to Use:**  
- `mkdir`, `touch`, `chmod`, `chown`, `ls -l`, `sudo`  

✅ **Deliverable:** A text file (`permissions_setup.txt`) with commands and `ls -l` output showing permissions.  

---

#### **📌 Task 3: Storage & File System Management (20 Marks)**  
🔹 Create a **new partition** (using a virtual disk or loop device if no physical disk is available).  
🔹 Format the partition as **ext4** and mount it at `/data`.  
🔹 Create a **tar archive** of `/project_files` and save it in `/data`.  
🔹 Compress the archive using `bzip2`.  

📌 **Commands to Use:**  
- `fdisk`, `mkfs.ext4`, `mount`, `tar -cvf`, `bzip2`, `lsblk`, `df -h`  

✅ **Deliverable:** A text file (`storage_setup.txt`) containing partition details, mount status, and archive details.  

---

#### **📌 Task 4: Process & System Management (20 Marks)**  
🔹 Run a background process using `sleep 600 &` and find its **process ID (PID)**.  
🔹 List all running processes and filter results for the `sleep` command.  
🔹 Kill the process using its PID and verify if it stopped.  
🔹 Display active system services using `systemctl`.  

📌 **Commands to Use:**  
- `sleep`, `ps aux`, `grep`, `kill`, `systemctl list-units --type=service`  

✅ **Deliverable:** A text file (`process_management.txt`) with command outputs.  

---

