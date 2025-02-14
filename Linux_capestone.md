 a **capstone project** for a **Linux Administrator job role** based on the topics provided. The project is designed to simulate real-world challenges that a Linux admin might face, requiring the candidate to apply their knowledge across multiple chapters. The candidate must use **CentOS**, **Ubuntu**, or **Kali Linux** to solve the problems.

---

## **Capstone Project: Linux Administrator Role**

### **Project Title**: **Enterprise Linux Server Management and Optimization**

---

### **Scenario**:
You are hired as a **Linux Administrator** for a mid-sized company. The company has a mix of servers running **CentOS**, **Ubuntu**, and **Kali Linux**. Your task is to manage, optimize, and secure these servers while addressing specific business requirements. The solution architect has provided a list of requirements and concerns that you need to address.

---

### **Tasks and Requirements**

#### **1. User and Group Management**
- **Requirement**: The company has three departments: **IT**, **HR**, and **Finance**. Create users and groups for each department.
  - Create users: `it_user1`, `hr_user1`, `finance_user1`.
  - Create groups: `it_group`, `hr_group`, `finance_group`.
  - Assign users to their respective groups.
  - Set passwords for all users.
  - Ensure that users in the `it_group` have sudo privileges.

---

#### **2. File System and Permissions**
- **Requirement**: Create a directory structure for each department under `/company`.
  - Directory structure:
    ```
    /company
    ├── IT
    ├── HR
    └── Finance
    ```
  - Set permissions so that:
    - Only members of `it_group` can access `/company/IT`.
    - Only members of `hr_group` can access `/company/HR`.
    - Only members of `finance_group` can access `/company/Finance`.
  - Create a shared directory `/company/shared` where all users can read and write files.

---

#### **3. Storage Management**
- **Requirement**: The company has added a new disk (`/dev/sdb`) to the server. Configure it for use.
  - Partition the disk into two partitions: one for data storage (`/dev/sdb1`) and one for swap (`/dev/sdb2`).
  - Format the data partition with `ext4` and mount it at `/mnt/data`.
  - Configure the swap partition and enable it.
  - Ensure the mount points persist after a reboot.

---

#### **4. Process Management**
- **Requirement**: The company runs a critical application that occasionally becomes unresponsive.
  - Write a script (`monitor_app.sh`) to monitor the application process and restart it if it stops.
  - Schedule the script to run every 5 minutes using `cron`.

---

#### **5. Monitoring and Logging**
- **Requirement**: The company wants to monitor server performance and log critical events.
  - Install and configure `htop` for real-time monitoring.
  - Set up a log rotation policy for `/var/log/syslog` to keep logs for 7 days.

---

#### **6. Networking**
- **Requirement**: The company wants to ensure secure and efficient network communication.
  - Configure a static IP address for the server.
  - Open port `80` for HTTP and port `22` for SSH in the firewall.
  - Block all other incoming ports.
  - Set up a DNS resolver to use `8.8.8.8` as the primary DNS server.

---

#### **7. Software Management**
- **Requirement**: The company needs a web server for hosting internal applications.
  - Install and configure `Apache` on the server.
  - Ensure the service starts automatically on boot.
  - Remove any unused packages to free up space.

---

#### **8. Secure Shell (SSH) and Secure Copy (SCP)**
- **Requirement**: The company wants to ensure secure remote access and file transfers.
  - Configure SSH key-based authentication for all users.
  - Disable password-based SSH login.
  - Write a script to securely copy files from the server to a remote machine using `scp`.

---

#### **9. Backup and Archiving**
- **Requirement**: The company wants to ensure data is backed up regularly.
  - Write a script (`backup.sh`) to archive and compress the `/company` directory.
  - Schedule the script to run every night at 2 AM using `cron`.

---

#### **10. Security Hardening**
- **Requirement**: The company wants to improve server security.
  - Disable root login via SSH.
  - Set up a firewall to allow only necessary ports.
  - Install and configure `fail2ban` to prevent brute-force attacks.

---

### **Deliverables**
1. **Documentation**:
   - A detailed report explaining the steps taken to complete each task.
   - Include screenshots or command outputs where necessary.
2. **Scripts**:
   - Provide all scripts created during the project (`monitor_app.sh`, `backup.sh`, etc.).
3. **Configuration Files**:
   - Include any configuration files modified (e.g., `/etc/fstab`, `/etc/ssh/sshd_config`, `/etc/crontab`).

---

### **Evaluation Criteria**
1. **Accuracy**: Solutions must meet the requirements exactly.
2. **Efficiency**: Use the most efficient commands and methods.
3. **Security**: Ensure all configurations follow security best practices.
4. **Documentation**: Clear and detailed documentation is required.
5. **Creativity**: Innovative solutions to problems will be rewarded.

---

### **Tools and Technologies**
- **Operating Systems**: CentOS, Ubuntu.
- **Tools**: `htop`, `cron`, `Apache`, `fail2ban`, `tar`, `scp`, `ssh`, `firewalld`, `systemd`.

