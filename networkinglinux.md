Here’s a **step-by-step guide** with executable commands to teach your students the concepts you’ve outlined. Each topic is broken down into clear steps with practical commands.

---

## **1. Identifying Network Interfaces**
### **Objective**: Learn how to identify network interfaces on a Linux system.
1. List all network interfaces:
   ```bash
   ip link show
   ```
2. Display detailed information about network interfaces:
   ```bash
   ip addr show
   ```
3. Check the status of a specific interface (e.g., `eth0`):
   ```bash
   ip link show eth0
   ```

---

## **2. Describing Network Interface Names**
### **Objective**: Understand how network interfaces are named.
1. List network interface names:
   ```bash
   ls /sys/class/net
   ```
2. Explain the naming conventions:
   - `eth0`: Ethernet interface.
   - `wlan0`: Wireless interface.
   - `lo`: Loopback interface.

---

## **3. Describing NetworkManager Concepts**
### **Objective**: Understand the role of NetworkManager in managing network connections.
1. Check if NetworkManager is running:
   ```bash
   systemctl status NetworkManager
   ```
2. List all connections managed by NetworkManager:
   ```bash
   nmcli con show
   ```
3. View active connections:
   ```bash
   nmcli con show --active
   ```

---

## **4. Viewing Networking Information**
### **Objective**: Learn how to view network configuration and statistics.
1. Display IP addresses and routing information:
   ```bash
   ip addr
   ```
2. View the routing table:
   ```bash
   ip route
   ```
3. Check network statistics:
   ```bash
   netstat -s
   ```

---

## **5. Modifying Network Connection Settings**
### **Objective**: Learn how to modify network settings.
1. Edit a connection (e.g., `eth0`):
   ```bash
   nmcli con edit eth0
   ```
2. Change the IP address of a connection:
   ```bash
   nmcli con mod eth0 ipv4.addresses 192.168.1.100/24
   ```
3. Apply changes:
   ```bash
   nmcli con up eth0
   ```

---

   ```

---

## **7. Check Network Statistics and Open Ports**
### **Objective**: Learn how to monitor network activity and open ports.
1. Display open ports and listening services:
   ```bash
   netstat -tulpn
   ```
2. Check network statistics:
   ```bash
   ss -s
   ```
3. Monitor real-time network traffic:
   ```bash
   nload
   ```

---

## **8. Domain Name System (DNS)**
### **Objective**: Understand DNS and how to configure it.
1. View the DNS resolver configuration:
   ```bash
   cat /etc/resolv.conf
   ```
2. Test DNS resolution:
   ```bash
   nslookup google.com
   ```

   ```

---

## **Lab 8: Networking in Linux**
### **Task 1: IP Configurations**
1. Assign a static IP address to an interface:
   ```bash
   nmcli con mod eth0 ipv4.method manual ipv4.addresses 192.168.1.100/24 ipv4.gateway 192.168.1.1 ipv4.dns 8.8.8.8
   ```
2. Apply the changes:
   ```bash
   nmcli con up eth0
   ```

### **Task 2: Checking Open Ports in Linux**
1. List all open ports:
   ```bash
   netstat -tulpn
   ```
2. Check if a specific port is open (e.g., port 80):
   ```bash
   netstat -tulpn | grep :80
   ```

### **Task 3: Working with Firewall in Linux**
1. Check the firewall status:
   ```bash
   firewall-cmd --state
   ```
2. Allow a service (e.g., HTTP):
   ```bash
   firewall-cmd --permanent --add-service=http
   ```
3. Reload the firewall:
   ```bash
   firewall-cmd --reload
   ```

---
