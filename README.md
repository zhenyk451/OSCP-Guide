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
