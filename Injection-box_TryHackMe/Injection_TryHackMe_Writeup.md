# Injection room [OS Injection basics] writeup (TryHackMe.com)
This is a simple picture only writeup of the Injection room on TryHackMe.com.

## (semi) Blind OS Command injection ping
- Use this command to ping yourself from the webserver/webapp 10 times.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/1.png)

- The page trows an error, you do not know if the injection worked. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/2.png)

- With wireshark we can see no incoming ICMP/ping packets, we can conclude that the OS Commmand injection did not work. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/3.png)

## text
- Text. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/4.png)

## text
- Text. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/5.png)

## text
- Text. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/6.png)

## text
- Text. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/7.png)

## text
- Text. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/8.png)

## text
- Text. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/9.png)

## Blind OS Command Injection
- We use the " root; " statement to generate a " true " condition in the webapp, so it will execute our command. It checks if the user root exists.
- We use netcat to push the output to our own machine, we have to do this since the injection is a blind one.
- ls -la generates the output (the files in the current directory)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/11.png)

- We can do the same with other readable files. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/10.png)

## OS Command Injection
- Linux Distrobution Enumeration: Since it is not a blind injection we can see the output on our screen/webapp/webpage. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/13.png)

- Linux User Shell Environment Enumeration 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/12.png)

## OS Command Injection - Find the flag!
- Connect with a reverse bash shell (netcat/nc -e was not working) and use the find query to find the flag file.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/14.png)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/15.png)
