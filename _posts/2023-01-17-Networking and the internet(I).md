---
layout: post
title: Networking and the Internet(I)
tags: 計算機概論
categories: 大學課堂筆記
date: '2023-01-17 01:35 +0800'
published: true
---
計算機概論-Networking and the Internet(I)隨手記
{: .message }

# Networking and the Internet(I)
## Network Classifications
* Scope
    * LAN: Local area network.
    * MAN: Metropolitan area network.
    * WAN: Wide area network.
* Ownership
    * Closed 
    * Opened
* Topology (拓樸學)
    * Bus:
        ![](https://i.imgur.com/1QUPg2e.png)
    * Ring:
        ![](https://i.imgur.com/bWnGTBf.png)
    * Star:
        ![](https://i.imgur.com/EWTkIgx.png)
## Protocols
* Token Ring
    * Popular in ring topology.
    * Token and messages are passed in one direction.
    * Only the machine which gets the token can transmit its message.
* CSMA/CD (Carrier sense, mutiple access with collision detection)
    * Popular in bus topology.
    * Broadcasting.
    * When collision, both machines wait for a random time before trying again. 
* CSMA/CA (Carrier sense, mutiple access with collision avoidence)
    * Popular in wireless Ethernet.
    * Broadcasting.
    * Detect if a channel is idle, if so, wait for a random time and then detect again. If the channel is still idle, then start sending.
## Wireless and Access Point(AP)
* Wi-Fi(wireless fidelity)
* IEEE 802.11-Standard for wireless network(b, g, i, n, ac...)
![](https://i.imgur.com/MOBFzwQ.png)
## Repeater，Bridge，Switch(Compatible Networks)
Reference: https://notfalse.net/66/repeater-hub-bridge-switch
* The protocol between these devices have to be the same.
* Repeater(Amplifier)
    * Passing through messages.
    * Connecting two compatible networks
![](https://i.imgur.com/0t1ZGPW.png)
* Bridge
    * Only passing those messages addressed to the other side.
    * Connecting two compatible networks more efficiently.
![](https://i.imgur.com/QEsDF9x.png)
* Switch(Multiple Bridge)
    * A bridge with multiple connections.
    * Connecting mutiple compatible networks efficiently.
![](https://i.imgur.com/uwwGpYy.png)
## Router(Incompatible Networks)
![](https://i.imgur.com/rJmNTSf.png)
* Router
    * Building a network of networks.(The protocol can be different)
    * Most come with firewall management.
## Interprocess Communication
![](https://i.imgur.com/6pWclWl.png)
* Server-Client
    * One server, several clients.
    * Clients initiate communications by sending requests.
* P2P(Peer-to-Peer)
    * Two processes communicating as equals.
    * The most popular distribution mode nowadays. 
## Distributed Systems
![](https://i.imgur.com/ZmowcOK.png)
* Infrastructure can be provided by standardized toolkits.
    * Ex: Java Beans，.NET framework.
## Internet Architecture
![](https://i.imgur.com/rB8IPMk.png)
* Domain
    * A network or an internet controlled by one single authority.
* ICANN(Internmet corporation for assigned names and numbers)
    * Supervise the registration of doimains
* Gateway
    * A router that connects a domain to the rest of the Internet.
## Internet Composition
![](https://i.imgur.com/3reTfwk.png)
* Internet Service Provider(ISP)
    * Allow customer to connect their domain to the ISP's equiment or join the domain already established by the ISP.
## IP Addresses
* IP(internet protocol)address
    * IPv4 -> 32bits(all are allocated already)
    * IPv6 -> 128bits
## Name Server vs Domain Server 
* Name server: 
    * Name servers organize and route traffic across the internet to get you to the right server.
* Domain Name Server(DNS)
    * A server that provide you with server information.
![](https://i.imgur.com/rYtlfru.png)
## Internet Application
* VoIP(Voice over Internet protocol)
* email(electronic mail)
* FTP(file transfer protocol)
* telnet and ssh(secure shell)
* P2P
## Browsers
* HTTP(Hyper text transfer protocol)
* URL(uniform resource locator)
* How a browser get access to a webpage(document):
![](https://i.imgur.com/hY3bIGo.png)
## Client-side and Server-side
* Client-side(The program is executed on one's pc)
    * Java applets
    * Javascript
    * Flash
* Server-side(The program is executed on the server)
    * CGI
    * Servlets
    * PHP
* Online game use both techniques.
## Internet Protocol
Reference:https://ithelp.ithome.com.tw/articles/10259569?sc=pt
* Layers
    * OSI Model
        * Reference:   https://en.wikipedia.org/wiki/OSI_model
    
    ![](https://i.imgur.com/e5dfV9e.png)

    * TCP/IP Model
        * Application: constructs message into packets.
        * Transport: chops message into packages.
        * Network: handles routing through the Internet.
        * Link handles actual transmission of packets.

    ![](https://i.imgur.com/0gNoMlv.png)

* Port
    * Incoming messages are delivered to different applications by unique port numbers.
![](https://i.imgur.com/54gXvXI.png)
## TCP/IP
* TCP and UDP(Transport Layer)
    * TCP(transmission control protocol):handshake berfore sending packets. => slow but reliable.
    * UDP(user datagram protocol): directly sending packets. => fast but not reliable.
* IP(NEtwork Layer)
    * routing based on IP(IPv4, IPv6)
* TCP and IP are two protocols. TCP/IP is a collection of protocols more than just TCP and IP.
## Security
* Attacks
    * Malware
    * Denial of Service(Dos)
    * Spam
* Protections
    * Firewall
    * Spam filter
    * Proxy
    * Antivirus, antispyware
* Public/Private Keys System
    * Reference: https://medium.com/@RiverChan/%E5%9F%BA%E7%A4%8E%E5%AF%86%E7%A2%BC%E5%AD%B8-%E5%B0%8D%E7%A8%B1%E5%BC%8F%E8%88%87%E9%9D%9E%E5%B0%8D%E7%A8%B1%E5%BC%8F%E5%8A%A0%E5%AF%86%E6%8A%80%E8%A1%93-de25fd5fa537
    * SSL(Secure Scoket Layer)
	    * Application: sftp, https, ssh
    * To prevent fishing, a certificate authority is needed, to ensure to correctivity of a key.
![](https://i.imgur.com/fnACCIR.png)
## RSA Algorithm
Reference: https://ithelp.ithome.com.tw/articles/10250721
* Generation
    ![](https://i.imgur.com/5SMoi2J.png)
* Encryption
    ![](https://i.imgur.com/WTvEm7R.png)

* Decryption
    ![](https://i.imgur.com/6fnmG7A.png)


    


	




