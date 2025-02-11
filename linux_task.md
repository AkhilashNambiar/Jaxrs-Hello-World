### **Linux Mastery Challenge – Solution Architect Mode**  

Welcome, Engineer! 🚀 Today, we embark on a real-world **Linux troubleshooting and automation mission.** Every command you execute will **build towards a final system setup.** Your goal is to **prove your Linux mastery step by step**—no shortcuts!  

> **Scenario:** You're working on a **high-security production server**. You need to set up users, manage permissions, manipulate files, and automate some tasks. Follow the architect's challenges below.  

---

### **🛠️ Level 1: Know Your System**  

1️⃣ **Before you touch anything, identify yourself!** What command shows your current username?  
2️⃣ **Confirm who else is lurking in the system.** List all logged-in users and their activity.  
3️⃣ **Prove your authority.** Are you the root user? Validate your privilege level.  
4️⃣ **Your location matters.** Print your current working directory without using `pwd`.  
5️⃣ **Navigate to your home directory with a single command.** No absolute paths allowed!  

---

### **📂 Level 2: File Operations & Organization**  

6️⃣ **Your boss asks for a new structure.** Create a `Projects` folder inside `/tmp`, then inside it, create `Backend`, `Frontend`, and `Database` folders—without using `mkdir` three times!  
7️⃣ **Inside `Backend`, generate five empty files in one shot:** `app.py`, `config.json`, `routes.py`, `db.sql`, `logfile.log`.  
8️⃣ **Oops! You accidentally created `logfile.log`.** Move it to `/var/logs/` instead of deleting it.  
9️⃣ **Security alert!** Change the permissions on `db.sql` so only the owner can read and write.  
🔟 **Too many developers!** Assign ownership of `routes.py` to a new user `devuser1` without switching accounts.  

---

### **🔍 Level 3: System Insights & File Manipulation**  

1️⃣1️⃣ **Check who has access.** Display the last 10 lines of `/etc/passwd` but filter out system accounts (users with IDs below 1000).  
1️⃣2️⃣ **Find out how many users exist.** Count the number of lines in `/etc/passwd` without opening the file.  
1️⃣3️⃣ **Your team loves logs!** Save today’s date into a file called `today.log`, but ensure it appends every time the command runs.  
1️⃣4️⃣ **Find suspicious activity.** Search for failed login attempts in `/var/log/auth.log` without opening the file.  
1️⃣5️⃣ **Someone modified the system groups!** Display the last 5 modified lines in `/etc/group`.  

---

### **🖥️ Level 4: User & Group Management**  

1️⃣6️⃣ **Your team expands!** Create two users, `developer1` and `developer2`, in a single command.  
1️⃣7️⃣ **Security protocol: Enforce passwords.** Set a temporary password for `developer1` that expires in 5 days.  
1️⃣8️⃣ **Restrict developer2.** Prevent them from logging in via SSH without deleting their account.  
1️⃣9️⃣ **Group policy update!** Create a group called `engineers` and add both `developer1` and `developer2` to it.  
2️⃣0️⃣ **Cleanup duty.** Remove `developer1` and `developer2`, along with their home directories.  

---

### **🚀 Bonus Level: Automation & Archiving**  

2️⃣1️⃣ **Your server is running out of space!** Compress everything inside `/tmp/Projects/` into a `.tar.gz` file but exclude `.log` files.  
2️⃣2️⃣ **Ensure you can extract it back later.** Extract the archive into `/opt/backup/` and verify its contents.  
2️⃣3️⃣ **Prevent accidental deletion.** Make `Projects` undeletable for non-root users.  
2️⃣4️⃣ **Write an automation script!** Create a script called `daily_backup.sh` that logs system memory usage to `/var/logs/mem.log` every day.  
2️⃣5️⃣ **Set it to run automatically.** Schedule `daily_backup.sh` to execute at midnight daily.  

---

🔥 **Final Boss Challenge:**  
🧩 **Something broke!** The `/tmp/Projects/` folder is **missing permissions**, and users can’t access it. **Fix it without changing ownership manually.**  

> **Your ultimate goal:** Execute all commands successfully while understanding their impact. Can you prove yourself as a **Linux Solution Architect?** 🏆
