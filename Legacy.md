# HTB - Legacy
$ nmap -sV -sC -A -T4 -Pn -oN filename 10.10.10.3

135/tcp open  msrpc           Microsoft Windows RPC
139/tcp open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp open  microsoft-ds  Windows XP microsoft-ds

$ smbmap -H IP
$ smbclient -N -L IP

nmap Example:
[samba-vuln-cve-2012-1182 NSE script — Nmap Scripting Engine documentation](https://nmap.org/nsedoc/scripts/samba-vuln-cve-2012-1182.html)

$ nmap --script smb-vuln* -p139 10.10.10.4

smb-vuln-ms08-067

