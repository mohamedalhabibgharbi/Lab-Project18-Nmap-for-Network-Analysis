# 🔍 Nmap Scanning Lab Summary

## 🎯 Objective

In this lab, I learned how to use **Nmap** to:

- 🖥️ Discover live hosts on a network  
- 🔓 Identify open TCP and UDP ports  
- 🧠 Determine which services are running and their versions  
- 🛠️ Use different scanning techniques and timing options  
- 💾 Format and save scan results  

---

## 🌐 Host Discovery

To find out which devices were online, I used:

- `nmap -sn 10.10.52.0/24`: This scanned my local network <br><br> 
  ![Screenshot1](https://i.imgur.com/uyAnKtf.png)
  <br><br><br>

- `nmap -sn 10.10.53.0/24`: This scanned a remote network  <br><br>
  ![Screenshot2](https://i.imgur.com/25GwL4Q.png)

From these scans, I was able to identify which hosts were active and even view their **MAC addresses** and **vendors** when scanning locally.

---

## 🚪 Port Scanning

To find open services, I used several scan types:

- `nmap -sT`: A TCP connect scan, which completes the three-way handshake  <br><br>
  ![Screenshot3](https://i.imgur.com/IC3ZTZm.png)
  <br><br><br>

- `nmap -sS`: A SYN scan, which sends SYN packets but does not complete the handshake (stealthier) <br><br> 
  ![Screenshot4](https://i.imgur.com/9WVh0CO.png)
  <br><br><br>

- `nmap -sU`: A UDP scan, to detect services like DNS or SNMP  <br><br>
  ![Screenshot5](https://i.imgur.com/FegJiof.png)
  <br><br><br>

I also learned how to limit the scan to specific ports using:

- `-F`: Fast scans (100 most common ports)  
- `-p`: Define custom port ranges <br>  
  ![Screenshot6](https://i.imgur.com/88SSZMf.png)

---

## 🔎 Service and OS Detection

To gather more detailed info, I used:

- `nmap -sV`: Enabled service and version detection  
- `nmap -O`: Tried to guess the target operating system  
- `nmap -A`: Combined both OS and service detection, along with traceroute  

These options helped me identify, for example, that the target web server was running **lighttpd 1.4.74** on **Ubuntu Linux**. <br><br>
![Screenshot7](https://i.imgur.com/iufzllU.png)

---

## ⏱️ Timing and Performance Tuning

I tested different scan speeds using:

- `-T0` to `-T5`: Ranging from paranoid (slowest) to insane (fastest)  
  ![Screenshot8](https://i.imgur.com/ZEqjA6P.png)  
  ![Screenshot9](https://i.imgur.com/dh1fwpG.png)

- `--min-parallelism`, `--max-parallelism`: Controlled how many probes ran at once  
- `--min-rate`, `--max-rate`: Adjusted scan speed in packets per second  
- `--host-timeout`: Limited how long to spend scanning a single host  
  ![Screenshot10](https://i.imgur.com/6d3ZPQa.png)

This helped me balance **stealth**, **speed**, and **thoroughness**.

---

## 🗣️ Verbose and Debug Modes

To get more insights while scanning:

- `-v`, `-vv`: Verbose output  
  ![Screenshot11](https://i.imgur.com/5ekJiuq.png)

- `-d`, `-d9`: Debugging output with more technical detail  

These modes helped me **track scan progress** and **understand Nmap’s behavior in real time**.

---

## 💽 Saving Output

To save my results, I used:

- `-oN`: Saved normal (human-readable) output  
- `-oG`: Grep-friendly format  
- `-oX`: XML format  
- `-oA`: Saved all three formats with the same basename  

![Screenshot12](https://i.imgur.com/Wwvb6oJ.png)  
![Screenshot13](https://i.imgur.com/PcCYBsz.png)

This allowed me to keep a **record of my scans** for later reference and analysis.

---

## 🧾 Final Notes

This lab has really helped me understand both the **basic** and **advanced** features of Nmap.

---

*📁 [Back to Portfolio](../README.md)*  
