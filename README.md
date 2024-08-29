Nmap Practical Exercises
This repository contains practical exercises I completed using Nmap, a powerful network scanning tool. The exercises demonstrate various Nmap features and their applications in network security.

Table of Contents
  * Introduction
  * Exercises
  * Scan Network Range
  * Scan IP List
  * Scan Single IP
  * Host and Port Scanning
  * Trace the Packets
  * Version Scan
  * Saving Scan Results
  * Screenshots
  * Conclusion

Introduction
In this practical, I explored the functionalities of Nmap by conducting various network scans. These exercises helped me understand how to discover live hosts, identify open ports, trace packet routes, and more.

Exercises
1. Scan Network Range: Scanned an entire network range to identify all active devices on the network.

sudo nmap 192.168.1.0/24 -sn -oA tnet | grep for | cut -d" " -f5

2. Discovering Open UDP Ports:
Scanned the network to discover open UDP ports, which can be used for various services like DNS or DHCP. This type of scan is essential for identifying less obvious entry points that could be exploited.

sudo nmap 192.168.1.126 -F -sU

3. Scan Single IP
Performed a detailed scan on a single IP address:

sudo nmap 192.168.1.21 -sn - oA host
sudo nmap 192.168.1.21 -sn - oA host -PE --packet-trace

4. Host and Port Scanning
Identified accessible services on the network:

sudo nmap 192.168.1.37 --top-ports=10

5. Trace the Packets
Traced the route packets take across the network:

sudo nmap 192.168.1.25 -p21 --packet-trace -Pn -n --disable-arp-ping

6. Version Scan
Detected software and versions running on open ports:

sudo nmap 192.168.1.126 -Pn -n --disable-arp-ping --packet-trace -p445 --reason -sV

7. Saving Scan Results
Saved scan results in various formats:

sudo nmap 192.168.1.37 -p- -oA scanfile --stats-every=10s
