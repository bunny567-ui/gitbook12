# Landscape Connectors

In general, SAP ECC and S/4HANA landscape systems will be deployed in the Client Network. As a SaaS platform, ReleaseOwl must communicate with the SAP system from the ReleaseOwl Network. There are multiple ways you can establish secure communication between ReleaseOwl and SAP systems.

**Whitelisting ReleaseOwl Server IP Address**\
Users must add the ReleaseOwl IP Address as a trusted IP in the client network settings. The IP address will be provided by mail communication during implementation.

**Setting up SAP Router**

**Reverse Proxy**\
A reverse proxy server is a type of proxy server that typically sits behind the firewall in a private network and directs client requests to the appropriate backend server. It provides an additional level of abstraction and control to ensure the smooth flow of network traffic between clients and servers.

ReleaseOwl will connect to the SAP On-Premise domain controller using Apache2 as Reverse Proxy as follows:

**Apache2 Reverse Proxy Configuration**\
Transport Domain Controller URL: `https://<domain-controller>:8080`\
Reverse Proxy (Apache2 server) URL: `https://<proxy-host>:443/`

Sample Configuration of reverse Proxy (Apache2) in file:\
`/etc/apache2/sites-enabled/rosap-ssl.conf`\


**ReleaseOwl Transport Domain Controller Configuration**\



<figure><img src="../../.gitbook/assets/image (225).png" alt=""><figcaption></figcaption></figure>

### **Application Server:**

**Port:** port to access the proxy

**Credential:** SAP On-Prem userID and password

### **Setting up Proxy Server**

SAP Router is a proxy between SAP systems on different networks and between SAP systems and external applications which means it acts as an additional layer of filter/firewall in addition to the main firewall.

ReleaseOwl interacts with SAP Systems via HTTP/HTTPS protocol, but SAP Router runs on Network Layer (NI) which cannot understand the HTTP/HTTPS protocol. So, we have to configure Reverse Invoke (RI) in SAP Router referring to the below link

[https://help.sap.com/viewer/af8bcf35778c4d098ba482cc0b59f339/7.5.22/en-US/46d37ef8e5343c1de10000000a155369.html](https://help.sap.com/viewer/af8bcf35778c4d098ba482cc0b59f339/7.5.22/en-US/46d37ef8e5343c1de10000000a155369.html)

The diagram below shows connection flow between SAP Routers (server and client)\


**Note:** One SAP Router should be configured for each domain controller because of HTTPS access using reverse invoke.

**RI Configuration of Server SAP Router**

RI can be configured with SNC (Secured Network Communications) or without SNC.

**With SNC**

SAP Router communication can be made more secure using Secure Network Communications by referring to the following links:

[https://support.sap.com/en/tools/connectivity-tools/saprouter/install-saprouter.html](https://support.sap.com/en/tools/connectivity-tools/saprouter/install-saprouter.html)

or

[https://wiki.scn.sap.com/wiki/display/Basis/How+to+setup+SNC+connection+between+SAProuters](https://wiki.scn.sap.com/wiki/display/Basis/How+to+setup+SNC+connection+between+SAProuters)

For secure communication certificates should be exchanged between client and server.

**Configuration File**

server = true

client\_hostname = 3.232.119.28 (Actual IP will be provided during setup)

client\_service = 5001

reg\_service = 5002 (to be provided by customer during setup)

**Route Permission file**

KP p: \* 8080

**Start SAP Router**

./saprouter -K p: -i -S 4002 -R

**Without SNC**

Configuration File

server = true

client\_hostname = 3.232.119.28 (Actual IP will be provided during setup)

client\_service = 5001

reg\_service = 5002

Route permission file

3.232.119.28 \* 8080

Start SAP Router

./saprouter -i -S 4002 -R

### **Configuration parameters that are required by RO from customer**

* Server certificates for SNC configuration
* Common Name (CN) of Server SAP Router to specify in route permission table
* IP address and port number for accessing Server SAP Router
* Domain name or IP and HTTP port of the Domain controller URL (These ports need not be opened to outside of customer network)

### **Configuration parameters that are required by customer from RO**

* Client certificate for SNC configuratio&#x6E;**(nexus URL)**
* Common Name (CN) of client SAP Router to specify in the route permission table
* Client SAP Router registration port, Access port and IP to establish RI connection.

### **Reference Links**

* [https://support.sap.com/en/tools/connectivity-tools/saprouter.html#section\_1556745727](https://support.sap.com/en/tools/connectivity-tools/saprouter.html#section_1556745727)[https://help.sap.com/saphelp\_nwce10/helpdata/en/46/d37f01e5343c1de10000000a155369/content.htm?no\_cache=true](https://help.sap.com/saphelp_nwce10/helpdata/en/46/d37f01e5343c1de10000000a155369/content.htm?no_cache=true)
