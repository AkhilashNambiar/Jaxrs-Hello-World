

### **Step 1: Identify the Disk**
1. List all disks and partitions:
   ```bash
   lsblk
   ```
   - Identify the disk you want to partition (e.g., `/dev/sdc`).

2. View detailed disk information:
   ```bash
   fdisk -l /dev/sdc
   ```

---

### **Step 2: Create Partitions**
1. Start partitioning the disk using `fdisk`:
   ```bash
   fdisk /dev/sdc
   ```

2. Inside `fdisk`:
   - Press `n` to create a new partition.
   - Choose `p` for a primary partition.
   - Specify the partition number (e.g., `1`).
   - Set the first and last sector (or press `Enter` to use default values).
   - Repeat the process to create additional partitions if needed.

3. Save changes and exit:
   - Press `w` to write changes to the disk.

4. Verify the partitions:
   ```bash
   lsblk /dev/sdc
   ```

---

### **Step 3: Set Up LVM (Logical Volume Manager)**
1. **Create a Physical Volume (PV)**:
   - Initialize the partition as a physical volume:
     ```bash
     pvcreate /dev/sdc1
     ```
   - Verify the physical volume:
     ```bash
     pvs
     ```

2. **Create a Volume Group (VG)**:
   - Create a volume group using the physical volume:
     ```bash
     vgcreate myvg /dev/sdc1
     ```
   - Verify the volume group:
     ```bash
     vgs
     ```

3. **Create a Logical Volume (LV)**:
   - Create a logical volume of **10 MB** within the volume group:
     ```bash
     lvcreate -L 10M -n mylv myvg
     ```
     - `-L 10M`: Size of the logical volume (10 MB).
     - `-n mylv`: Name of the logical volume.
     - `myvg`: Name of the volume group.
   - Verify the logical volume:
     ```bash
     lvs
     ```

---

### **Step 4: Format the Logical Volume**
1. Format the logical volume with a filesystem (e.g., `ext4`):
   ```bash
   mkfs.ext4 /dev/myvg/mylv
   ```

2. Verify the filesystem:
   ```bash
   blkid /dev/myvg/mylv
   ```

---

### **Step 5: Mount the Logical Volume**
1. Create a mount point:
   ```bash
   mkdir /mnt/mylv
   ```

2. Mount the logical volume:
   ```bash
   mount /dev/myvg/mylv /mnt/mylv
   ```

3. Verify the mount:
   ```bash
   df -h /mnt/mylv
   ```

---

### **Step 6: Make the Mount Persistent**
1. Edit the `/etc/fstab` file:
   ```bash
   vi /etc/fstab
   ```

2. Add the following line:
   ```
   /dev/myvg/mylv /mnt/mylv ext4 defaults 0 0
   ```

3. Save and exit the file.

4. Test the `fstab` entry:
   ```bash
   mount -a
   ```

---

### **Step 7: Verify the Setup**
1. Check the logical volume:
   ```bash
   lvdisplay /dev/myvg/mylv
   ```

2. Check the mounted filesystem:
   ```bash
   df -h
   ```

---

### **Summary of Commands**
| Step | Command | Purpose |
|------|---------|---------|
| 1    | `lsblk` | List disks and partitions |
| 2    | `fdisk /dev/sdc` | Partition the disk |
| 3    | `pvcreate /dev/sdc1` | Create a physical volume |
| 4    | `vgcreate myvg /dev/sdc1` | Create a volume group |
| 5    | `lvcreate -L 10M -n mylv myvg` | Create a logical volume |
| 6    | `mkfs.ext4 /dev/myvg/mylv` | Format the logical volume |
| 7    | `mount /dev/myvg/mylv /mnt/mylv` | Mount the logical volume |
| 8    | Edit `/etc/fstab` | Make the mount persistent |

