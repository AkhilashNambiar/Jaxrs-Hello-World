
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

The `top` command is a powerful tool for monitoring system processes and resource usage in real-time. Below is a detailed explanation of how to use the `top` command with the specific keybindings you mentioned:

---

### **Starting `top`**
To start `top`, simply type:
```bash
top
```
This will display a dynamic, real-time view of system processes, CPU, memory, and other resource usage.

---

### **Keybindings in `top`**

1. **`t`**: Toggle the display of the task/cpu line.
   - This shows or hides the summary line for CPU usage (user, system, idle, etc.).
   - Press `t` to toggle between showing and hiding this line.

2. **`m`**: Toggle the display of memory (RAM and SWAP) details.
   - This shows or hides the memory and swap usage summary.
   - Press `m` to toggle between showing and hiding this information.

3. **`R`**: Sort processes by PID number.
   - By default, processes are sorted by CPU usage.
   - Press `R` to sort them by PID in ascending or descending order.

4. **`P`**: Sort processes by CPU utilization.
   - This is the default sorting method.
   - Press `P` to sort processes by CPU usage (highest to lowest).

5. **`M`**: Sort processes by RAM (memory) utilization.
   - Press `M` to sort processes by memory usage (highest to lowest).

6. **`e`**: Toggle the display of the full command path.
   - By default, `top` truncates the command name.
   - Press `e` to show the full command path or toggle back to the truncated view.

7. **`r`**: Renice a process.
   - Press `r`, then enter the PID of the process you want to renice.
   - After entering the PID, specify the new nice value (between -20 and 19).
     - A lower nice value increases the process priority.
     - A higher nice value decreases the process priority.

8. **`k`**: Kill a process.
   - Press `k`, then enter the PID of the process you want to kill.
   - After entering the PID, press `Enter` to send the default `SIGTERM` signal.
   - You can also specify a different signal (e.g., `9` for `SIGKILL`).

9. **`W`**: Save the modified configuration permanently.
   - If you customize the display (e.g., sorting, toggling fields), press `W` to save the configuration to the `~/.toprc` file.
   - This ensures your changes are applied the next time you run `top`.

10. **`q`**: Quit the `top` command.
    - Press `q` to exit `top` and return to the terminal.

11. **`h`**: Display help.
    - Press `h` to open the help screen, which lists all available keybindings and their functions.

---

### **Example Workflow**
1. Start `top`:
   ```bash
   top
   ```

2. Sort processes by CPU usage:
   - Press `P`.

3. Sort processes by memory usage:
   - Press `M`.

4. Renice a process:
   - Press `r`, enter the PID, and specify the new nice value.

5. Kill a process:
   - Press `k`, enter the PID, and press `Enter`.

6. Save your configuration:
   - Press `W` to save changes to `~/.toprc`.

7. Quit `top`:
   - Press `q`.

---

### **Additional Tips**
- **Resize the Display**: If your terminal window is resized, press `Shift + F` to adjust the display.
- **Change Update Interval**: Press `d` and enter a new delay (in seconds) to change the refresh rate.
- **Highlight Running Tasks**: Press `z` to toggle color highlighting for running tasks.

---

### **Summary of Keybindings**
| Key | Function |
|-----|----------|
| `t` | Toggle task/cpu line |
| `m` | Toggle memory (RAM/SWAP) details |
| `R` | Sort by PID |
| `P` | Sort by CPU usage |
| `M` | Sort by memory usage |
| `e` | Toggle full command path |
| `r` | Renice a process |
| `k` | Kill a process |
| `W` | Save configuration |
| `q` | Quit `top` |
| `h` | Display help |

