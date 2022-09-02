# OSCP-Guide

So yea I didn't pass it... I would definitely recommend 3 months subscription, I got 2 and solved 49 boxes, and did not manage to touch Buffer Overflow. I knew that I could attempt the Buffer Overflow exercises as long as I tranferred the necessary files over from the Offsec provided Windows VM to my own. However, I miscalculated the amount of time I had left due to timezone differences, and thought I had an additional day to make the transfer, I really should not have procrastinated... 

So yea my number 1 tip, is that you transfer the Buffer Overflow materials before your subscription expires. You can always analyze the .exe files with Immunity Debugger after the timer expires, so long as you have access to those files.

My prior knowledge of ethical hacking was just port enumeration and metasploit. I would suggest you try out vulnhub VM's like Kioptrix and attempt to solve them with manual exploits, by that I meant not use automated tools, i.e. Nessus for Port Enumeration or Metasploit for all the things Metasploit does.

With that being said, know the basics of metasploit as you are allowed to use it for one out of the five boxes in your exam. Incorporate it when you are practicing, but do not rely on it for all your boxes.

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
