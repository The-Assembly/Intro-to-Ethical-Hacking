# Intro to Ethical Hacking and Security

This is a beginner workshop tutorial on network hacking tools such as BeEF, Social Fish and Bettercap.

## Bettercap

**Bettercap** is a powerful, easily extensible and portable framework written in Go which aims to offer to security researchers, red teamers and reverse engineers an easy to use, all-in-one solution with all the features they might possibly need for performing reconnaissance and attacking WiFi networks, Bluetooth Low Energydevices, wireless HID devices and Ethernet networks.

Power ON the Machine

Okay, to start working, we need to first search and click for “VirtualBox” then select the engine and click start at the top. This way we have everything set up to start working with Kali Linux with
Default username: root and pass: toor

1.	Click on the Terminal
2.	Install bettercap 

```apt install bettercap```


3.	Update the repositories 

```apt-get update```

4.	Type “bettercap” and “help” to show all the commands available to use this tool.
5.	To see the clients that are connected to the same network 

```net.probe on```


6.	To show all the devices connected to your network

```net.show```

7.	To begin the process of spoofing an IP Address

```help arp.spoof```

8.	Now we proxy the connection as we want the victim to know we are the gateway but we don’t want the gateway to know we are targeting it so that we can get responses.

	```set arp.spoof.fullduplex true```

9.	To  select the victim’s ip address which we want to target , just fill the “bla” spaces with numbers. 

```set arp.spoof.targets bla.bla.bla.bla```

10.	To start the spoof attack 

```arp.spoof on```

11.	To capture the victim’s data aka “sniffing”
```net.sniff on```

12.	Now we use WireShark  which is a tool that captures the victim’s information and decodes into a file that is easy to read by the user so to Run the program, all you need to do is type “wireshark”
13.	Now to release the attack on the  wanted interface 
```select eth0```

14.	Now is Testing Time!!! So all you need to do is go to any “http” Website and not “https” and then you can enter some data and check the “POST” Packets to see how your data has been sniffed and sent to the hacker.

## BeEF


**BeEF** is a penetration testing tool that focuses on web browsers vulnerabilities to be able to secure web browsers against malicious attacks.

1.	First, we have to update the repositories to make sure that we start fresh 
```apt-get update```

2.	We install the tool
```apt install beef.xss```

3.	We initialize the tool by typing “beef-xss” 
4.	Then you are asked to type a password.Enter any password that you choose. However, make sure you remember this password as you will need it later for a following step.

5.	Look for the “script” tag and copy it.

6.	To perform our attack, you need inject the code line into the website by  pasting it to apache server so you have to navigate the wanted folder by going to “home” and write the following piece

```/var/www/html/index.html```

7.	Paste the script line in the above file and then spot the IP Address at the bottom of the file and fill in you own device ip address. 

8.	Go to the browser and add a zero to the ip address at the top as such “172.0.0.10”. You’ll be directed to a login page so just enter “beef” as username and the password you have set before.


9.	Now, we have to run the Apache Server by typing the following commands

      ``` apt apache2 install```
      
      ```service apache2 start```
          
10.	Then, we have to hook a server file so we go to the browser and paste the ip address of the victim which in this case is our ip address that we got from the -ipconfig- command. You should be redirected then to a page with a msg that says that your hooked.

11.	Next, we should have a connection on some networks under online browsers. So under online browsers, after clicking on the wanted network address, you’ll find a list of commands and ways to play with and execute attacks on the victim such as “Alert Dialogue” option. This will display the directed message on the victim’s device.

12.	There are many other commands that could performed such as Pretty theft and Google Phishing which creates a fake page exactly like google to record your activities.


## Social Phishing

This  is a tool that is used to create a duplicate of a popular site like Facebook,Instagram,Twitter..etc so that the hacker could trick the victim into thinking this is the real page and have them login with their data and  then be able to manipulate the data and perhaps blackmail them with it.


1.	 To begin with , we have to install the tool by cloning its github repository

```git clone https://github.com/pUndeadSec/SocialFish```


2.	 We  navigate to the folder we just cloned by typing “dir” then 

```cd SocialFish/```


3.	 Because this tool is python scripted, we will have to apply the following commands

```apt-get install python3 python3-pippython3-dev -y```

```Python -m pip install -r requirements.txt```

4.	Now, we initialize the service 

```Python3 SocialFish.py root pass```

5.	 Then, you go to the top under the Social Fish logo, you’ll notice a line that says 
“Go to **http://0.0.0.0:5000/neptune** to start”. So you  paste the ip address into your browser.

6.	 You will be redirected to a login page where you can enter “root” for username and “pass” for password

7.	 Now, you could write the name of the website you want to clone and the one to be redirected to.  For example:

8.	Now if you copy the ip address “0.0.0.0:5000/Neptune” You’ll be redirected to the cloned page which in this case is facebook. This is a fake page based on facebook design and everything that you enter gets copied and sent to the hacker. So to test it, just enter any garbage text and submit.

9.	You can check your entries or responses got from the fake site we cloned by going down on the original page and clicking “View” to see whatever username and pass were entered.

