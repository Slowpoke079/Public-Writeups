
# Tomghost room, TryHackMe.com [Ghostcat CVE-2020-1938]
This is a writeup of the Tomghost room on TryHackMe.com. This room is made to demonstrate the "Ghostcat exploit" and "CVE-2020-1938 bug". The writeup can feel a bit bloated, this is however the result of showing every step I took.

## Ghostcat? - Here is a quick update:
Ghostcat is a serious vulnerability in Tomcat discovered by security researcher of Chaitin Tech. Due to a flaw in the Tomcat AJP protocol, an attacker can read or include any files in the webapp directories of Tomcat. For example, An attacker can read the webapp configuration files or source code. In addition, if the target web application has a file upload function, the attacker may execute malicious code on the target host by exploiting file inclusion through Ghostcat vulnerability. https://www.chaitin.cn/en/ghostcat


# Tomghost Writeup:
## H1 Scanning
- Use Masscan to quickly scan for open tcp ports. (Masscan is heavier and less accurate then nmap, but the speed is nice for CTF's and large scale scanning.)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/1.png)

- Use Masscan to quickly scan for open udp ports.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/2.png)

- Use Nmap to scan the found open tcp ports for service and version discovery.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/3.png)


## H2 Searching
- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/4.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/5.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/6.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/7.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/8.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/9.png)


## H3 Ghostcat Exploitation

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/10.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/11.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/12.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/13.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/14.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/15.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/16.png)


## H4 Finding user.txt flag

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/4%20finding%20user.txt%20flag/17.png)


## H5 Horizontal privilege escalation

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/18.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/19.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/20.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/21.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/22.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/23.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/23.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/24.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/25.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/26.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/27.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/28.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/29.png)


## H6 Vertical privilege escalation
- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/6%20vertical%20privilege%20escalation/30.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/6%20vertical%20privilege%20escalation/31.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/6%20vertical%20privilege%20escalation/32.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/6%20vertical%20privilege%20escalation/33.png)


## H7 Finding root.txt flag
- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/7%20finding%20root.txt%20flag/34.png)


## H8 Mitigation
- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/8%20mitigation/1.PNG)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/8%20mitigation/2.PNG)


## H9 Other
- A google search typo led to the finding of AJP Shooter, another Ghostcat exploit (tool).
- In the CNVD (Chinese National Vulnerability Database) the ghostcat exploit bug (CVE-2020-1938) is known as (CNVD-2020-10478).

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/9%20other/35%20extra%201.png)


- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/9%20other/36%20extra%202.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/9%20other/38%20extra%203.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/9%20other/39%20extra%204.png)


## H10 Sources
- TryHackMe.com Tomghost room: https://tryhackme.com/room/tomghost
- Chaitin Ghostcat exploit Writeup page: https://www.chaitin.cn/en/ghostcat
- Wikipedia page for CNVDB: https://en.wikipedia.org/wiki/Chinese_National_Vulnerability_Database
- Chinese National Vulnerabillity Database: https://www.cnvd.org.cn/
- AJP Shooter (Ghostcat exploitation tool): https://github.com/00theway/Ghostcat-CNVD-2020-10487
- Ghostcat exploit code Exploit-DB: https://www.exploit-db.com/exploits/48143
- GTFOBins zip privilege escalation: https://gtfobins.github.io/gtfobins/zip/
- Google (lol): https://www.google.com/

