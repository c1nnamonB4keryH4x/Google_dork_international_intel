 Shodan Dork Arsenal For IOT and OT

---

## General Device & Location Queries
```sh
city:"Bangalore"
city:"San Francisco" country:"US"
country:"RU"
country:"DE"
geo:"56.913055,118.250862"
geo:"37.7749,-122.4194"
net:210.214.0.0/16
net:192.168.0.0/24
org:"Microsoft"
org:"Amazon Technologies"
asn:AS15169
hostname:"google.com"
hostname:example.com
hostname:example.org
```
**Combined Examples**
```sh
city:"New York" port:22 org:"University"
country:"US" port:23 "default password"
geo:"48.8566,2.3522" port:80 title:"Login Page"
org:"university" port:443 "admin panel"
asn:AS15169 port:80 "Apache/2.4"
```

##  Device Types
```sh
device:firewall
device:router
device:webcam
device:printer
device:storage
device:phone
device:proxy
device:power
device:switch
device:pbx
device:telecom
device:specialized
device:"voip phone"
device:"load balancer"
```
**Combined Examples**
```sh
device:router port:80 "default password"
device:webcam port:554 has_screenshot:true
device:printer "Server: HP HTTP" country:"US"
device:pbx port:23 "PBX console"
```

##  Operating Systems
```sh
os:"Windows 7"
os:"Windows Server 2012"
os:"Linux 3.x"
os:"Android 9"
os:"FreeBSD 11.2"
```
**Combined Examples**
```sh
os:"Windows 7" port:3389 "Remote Desktop"
os:"Linux 3.x" port:22 title:"SSH Login"
os:"FreeBSD" port:80 "default admin"
```

## Product Banners
```sh
product:"Apache"
product:"nginx"
product:"Chromecast"
product:"D-Link"
product:"OpenWRT"
product:"Sonos Sound System"
```
**Combined Examples**
```sh
product:"nginx" port:443 ssl.cert.expired:true
product:"Chromecast" "Server: Chromecast"
product:"Apache" title:"Test Page" port:80
```

##  Customer Premise Equipment (CPE)
```sh
cpe:apple
cpe:microsoft
cpe:cisco
cpe:nginx
cpe:linksys
cpe:tplink
```
**Combined Examples**
```sh
cpe:tplink port:80 "admin"
cpe:cisco port:443 "SSL VPN"
cpe:nginx title:"Welcome to nginx!"
```

##  Web Server Signatures
```sh
server:apache
server:nginx
server:microsoft
server:cisco-ios
server:GoAhead-Webs
server:Boa
```

##  SSL Certificate Flags
```sh
ssl.cert.issuer.cn:"Let's Encrypt"
ssl.cert.subject.cn:"example.com"
ssl.cert.subject.cn:"*.gov"
ssl.cert.expired:true
ssl.cert.serial:1234567890abcdef
```

##  Authentication Issues
```sh
"default password"
"Login: admin" port:80
"root: root" port:23
"authentication disabled" port:5900
"Set-Cookie: PHPSESSID" port:80
"401 Authorization Required" title:"Admin Panel"
```

##  Open Ports
```sh
port:21
port:22
port:23
port:80
port:443
port:502
port:47808
port:3306
port:27017
port:9200
port:5006
port:9600
port:2455
port:102
port:2404
port:20000
port:44818
```

##  Database Services
```sh
product:"MySQL" port:3306
product:"MongoDB" port:27017 -authentication
product:"Redis" port:6379
product:"Cassandra" port:9042
product:"PostgreSQL" port:5432
product:"CouchDB" port:5984
product:"Elastic" port:9200
product:"Kibana" port:5601
product:"Riak" port:8087
```

##  ICS / SCADA Protocols
```sh
port:502 "modbus"
port:47808 "BACnet"
port:102 "S7Comm"
port:2404 "IEC 60870-5-104"
port:20000 "DNP3"
port:18245 "GE SRTP"
port:5006 "MELSEC-Q"
port:2455 "CODESYS"
port:1911 "Niagara Fox"
port:44818 "EtherNet/IP"
port:1962 "PCWorx"
port:789 "Red Lion"
port:20547 "ProConOS"
port:5094 "HART-IP"
port:9600 "Omron FINS"
```

##  Surveillance Systems
```sh
title:"webcamXP"
title:"IP Camera"
http.title:"NVR Web Client"
html:"DVR_H264 ActiveX"
html:"PIPS Technology ALPR Processors"
"NetSurveillance" "uc-httpd"
```

##  Telephony / VoIP
```sh
port:5060 "sip server"
port:23 "PBX login"
"Polycom Command Shell"
"PBX gateway console" -password
"VoIP status page" port:80
```

## Industrial Manufacturers
```sh
product:"Siemens"
product:"Mitsubishi Electric"
product:"Schneider Electric"
product:"Allen-Bradley"
product:"Rockwell Automation"
product:"Honeywell"
```

##  Smart Home & Consumer IoT
```sh
title:"Baby Monitor"
title:"Smart Plug"
"Server: AV_Receiver" port:80
"Chromecast:" port:8008
"Server: Roku"
"Server: IP Webcam Server"
"Model: PYNG-HUB"
```

##  Exposed Configuration Files
```sh
http.title:"Index of /"
http.html:"wp-config.php"
http.html:"passwd"
http.html:"user.txt"
http.html:".pem"
http.html:"database.yml"
```

##  Exploit & CVE Recon
```sh
"Content-Type: %{(#" product:"Apache" port:80
"jndi:ldap" port:80,443
"smart install client active" product:"Cisco IOS"
ssl.jarm:07d14d16d21d21d07c42d41d00041d24a458a375eef0c576d23a7bab9a9fb1
http.favicon.hash:-1389058761 product:"Fortinet" port:443
```

##  Debug & Diagnostics
```sh
title:"PHP Info"
html:"X-Debug-Token"
html:"debug=true"
title:"Diagnostics"
html:"System Logs"
```

##  Geo & Org Targeting
```sh
country:"US"
city:"Chicago"
city:"New York" country:"US"
org:"University of Texas"

```

##  Regex / AI Pattern Search
```sh
regex:".*(admin|root).*(1234|admin|password).*"
regex:"password.*admin"
regex:"^.*user.*login.*$"
```
# 🛡️ Advanced Shodan Dork Applications for Global IoT/OT Organizations & Sectors

This enhanced document aligns Shodan dork intelligence with real-world **industrial, cyber-physical, and smart infrastructure ecosystems**. These dorks are designed to trace exposed IIoT/OT technologies by geography, industry, organization, and protocol fingerprinting.

---

## 🌐 Global OT Standards & Consortiums

### Industrial Internet Consortium (IIC)
```sh
org:"Industrial Internet Consortium" OR "IIC" (port:102 OR port:502 OR port:2404) title:"industrial" country:US,DE,CN
```

### Industrial IoT (IIoT) Forum
```sh
("IIoT" OR title:"Industrial Internet of Things") (port:44818 OR port:47808) http.title:"gateway"
```

### International Society of Automation (ISA)
```sh
org:"International Society of Automation" port:502 OR port:1911 title:"automation" "PLC"
```

### IEC-Compliant SCADA Devices
```sh
port:2404 "IEC 60870-5-104" "asdu address" -authentication country:US,DE,CN
```

### IEEE-Controlled Testbeds & Infrastructures
```sh
ssl.cert.subject.cn:"ieee.org" port:443 "testbed" OR "telemetry"
```

---

## 🇺🇸 North America

### NIST (Smart Grid + OT Security)
```sh
org:"NIST" (port:2404 OR port:47808 OR port:443) title:"SCADA" OR "smart grid"
```

### Department of Energy (DOE) / Grid Ops
```sh
org:"Department of Energy" "modbus" OR "ethernet/ip" port:502 OR port:44818
```

### NREL (Renewables Infrastructure)
```sh
hostname:nrel.gov (port:443 OR port:47808) title:"solar" OR "battery management"
```

### ASME (Industrial Engineering Networks)
```sh
org:"ASME" port:502 title:"process control" OR "CNC"
```

---

## 🇨🇦 Canada

### CSA (Smart Metering + Automation)
```sh
org:"CSA Group" (port:47808 OR port:9600) title:"automation controller"
```

### NRCan (Energy Research Endpoints)
```sh
hostname:nrcan.gc.ca port:443 "wind turbine" OR "solar node"
```

---

## 🇪🇺 Europe (Advanced Industrial Networks)

### Fraunhofer (Digital Factory Interfaces)
```sh
org:"Fraunhofer" (port:502 OR port:2455 OR port:1962) "industrial gateway"
```

### ZVEI (Electronics Infrastructure)
```sh
org:"ZVEI" port:102 "S7Comm" OR "SIMATIC"
```

### CEA / CNRS (France)
```sh
(hostname:cea.fr OR hostname:cnrs.fr) port:443 "smart energy"
```

---

## 🌏 Asia (SCADA + IoT in Mega-Infrastructure)

### CESI / CAS (China)
```sh
(hostname:cesi.cn OR hostname:cas.cn) (port:9600 OR port:2404) title:"RTU" OR "telemetry"
```

### IITs (India)
```sh
hostname:iit*.ac.in (port:2455 OR port:47808) "testbed" OR "sensor node"
```

### JEMA / JSME (Japan)
```sh
(hostname:jema-net.or.jp OR jsme.or.jp) port:44818 title:"robot arm" OR "PLC"
```

---

## 🌍 Global Infrastructure & Smart City Technologies

### Smart Cities (Smart Grids, Lighting, Traffic)
```sh
("smart city" OR "public lighting" OR "intelligent transport") (port:47808 OR port:80) title:"controller"
```

### Environmental Monitoring Nodes
```sh
("air quality" OR "weather station" OR "pollution sensor") port:443 OR port:8080
```

### Smart Agriculture
```sh
title:"greenhouse" OR "precision agriculture" port:502 OR port:9600 "soil sensor"
```

### Transportation + Vehicle Infrastructure
```sh
("V2X" OR "vehicle telematics") (port:5060 OR port:5006) title:"telemetry"
```

### Smart Energy (DER + BMS)
```sh
("DER" OR "battery" OR "inverter") (port:502 OR port:47808) title:"energy node"
```

### Healthcare IoT / MedTech
```sh
(title:"DICOM Server" OR "medical telemetry") (port:104 OR port:443) "device ID"
```

---

## 🛡️ ICS + OT Cybersecurity Detection

### Exposure of Industrial Intrusion Detection Systems
```sh
title:"IDS" OR "industrial firewall" OR "cyber-physical" port:443
```

### PLCs and SCADA panels with no authentication
```sh
(port:502 OR port:2455) -authentication title:"PLC Web Interface" OR "Control Panel"
```

### IoT Devices with Dangerous Defaults
```sh
"default password" OR "admin:admin" port:23,80,443 has_screenshot:true
```

---
