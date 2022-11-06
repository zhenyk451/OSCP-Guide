# OSCP-Guide

NMAP

	sudo nmap -sT -sC -sV -Pn -o 120 10.11.1.120

	sudo nmap -sU -sC -sV -Pn -o 120udp 10.11.1.120

	sudo nmap -sS -sC -sV -Pn -o 120sS 10.11.1.120

	sudo nmap -p- -T4 -v -Pn -o 120full 10.11.1.120

Web Enum
Directory brute forcer

	- wfuzz -w /usr/share/wordlists/dirb/big.txt --hc 404 -c -t 100 http://<ip>/FUZZ
	- wfuzz -w /usr/share/seclists/Discovery/Web-Content/common.txt --hc 404 -c -t 100 http://<ip>/FUZZ
	/usr/share/seclists/Discovery/Web-Content/common.txt
	- wfuzz -w /usr/share/dirb/wordlists/vulns/sharepoint.txt --hc 404 -c -t 100 http://<ip>/FUZZ

Replace hc 404 with 400 for https

SMB
SMBClient

	- smbclient -L <host>

	- smbclient \\\\<host>\\<shareName> password

	From <https://www.tldp.org/HOWTO/SMB-HOWTO-8.html> 

	enum4linux -a <host>
	
MSSQL
	http://pentestmonkey.net/cheat-sheet/sql-injection/mssql-sql-injection-cheat-sheet

	https://www.netsparker.com/blog/web-security/sql-injection-cheat-sheet/#UnionInjections

	https://hydrasky.com/network-security/mssql-server-injection-tutorial/

	https://pentestlab.blog/2012/12/24/sql-injection-authentication-bypass-cheat-sheet/

	http://www.securityidiots.com/Web-Pentest/SQL-Injection/MSSQL/MSSQL-Union-Based-Injection.html

	https://www.exploit-db.com/papers/12975
	
Netcat

	- nc -nv 10.10.10.10 <port>
	From <https://scund00r.com/all/oscp/2018/02/25/passing-oscp.html#scripts> 
	
	- telnet 10.10.10.10 <port>
	From <https://scund00r.com/all/oscp/2018/02/25/passing-oscp.html#scripts> 
	
	- nc -u -nv 10.1.1.226 69
	<-u for udp>
	
FTP

	ftp://<ip>
	<in browser>
		
	or
	
	ftp <ip> <port>
	anonymous:anonymous\
	
Wordpress

	wpscan --url http://10.11.1.234/ --passwords rockyou.txt
	https://blog.wpscan.org/wpscan/2019/09/17/wpscan-brute-force.html
