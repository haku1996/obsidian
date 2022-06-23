`nmap -T4 10.10.10.3 -sC -sV ` 默認腳本+版本
21/tcp  open  ftp         vsftpd 2.3.4
22/tcp  open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp open  netbios-ssn Samba smbd 3.0.20-Debian (workgroup: WORKGROUP)

ftp allow username:anonymous password:anonymous login
vsftpd 2.3.4 exploit not work




## smbmap