### **Linux Administrator Assignments – Ubuntu Server**  

#### **1. User & Group Management**  
- Create a new user named `developer1` and add them to a group called `devteam`.  
- Ensure `developer1` has **sudo access** but cannot change system-critical files.  
- Set up a shared directory `/opt/devteam` where only `devteam` members can **read, write, and execute** files.  
- Restrict `developer1` from logging in via SSH but allow them to execute commands remotely.  
- Delete the user `developer1` but **preserve their home directory and files**.  

---

#### **2. File System & Storage (LVM Setup & Mounting)**  
- Create a **Logical Volume (LVM)** setup using a **20GB disk** (`/dev/xvdb`).  
- Divide it into two partitions:  
  - **10GB partition** formatted as `ext4`, mounted at `/data`.  
  - **10GB partition** formatted as `xfs`, mounted at `/backup`.  
- Ensure both mounts are **persistent after reboot**.  
- Expand the `/data` partition by **5GB** dynamically without unmounting it.  
- Take a **snapshot of the `/backup` partition** before deleting it.  

---

#### **3. Process & Job Management**  
- Identify the top **5 CPU-consuming and memory-intensive processes** and log their details in `/var/log/process_report.txt`.  
- Find and kill a **long-running process** named `auto_backup.sh` without using its PID directly.  
- Schedule a cron job that runs every Sunday at 2 AM to **clear system logs older than 30 days**.  
- Set up a process that should automatically restart **if it crashes**.  
- Restrict user `developer1` from running **specific processes**, such as `vim` and `wget`.  

---

#### **4. Monitoring & Logging (Deep Analysis)**  
- Generate a **real-time system resource usage report** and save it as `/var/log/sys_monitor.log`. The report should include:  
  - CPU & Memory usage of each process.  
  - Network bandwidth usage per interface.  
  - Disk I/O statistics.  
  - Logged-in users with active SSH sessions.  
  - Services consuming the highest swap memory.  
- Find all **failed login attempts** from the system logs and extract the usernames and IP addresses.  
- Set up **automatic log rotation** for `/var/log/sys_monitor.log` to ensure it does not exceed 100MB.  
- Track the **real-time disk usage** and send an alert if any partition exceeds **80% capacity**.  
- Monitor a log file (`/var/log/app.log`) and trigger a script whenever the word "ERROR" appears.  

---

#### **5. Networking & Security**  
- Block all incoming connections **except SSH and HTTP(S)**.  
- Set up a **firewall rule** to allow SSH access only from a specific IP range (`192.168.1.0/24`).  
- Disable root login via SSH but allow `sudo` users to execute commands remotely.  
- Configure a rule to **automatically ban** an IP after 3 failed login attempts.  
- Implement a script that checks and reports all **open ports** on the system every 12 hours.  

---

#### **6. Backup & Disaster Recovery**  
- Create a backup policy that archives `/home` every **midnight** and stores the last **7 days' worth** of backups.  
- Compress the backup files using the best **compression ratio** without consuming excessive CPU.  
- Implement a backup strategy where `/var/log` is automatically backed up to `/backup/logs`.  
- Simulate a **disaster recovery scenario** by restoring a deleted user along with their home directory.  
- Restore a **corrupted partition** using a previously created snapshot.  

-
