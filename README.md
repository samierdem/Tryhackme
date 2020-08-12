# Source by Tryhackme

<a href="https://tryhackme.com/room/source" rel="nofollow">Odaya Buradan Ulaşabilirsiniz.</a> 

İlk olarak VPN açıp makinayı çalıştırıyourm. 

Bana verdiği IP adresi şu şekilde = 10.10.90.55 (sizde bu farklı olacaktır.)

Şimdi NMAP taraması yapıyorum 

<pre><code>namp -sV 10.10.90.55 </code></pre>


tarama sonucu şu şekilde;

<pre><code>
nmap -sV 10.10.90.55
Starting Nmap 7.80 ( https://nmap.org ) at 2020-08-12 08:21 EDT
Nmap scan report for 10.10.90.55
Host is up (0.090s latency).
Not shown: 998 closed ports
PORT      STATE SERVICE VERSION
22/tcp    open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
10000/tcp open  http    MiniServ 1.890 (Webmin httpd)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 40.58 seconds
</code></pre>
