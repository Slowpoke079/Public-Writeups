
# Tomghost room, TryHackMe.com [Ghostcat CVE-2020-1938]
This is a writeup of the Tomghost room on TryHackMe.com. This room is made to demonstrate the "Ghostcat exploit" and "CVE-2020-1938 bug".

## Ghostcat? - Here is a quick update:
Ghostcat is a serious vulnerability in Tomcat discovered by security researcher of Chaitin Tech. Due to a flaw in the Tomcat AJP protocol, an attacker can read or include any files in the webapp directories of Tomcat. For example, An attacker can read the webapp configuration files or source code. In addition, if the target web application has a file upload function, the attacker may execute malicious code on the target host by exploiting file inclusion through Ghostcat vulnerability. https://www.chaitin.cn/en/ghostcat


# Writeup
## H1 Scanning
- TEXT

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/1.png)

- TEXT
picture

## H2 Searching
- TEXT

## H3 Ghostcat Exploitation
- TEXT

## H4 Finding user.txt flag
- TEXT

## H5 Horizontal privilege escalation
- TEXT

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

