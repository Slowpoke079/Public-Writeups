# Injection room [OS Injection basics] writeup (TryHackMe.com)
This is a simple picture only writeup of the Injection room on TryHackMe.com.

## (semi) Blind OS Command injection ping
- Use this command to ping yourself from the webserver/webapp 10 times.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/1.png)

- The page trows an error, you do not know if the injection worked. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/2.png)

- With wireshark we can see no incoming ICMP/ping packets, we can conclude that the OS Commmand injection did not work. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/3.png)

- Ping injection did not work because there was no " true " condition. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/6.png)

- Ping injection did not work because there was no " true " condition. We can create a true condition by inputting a findable product/object in the search bar/command. In this case the username of an existing user combined with " ; " will do.
- root exists, so root; = true (If you could return/find a product with the search term carrot. You could try and use carrot; to try and create a true statement)
- "ping -c 10 10.9.118.170" = false, and thus ignored
- "root; ping -c 10 10.9.118.170" = true, and thus executed

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/7.png)

## OS Command Injection without "true" statement
- In a lot of webapps it's also possible to do a OS Command injection without any true statements. This can work for ping also.
- Linux Distrobution Enumeration: Since it is not a blind injection we can see the output on our screen/webapp/webpage. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/13.png)

- Linux User Shell Environment Enumeration 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/12.png)

## Blind OS Command Injection
- We will have to receive packets to see if the Blind OS injection works. So lets open up a port in the firewall "the easy way" with gufw (gufw is the graphical frontend of ufw, which is the cli frontend of the iptables firewall.)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/4.png)

- Lets start a netcat listener on the openend port

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/5.png)

- We use the " root; " statement to generate a " true " condition in the webapp, so it will execute our command. It checks if the user root exists.
- We use netcat to push the output to our own machine, we have to do this since the injection is a blind one.
- ls -la generates the output (the files in the current directory)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/11.png)

- We can do the same with other readable files. 

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/8.png)

- And with other users.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/10.png)

## OS Command Injection - Find the flag!
- Connect with a reverse bash shell (netcat/nc -e was not working) and use the find query to find the flag file.

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/14.png)

![github-small](https://github.com/Slowpoke079/Public-Writeups/blob/main/Injection-box_TryHackMe/Pictures/15.png)
