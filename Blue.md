$ nmap -sC -Pn -T4 -O -sV -sS -A 10.10.10.40
$ nmap -oA

$ smbmap -H 10.10.10.40 -u "隨便"
$ smbclient //10.10.10.40/??? 

$ nmap --script smb-vuln* -p445 10.10.10.40
-> smb-vuln-ms17-010

[Exploit Database SearchSploit Manual (exploit-db.com)](https://www.exploit-db.com/searchsploit)
$ searchsploit -t ms17-010 -v -o -m
title, verbose, overflow, mirror(copied to current dir)

$ find / -name  42031.py
$ cp 

exploit Code stored @ /usr/share/exploitdb/exploits