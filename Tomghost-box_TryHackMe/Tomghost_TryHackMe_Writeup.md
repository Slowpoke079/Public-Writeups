
# Tomghost room, TryHackMe.com [Ghostcat CVE-2020-1938]
This is a writeup of the Tomghost room on TryHackMe.com. This room is made to demonstrate the "Ghostcat exploit" and "CVE-2020-1938 bug". The writeup can feel a bit bloated, this is however the result of showing every step I took.

## Ghostcat? - Here is a quick update:
Ghostcat is a serious vulnerability in Tomcat discovered by security researcher of Chaitin Tech. Due to a flaw in the Tomcat AJP protocol, an attacker can read or include any files in the webapp directories of Tomcat. For example, An attacker can read the webapp configuration files or source code. In addition, if the target web application has a file upload function, the attacker may execute malicious code on the target host by exploiting file inclusion through Ghostcat vulnerability. https://www.chaitin.cn/en/ghostcat


# Tomghost Writeup:
## H1 Scanning
- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/1.png)

- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/2.png)

- TEXT

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

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/4%20finding%20user.txt%20flag/17.png)


## H6 Vertical privilege escalation
- TEXT

## H7 Finding root.txt flag
- TEXT

## H8 Mitigation
- TEXT

## H9 Other
- A google search typo led to the finding of AJP Shooter, another Ghostcat exploit (tool).
- In the CNVD (Chinese National Vulnerability Database) the ghostcat exploit bug (CVE-2020-1938) is known as (CNVD-2020-10478).

## H10 Sources
- TryHackMe.com Tomghost room: https://tryhackme.com/room/tomghost
- Chaitin Ghostcat exploit Writeup page: https://www.chaitin.cn/en/ghostcat
- Wikipedia page for CNVDB: https://en.wikipedia.org/wiki/Chinese_National_Vulnerability_Database
- Chinese National Vulnerabillity Database: https://www.cnvd.org.cn/
- AJP Shooter (Ghostcat exploitation tool): https://github.com/00theway/Ghostcat-CNVD-2020-10487
- Ghostcat exploit code Exploit-DB: https://www.exploit-db.com/exploits/48143
- GTFOBins zip privilege escalation: https://gtfobins.github.io/gtfobins/zip/
- Google (lol): https://www.google.com/

