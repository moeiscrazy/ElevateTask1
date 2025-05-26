# ElevateTask1

For this task I used the Nmap and Wireshark tools. 

To find the local IP range I opened up cmd as admin and typed in ipconfig /all. This gave me the IPv4 address. I then entered the arp -a command to find the range of addresses on my network. Once I had that I went ahead with using Nmap to scan this ip address range.

During the scan, my AV detected the system being scanned and took protective measures against it. In the scan results I saw 4 open ports for ip address 192.168.1.1

The ports were 53 (default port for DNS), 80 (default network port for web servers using HTTP), 443 (standard port for HTTPS), 5555(used by the Android Debug Bridge).

Port 53, used primarily for DNS (Domain Name System) services, can be exploited in several ways. If a DNS server is exposed to the internet without proper configuration, it may become vulnerable to DNS amplification attacks, where an attacker uses it to flood a target with traffic in a distributed denial-of-service (DDoS) scenario. It can also be used for data exfiltration via DNS tunneling, where attackers hide stolen data within DNS queries and responses. Insecure DNS configurations can expose the server to cache poisoning or spoofing attacks, potentially redirecting users to malicious sites.

Port 80, used for unencrypted HTTP traffic, poses a significant security risk because the data transmitted is not encrypted. This can lead to man-in-the-middle attacks where sensitive information such as login credentials, cookies, or session tokens are intercepted. Web servers running on port 80 may be subject to various vulnerabilities depending on the software used and its configuration. Attackers often scan for outdated web applications to exploit known vulnerabilities such as SQL injection, remote code execution, or cross-site scripting (XSS). Leaving port 80 open without redirecting to HTTPS also weakens the overall security posture of a site.

Port 443, which handles HTTPS traffic, is generally more secure due to its use of SSL/TLS encryption, but it is not immune to risk. Vulnerabilities in SSL/TLS implementations, such as outdated protocols (e.g., SSLv3 or early versions of TLS), weak cipher suites, or improper certificate configurations, can be exploited. Additionally, if the web server software or the web application itself has vulnerabilities, attackers can still gain access through exploits or logic flaws even if the transmission is encrypted. Misconfigurations such as improper access controls or exposed admin panels over HTTPS can further compound the risks.

Port 5555 is not associated with a standard protocol but is commonly used by Android Debug Bridge (ADB) when it is enabled over a network. If ADB is exposed on port 5555, especially without authentication, it becomes a serious security risk. Attackers can gain shell access to the device, allowing them to install malicious applications, access sensitive data, or fully take over the device. Even on non-Android systems, if any service listens on this port and is improperly secured, it can be exploited similarly. This port is often scanned by automated tools looking for vulnerable IoT or Android devices, making it a high-risk vector if exposed.
