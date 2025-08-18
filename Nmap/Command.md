---
<p align="center">

# 🚀 **How I Mastered Nmap: Essential Commands, Practical Examples, and Insights**

_A hands-on journey through network scanning and security auditing with Nmap_

</p>
---

<style>
  h1 {
    color: #2c3e50;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  p {
    color: #34495e;
    font-style: italic;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
</style>


Nmap (Network Mapper) is a powerful open-source tool used for network discovery and security auditing. Below are 18 essential commands with example outputs and explanations to help you master Nmap basics.

---

## 1. Scan a Single Host

```bash
nmap scanme.nmap.org
```

**Example Output:**
```
Starting Nmap 7.94 ( https://nmap.org )
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.026s latency).
Not shown: 995 closed ports
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
```

**Explanation:**
Scans common ports on the target host, showing which ports are open (SSH and HTTP) and confirming host availability.

---

## 2. Scan Multiple Hosts

```bash
nmap 192.168.1.1 192.168.1.2
```

**Example Output:**
```
Nmap scan report for 192.168.1.1
Host is up.
PORT    STATE SERVICE
22/tcp  open  ssh

Nmap scan report for 192.168.1.2
Host is up.
PORT    STATE SERVICE
80/tcp  open  http
```

**Explanation:**
Scans multiple specified hosts in one command, reporting open ports for each.

---

## 3. Scan a Range of IPs

```bash
nmap 192.168.1.1-10
```

**Example Output:**
```
Nmap scan report for 192.168.1.1
Host is up.
...
Nmap scan report for 192.168.1.10
Host is up.
```

**Explanation:**
Scans all devices in the specified IP range and lists those that are online.

---

## 4. Scan an Entire Subnet

```bash
nmap 192.168.1.0/24
```

**Example Output:**
```
Nmap scan report for 192.168.1.25
Host is up.
PORT   STATE SERVICE
53/tcp open  domain
...
```

**Explanation:**
Performs a scan on all 256 addresses of the subnet, discovering active hosts and open services.

---

## 5. Ping Scan (Discover Live Hosts)

```bash
nmap -sn 192.168.1.0/24
```

**Example Output:**
```
Host is up (0.026s latency).
```

**Explanation:**
Used to quickly identify which hosts in a subnet are online, without scanning ports.

---

## 6. Scan Specific Ports

```bash
nmap -p 80,443 scanme.nmap.org
```

**Example Output:**
```
PORT    STATE SERVICE
80/tcp  open  http
443/tcp closed https
```

**Explanation:**
Scans only the specified ports (HTTP and HTTPS in this case), useful for focused auditing.

---

## 7. Scan All TCP Ports (1-65535)

```bash
nmap -p 1-65535 scanme.nmap.org
```

**Example Output:**
```
PORT      STATE   SERVICE
22/tcp    open    ssh
80/tcp    open    http
...
```

**Explanation:**
Thoroughly scans every possible TCP port, uncovering any open services.

---

## 8. Aggressive Scan with OS and Version Detection

```bash
nmap -A scanme.nmap.org
```

**Example Output:**
```
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.6p1 Ubuntu
80/tcp   open  http    Apache httpd 2.4.18

Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

**Explanation:**
Performs detailed scanning including OS detection, service versioning, and traceroute.

---

## 9. Verbose Output

```bash
nmap -v scanme.nmap.org
```

**Example Output:**
```
Initiating SYN Stealth Scan...
Scanned at 2025-08-17 22:30 PDT...
PORT   STATE SERVICE
22/tcp open  ssh
```

**Explanation:**
Enables detailed scan progress information for deeper insight during scanning.

---

## 10. Disable DNS Resolution to Speed Up Scans

```bash
nmap -n scanme.nmap.org
```

**Example Output:**
```
Scanning IP address directly, no hostname mapping.
```

**Explanation:**
Skips reverse DNS lookups, improving scan speed on large networks.

---

## 11. Operating System Detection

```bash
nmap -O scanme.nmap.org
```

**Example Output:**
```
OS details: Linux 4.4 - 4.15 (96% accuracy)
```

**Explanation:**
Attempts to identify the target machine's OS using TCP/IP stack fingerprinting.

---

## 12. Save Scan Output to a File

```bash
nmap -oN scan.txt scanme.nmap.org
```

**Example Output:**
- Scan results saved to `scan.txt` file matching what is shown in the terminal.

**Explanation:**
Useful for preserving scan data for later review or reporting.

---

## 13. UDP Port Scan

```bash
nmap -sU scanme.nmap.org
```

**Example Output:**
```
PORT      STATE  SERVICE
53/udp    open   domain
```

**Explanation:**
Scans UDP ports, which are often slower and harder to detect than TCP.

---

## 14. TCP SYN Scan (Stealth Scan)

```bash
nmap -sS scanme.nmap.org
```

**Example Output:**
```
PORT    STATE SERVICE
22/tcp  open  ssh
```

**Explanation:**
Sends SYN packets to check for open TCP ports stealthily, without completing the 3-way handshake.

---

## 15. Perform Traceroute Alongside Scan

```bash
nmap --traceroute scanme.nmap.org
```

**Example Output:**
```
Traceroute (using port 80/tcp):
1  192.168.1.1  0.246ms
2  10.0.0.1     12.3ms
3  ...
```

**Explanation:**
Displays the network path packets take to reach the target host.

---

## 16. Scan Targets from a File

```bash
nmap -iL targets.txt
```

**Example Output:**
- Reads multiple targets from `targets.txt` and scans each.

**Explanation:**
Efficient for bulk scanning lists of IPs or hostnames.

---

## 17. Exclude Specific Hosts from Scan

```bash
nmap 192.168.1.1-10 --exclude 192.168.1.5
```

**Example Output:**
- Skips scanning `192.168.1.5` while scanning others in the range.

**Explanation:**
Allows you to avoid scanning certain hosts for operational or policy reasons.

---

## 18. Show Only Open (or Possibly Open) Ports in Output

```bash
nmap --open scanme.nmap.org
```

**Example Output:**
```
PORT    STATE SERVICE
22/tcp  open  ssh
80/tcp  open  http
```

**Explanation:**
Filters the scan results to show only the ports currently accessible.
