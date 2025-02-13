
### **Step 1: Enable the EPEL Repository**
The EPEL repository contains additional packages, including `htop`. To enable it:

1. Install the EPEL repository:
   ```bash
   sudo yum install epel-release -y
   ```

2. Verify that the EPEL repository is enabled:
   ```bash
   sudo yum repolist
   ```
   Look for `epel` in the list of enabled repositories.

---

### **Step 2: Install `htop`**
Once the EPEL repository is enabled, you can install `htop`:
```bash
sudo yum install htop -y
```

---

### **Alternative Tools to `htop`**
If you cannot enable EPEL or prefer not to, there are alternative tools for process monitoring:

1. **`top`**:
   - A built-in process monitoring tool available on most Linux systems.
   - Usage:
     ```bash
     top
     ```

2. **`atop`**:
   - A more advanced process monitor that logs system activity.
   - Install it using:
     ```bash
     sudo yum install atop -y
     ```

3. **`glances`**:
   - A cross-platform monitoring tool with a web-based interface.
   - Install it using:
     ```bash
     sudo yum install glances -y
     ```

4. **`nmon`**:
   - A performance monitoring tool for Linux.
   - Install it using:
     ```bash
     sudo yum install nmon -y
     ```

---

### **Step 3: Verify Installation**
After installing `htop` or an alternative, verify it works:
```bash
htop
```
or
```bash
top
```

---

### **Why Use `htop`?**
- **Interactive Interface**: Easier to navigate than `top`.
- **Color-Coded Output**: Helps quickly identify resource usage.
- **Mouse Support**: Allows clicking to select processes.
- **Customizable**: Can be configured to show additional details.

---

### **Summary**
1. Enable the EPEL repository:
   ```bash
   sudo yum install epel-release -y
   ```
2. Install `htop`:
   ```bash
   sudo yum install htop -y
   ```
3. If `htop` is unavailable, use alternatives like `top`, `atop`, `glances`, or `nmon`.

