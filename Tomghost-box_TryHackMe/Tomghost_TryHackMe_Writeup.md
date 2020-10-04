# Tomghost room [Ghostcat CVE-2020-1938/CNVD-2020-10487] writeup (TryHackMe.com)
This is a writeup of the Tomghost room on TryHackMe.com. This room is made to demonstrate the "Ghostcat exploit" and "CVE-2020-1938 bug". The writeup can feel a bit bloated, this is however the result of showing every step I took.

## Ghostcat? - Here is a quick update:
Ghostcat is a serious vulnerability in Tomcat discovered by security researcher of Chaitin Tech. Due to a flaw in the Tomcat AJP protocol, an attacker can read or include any files in the webapp directories of Tomcat. For example, An attacker can read the webapp configuration files or source code. In addition, if the target web application has a file upload function, the attacker may execute malicious code on the target host by exploiting file inclusion through Ghostcat vulnerability. https://www.chaitin.cn/en/ghostcat


# Tomghost Writeup:
## H1 Scanning
- Use Masscan to quickly scan for open tcp ports. 
- (Masscan is heavier and less accurate then nmap, but the speed is nice for CTF's and large scale scanning.)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/1.png)

- Use Masscan to quickly scan for open udp ports.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/2.png)

- Use Nmap to scan the found open tcp ports for service and version discovery.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/1%20scanning/3.png)


## H2 Searching
- Since the Tomghost room was created to demonstrate the "Ghostcat exploit" we start our searching by googling "Ghostcat".

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/5.png)

- Chaitin, a chinese security company, has created the Ghostcat exploit and found the "CVE-2020-1938" bug. They also created a writeup website for it.
- (No worries, you can find all found links at the end of this writeup)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/4.png)

- This all sounds pretty straight forward

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/6.png)

- They created their own scanner tool for the Ghostcat bug! I could not install and make use of the tool since everything was in chinese and google translate didn't help much.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/7.png)

- So lets try looking for exploit code starting at exploit-db.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/8.png)

- Found exploit code written in python

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/2%20searching/9.png)


## H3 Ghostcat Exploitation

- Download the raw exploit code with wget.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/10.png)

- Read the code (to see what it does and to see if wget succeeded).

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/11.png)

- It looked like python code so lets rename the file to 48143.py

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/12.png)

- Run the exploit with python.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/13.png)

- Oops, add the needed arguments. Target the AJP port, not the Tomcat Apache port itself!

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/14.png)

- By reading a configuration file we could find hardcoded user credentials.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/15.png)

- We discovered SSH port 22 to be open with masscan, lets try to log in with our credentials.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/3%20ghostcat%20exploit/16.png)


## H4 Finding user.txt flag

- Lets do a "find" to search for the user.txt file. This is our first flag (we need two).

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/4%20finding%20user.txt%20flag/17.png)


## H5 Horizontal privilege escalation

- We cannot use sudo. Here you can see two examples of trying to use sudo, but note that sudo -l does not trigger "a logging warning".

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/18.png)

- Credential.pgp and tryhackme.asc look quite out of place. They are probably setup for this CTF as a privilege escalation.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/19.png)

- Download the files to our kali machine

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/20.png)

- Turn the .asc into a crackable hash with John for John (tool).

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/21.png)

- Search for the most widely used wordlist in CTF's.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/22.png)

- Crack the hash with john.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/23.png)

- Show the cracked password.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/24.png)

- Import the cracked .asc

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/25.png)

- Fill in the password

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/26.png)

- Import the gpg key (in .asc form).

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/27.png)

- Decrypt our credential.pgp private key with our imported .asc key.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/28.png)

- Now back on the hacked tomcat server we can switch our current user to merlin with the previously found credentials.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/5%20horizontal%20privilege%20escalation/29.png)


## H6 Vertical privilege escalation
- Lets do the sudo -l test one more time to see if we can use sudo with merlin (which would make privilege escalation way easier).
- We can use the sudo command without stating a password if we call the zip binary.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/6%20vertical%20privilege%20escalation/30.png)

- Searching for sudo + zip privelege escalation

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/6%20vertical%20privilege%20escalation/31.png)

- GTFOBins got our back!

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/6%20vertical%20privilege%20escalation/32.png)

- Run the "manual privilege escalation exploitation" of the sudo + zip binary.
- We are now root!

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/6%20vertical%20privilege%20escalation/33.png)


## H7 Finding root.txt flag
- Lets search for the root.txt flag file.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/7%20finding%20root.txt%20flag/34.png)


## H8 Mitigation
- If your tomcat apache server is using the AJP connector and contains the same or an older version then the ones specified you should patch your tomcat.
- Update your apache tomcat to the latest version is the best practice mitigation. If this is not possible however you can:
- Set AJP to listen to your local ip address 127.0.0.1 only.
- You can also include a "secret" in your AJP connections to patch this vulnerabillity. This secret should be strong and now set to something easily cracked.
- Or disable the AJP adapter (this can possibly create a performance downgrade).

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/8%20mitigation/1.PNG)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/8%20mitigation/2.PNG)


## H9 Other
- A google search typo led to the finding of AJP Shooter, another Ghostcat exploit (tool).

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/9%20other/35%20extra%201.png)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/9%20other/36%20extra%202.png)

- In the CNVD (Chinese National Vulnerability Database) the ghostcat exploit bug (CVE-2020-1938) is known as (CNVD-2020-10478).

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Tomghost-box_TryHackMe/Pictures/Ghostcat%20Writeup/9%20other/38%20extra%203.png)

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

