Samajh gaya bhai — tu chaahta hai **ek hi Markdown block** jisme **poora Nmap process** likha ho, properly formatted, ekdam copy-paste-ready.

Yeh le, **saare steps ek hi Markdown block mein**:

---

````markdown
# 🛰️ Nmap Reconnaissance Report

**Nmap** (Network Mapper) helps identify **open ports**, **running services**, **OS details**, and more. It is mainly used for **reconnaissance** in ethical hacking and penetration testing.

---

## 🔧 Steps I Followed

### ✅ Step 1: Check if Nmap is Installed

To check if Nmap is installed on your system:

```bash
nmap --version
````

If it shows a version number, Nmap is installed. Otherwise, install it with:

```bash
sudo apt install nmap
```

---

### ✅ Step 2: Identify the IP Address

I identified the IP address of my system (or target) to scan.
In my case, the IP was:

```
192.168.18.240
```

You can find your IP using:

```bash
ip a
```

---

### ✅ Step 3: Perform the Nmap Scan

I performed an advanced scan using this command:

```bash
sudo nmap -sS -p- -A -O -oX nmap_scan.xml 192.168.18.240
```

#### 🔍 Breakdown of the Flags:

* `-sS` → **TCP SYN Scan** (stealthy & fast).
* `-p-` → Scan **all 65,535 ports** (not just top 1000).
* `-A`  → **Aggressive scan** (includes version detection, OS detection, script scan, and traceroute).
* `-O`  → Tries to detect the **Operating System**.
* `-oX` → Saves the result in **XML format**.

---

### ✅ Step 4: Convert XML to HTML

To make the scan result viewable in a web browser, I converted it using `xsltproc`:

```bash
xsltproc nmap_scan.xml -o nmap_scan.html
```

This creates an HTML file `nmap_scan.html`, which you can open in any browser:

```bash
xdg-open nmap_scan.html
```

---

