# ElevateTask1

For this task I used the Nmap and Wireshark tools. 

To find the local IP range I opened up cmd as admin and typed in ipconfig /all. This gave me the IPv4 address. I then entered the arp -a command to find the range of addresses on my network. Once I had that I went ahead with using Nmap to scan this ip address range.

During the scan, my AV protected the system from one of the scans. In the scan results I saw 4 open ports for ip address 192.168.1.1

The ports were 53 (default port for DNS), 80 (default network port for web servers using HTTP), 443 (standard port for HTTPS), 5555(used by the Android Debug Bridge).

