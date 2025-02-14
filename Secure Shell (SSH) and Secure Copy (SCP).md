For **Secure Shell (SSH) and Secure Copy (SCP)**, follow these step-by-step instructions.  

Your **VM Details**:  
- **IP Address**: `20.191.95.222`  
- **Username**: `akhilash`  
- **Password**: `Akhilash@123`  

---

## **Step 1: Connect to Your VM Using SSH**
On your local machine (Linux/Mac/Windows with Git Bash or PowerShell):  

```bash
ssh akhilash@20.191.95.222
```
- If prompted with `Are you sure you want to continue connecting? (yes/no)`, type `yes` and press **Enter**.  
- Enter the password: `Akhilash@123`.  

👉 **Success Check**: If login is successful, you'll see a terminal prompt like:  
```
akhilash@your-vm:~$
```

---

## **Step 2: Enable SSH on the VM (if not enabled)**
If SSH is not working, enable it:  

```bash
sudo systemctl start ssh
sudo systemctl enable ssh
sudo systemctl status ssh
```

If `ssh` is not installed:  
```bash
sudo apt update && sudo apt install openssh-server -y
```

---

## **Step 3: Securely Copy a File from Local to VM Using SCP**
To **copy a file from your local machine to the VM**:  
```bash
scp /path/to/local/file.txt akhilash@20.191.95.222:/home/akhilash/
```
Example:
```bash
scp myfile.txt akhilash@20.191.95.222:/home/akhilash/
```
- Enter the password (`Akhilash@123`) when prompted.

---

## **Step 4: Securely Copy a File from VM to Local Machine**
To **download a file from the VM to your local machine**:  
```bash
scp akhilash@20.191.95.222:/home/akhilash/myfile.txt /local/destination/
```
Example:
```bash
scp akhilash@20.191.95.222:/home/akhilash/myfile.txt ~/Downloads/
```

---

## **Step 5: Securely Copy a Directory**
Copy an entire directory **from local to VM**:
```bash
scp -r /path/to/local/dir akhilash@20.191.95.222:/home/akhilash/
```

Copy an entire directory **from VM to local**:
```bash
scp -r akhilash@20.191.95.222:/home/akhilash/mydir ~/Downloads/
```

---

## **Step 6: Exit SSH Session**
To exit the SSH session:  
```bash
exit
```

---

### **Common Issues & Fixes**
✅ **Permission denied (publickey, password):**  
- Check if SSH is running:  
  ```bash
  sudo systemctl status ssh
  ```
- Restart SSH if needed:  
  ```bash
  sudo systemctl restart ssh
  ```

✅ **Connection timed out:**  
- Ensure the VM has port **22 open** in firewall settings:  
  ```bash
  sudo ufw allow 22
  sudo ufw enable
  ```

✅ **scp: No such file or directory**  
- Ensure the source file exists before copying.

---

### **Next Steps**
- Automate login with SSH keys (`ssh-keygen` and `ssh-copy-id`).  
- Use `rsync` for better file transfers.  

Let me know if you need further help! 🚀
