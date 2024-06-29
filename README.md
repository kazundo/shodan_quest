# Shodan Quest
Shodan Quest is a powerful and useful tool that can be used to search for sensitive devices/services on Shodan. The implemented collection of Shodan dorks can reveal sensitive personal and/or organizational information such as vulnerable internet routers or servers, access to some services like security cameras, maritime satellites, traffic light systems, prison pay phones, etc... This list is supposed to be useful for assessing security and performing pen-testing of systems. You can also make your own custom query.

![Shodan Quest Logo](https://i.ibb.co/Y361tXX/Shodan-quest.png)

Shodan Quest is not a perfect tool at the moment but provides basic functionalities to automate the search on Shodan based on your query or using the provided dorks selection.
There is also the possibility to save the result of a query in `.CSV` or `.TXT` (at moment) once the research completed.

### Proof Of Concept
[![Video PoC Shodan Quest](https://i.ibb.co/7gXHL9q/500px-youtube-social-play.png)](https://www.youtube.com/watch?v=-UWjLwERZxQ)

### Requirement
* Python 3 (Tested with Python 3.8.5)
* Shodan Account (API key)

### Installation
Clone this repository and run:
```shell
pip install -r requirements.txt
```
#### Usage
```
python3 shodan-quest.py
```
Then let yourself be guided!

![Shodan Quest Cli](https://i.ibb.co/Bg3ckHk/shodan-quest-demo.png)

### Contribution
Please consider contributing dorks that can reveal potentially sensitive information on Shodan.

### List of Dorks
I am not categorizing at the moment. Instead, I am going to just the list of dorks with a description. Many of the dorks can be modified to make the search more specific or generic.

 Dork                                           | Description
------------------------------------------------|--------------------------------------------------------------------------
"octobot" | Crypto Currency trading bot.
title:"Gekko" | Gekko UI Crypto Currency trading bot.
"MongoDB Server Information" port:27017 -authentication | MongoDB database servers open authentication.
"Set-Cookie: mongo-express=" "200 OK" |  Mongo Express Web GUI.
mysql port:"3306" | MySQL-powered databases.
port:"9200" all:"elastic indices" | ElasticSearch-powered instances.
port:5432 PostgreSQL | PostgreSQL-powered databases
proftpd port:21 | proftpd server.
"220" "230 Login successful." port:21 | FTP servers that allow anonymous logins.
openssh port:22 | OpenSSH server.
port:"23" | Telnet server.
"Polycom Command Shell" -failed port:23 | Polycom Video Conferencing.
port:"25" product:"exim" | EXIM-powered mail servers.
port:"11211" product:"Memcached" | Memcached ddos.
"X-Jenkins" "Set-Cookie: JSESSIONID" http.title:"Dashboard" | Jenkins Dashboard.
"Docker Containers:" port:2375 | Docker APIs.
"Docker-Distribution-Api-Version: registry" "200 OK" -gitlab | Docker Private Registries.
"dnsmasq-pi-hole" "Recursion: enabled" | Pi-hole Open DNS Servers.
http.favicon.hash:"1485257654" "200" | SonarQube Dashboard.
"port: 53" Recursion: Enabled | DNS servers with recursion enabled.
port:8291 os:"MikroTik RouterOS 6.45.9" | Routers and other networking gear running an older and possibly vulnerable version of the RouterOS.
product:"Apache httpd" port:"80" | Apache web server.
product:"Microsoft IIS httpd" | Microsoft IIS web server.
product:"nginx" | Nginx web server.
"port: 8080" product:"nginx" | Nginx web server tageting 8080 port.
net:175.45.176.0/22,210.52.109.0/24,77.94.35.0/24 | North Korean server.
os:"windows 7" | Find devices based on windows 7.
os:"Windows 10 Home 19041" | Find devices based on windows 10.
os:"Linux" | Find devices based on Linux.
"Android Debug Bridge" "Device" port:5555 | Android Root Bridges.
Server: SQ-WEBCAM | Find webcams.
"Server: yawcam" "Mime-Type: text/html" | Find webcams.
title:"xzeres wind" |  XZERES Wind Turbines.
port:5006,5007 product:mitsubishi | Mitsubishi Electric, MELSEC-Q protocol is commonly used by control system.
"Server: IP Webcam Server" "200 OK" | Android IP Webcam Server.
("webcam 7" OR "webcamXP") http.component:"mootools" -401 | webcamXP/webcam7.
"Server: AV_Receiver" "HTTP/1.1 406" | Yamaha Stereos.
"\x08_airplay" port:5353 | Apple AirPlay Receivers.
"Chromecast:" port:8008 | Chromecasts / Smart TVs.
"Model: PYNG-HUB" | Crestron Smart Home Controllers
remote desktop "port:3389" | Windows Remote Desktop default port.
"authentication disabled" "RFB 003.008" | Devices with VNC available without authentication.
"Authentication: disabled" port:445 | Samba protocol default port 445 with authentication disabled.
"X-Plex-Protocol" "200 OK" port:32400 | Plex devices.
"220" "230 Login successful." port:21 | NAS devices FTP services running.
"Set-Cookie: iomega=" -"manage/login.html" -http.title:"Log In" | Iomega / LenovoEMC NAS Drives.
Redirecting sencha port:9000 | Buffalo TeraStation NAS Drives.
"Authentication: disabled" port:445 | SMB (Samba) File Shares. 
"Serial Number:" "Built:" "Server: HP HTTP" | HP Printers.
"SERVER: EPSON_Linux UPnP" "200 OK" | Epson Printers.
"Server: EPSON-HTTP" "200 OK" | Epson Printers.
ssl:"Xerox Generic Root" | Xerox Copiers/Printers.
"Server: KS_HTTP" "200 OK" | Canon Printers.
"Server: CANON HTTP Server" | Canon Printers.
"Server: Prismview Player" | Samsung Electronic Billboards.
"in-tank inventory" port:10001 | Gas Station Pump Controllers.
P372 "ANPR enabled" | Automatic License Plate Readers.
mikrotik streetlight | Traffic Light Controllers / Red Light Cameras.
"voter system serial" country:US | "voter system serial" country:US.
"Cisco IOS" "ADVIPSERVICESK9_LI-M" | Telcos Running Cisco Lawful Intercept Wiretaps.
"[2J[H Encartele Confidential" | Prison Pay Phones.
http.title:"Tesla PowerPack System" http.component:"d3" -ga3ca4f2 | Tesla PowerPack Charging Status.
"Server: gSOAP/2.8" "Content-Length: 583" | Electric Vehicle Chargers.
"Cobham SATCOM" OR ("Sailor" "VSAT") | Maritime Satellites.
title:"Slocum Fleet Mission Control" | Submarine Mission Control Dashboards.
"Server: CarelDataServer" "200 Document follows" | CAREL PlantVisor Refrigeration Units.
http.title:"Nordex Control" "Windows 2000 5.0 x86" "Jetty/3.1 (JSP 1.1; Servlet 2.2; java 1.6.0_14)" | Nordex Wind Turbine Farms. 
"[1m[35mWelcome on console" | C4 Max Commercial Vehicle GPS Trackers
"DICOM Server Response" port:104 | DICOM Medical X-Ray Machines.
"Server: EIG Embedded Web Server" "200 Document follows" | GaugeTech Electricity Meters.
"Siemens, SIMATIC" port:161 | Siemens Industrial Automation.
"Server: Microsoft-WinCE" "Content-Length: 12581" | Siemens HVAC Controllers.
title:"Sony Network Camera" | Sony Video Surveillance Camera.
title:"network camera vb-" | Canon Video Surveillance Camera.
title:"INSTAR Full-HD IP-Camera" | INSTAR Video Surveillance Camera.
title:"VideoIQ Camera Login" | VideoIQ Video Surveillance Camera.
title:"Milesight Network Camera" | Milesight Video Surveillance Camera.
title:"Alphafinity Network Camera" | Alphafinity Video Surveillance Camera.
title:"IP Network Camera" | Panasonic Video Surveillance Camera.

### Note
FOR EDUCATIONAL PURPOSE ONLY.
