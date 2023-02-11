# 5 - Network Protocols
## 5.1 Network Communications Process
### + Networks of Many Sizes
Networks come in all sizes. They range from simple networks that consist of two computers, to networks connecting millions of devices.

***Small Home Networks*** - Small home networks connect a few computers to each other and to the internet.

***SOHO*** network allows computers in a home office or a remote office to connect to a corporate network, or access centralized, shared resources.

***Medium to large networks***, such as those used by corporations and schools, can have many locations with hundreds or thousands of interconnected hosts.

The ***internet*** is a network of networks that connects hundreds of millions of computers world-wide.

In small businesses and homes, many computers function as both the servers and clients on the network. This type is called a peer-to-peer network.

### + Client-Server Communications
***Client*** computers have software installed, such as web browsers, email clients, and file transfers applications. This software enables them to request and display the information obtained from the server.

***Servers*** are simply computers with specialized software. This software enables servers to provide information to other end devices on the network.

* ***File Server*** - The file server stores corporate and user files in a central location.
* ***Web Server*** - The web server runs web server software that allows many computers to access web pages.
* ***Email Server*** - The email server runs email server software that enables emails to be sent and received.

![net](https://user.oc-static.com/upload/2019/05/29/15591415735154_clients_servers1.png)

### + Tracing the Path
We tend to think about the data networks we use in our daily lives as we think about driving a car.
We do not really care what happens in the engine as long as the car takes us where we want to go.
However, just like a car’s mechanic knows the details of how a car operates, you need to have a deep understanding of how networks operate.

#### Example :
Terry has connected her phone to the school Wi-Fi network. Her search is submitted from her phone to the school network wirelessly. 
Before her search can be sent, the data must be addressed so that it can find its way back to Terry. Her search terms are then represented as a string of binary data that has been encoded into radio waves. 
Her search string is then converted to electrical signals that travel on the school’s wired network until they reach the place at which the school’s network connects to the Internet Service Provider’s (ISP) network. 
A combination of technologies take Terry’s search to the search engine website.
and is processed by its powerful servers. The results are then encoded and addressed to Terry’s school and her device.

All of these transitions and connections happen in a fraction of a second, and Terry has started on her path to learning about her subject.

## 5.2 Communications Protocols
### + What are Protocols?
Having a wired or wireless physical connection between end devices is not enough to enable communication. For communication to occur, devices must know “how” to communicate. Communication, whether by face-to-face or over a network, is governed by rules called protocols.

For example, consider two people communicating face-to-face. Prior to communicating, they must agree on how to communicate. If the communication is using voice, they must first agree on the language. Next, when they have a message to share, they must be able to format that message in a way that is understandable. For example, if someone uses the English language, but poor sentence structure, the message can easily be misunderstood.

Similarly, network protocols specify many features of network communication

Networking protocols define a common format and set of rules for exchanging messages between devices. Network protocols dictate the message encoding, formatting, encapsulation, size, timing, and delivery options.
### + The TCP/IP Protocol Suite

![net](https://ccna-200-301.online/wp-content/uploads/2020/04/TCP-IP-Protocol-Suite.png)

### - Application Layer

Consist of 5 main parts : Name System / Host Config / Email / File Transfer / Web & Web Service

#### Name System
* ***DNS*** - Translates domain names such as cisco.com, into IP addresses.
#### Host Config
* ***DHCPv4/6*** - A DHCP server dynamically assigns IPv4/6 addressing information to DHCP clients at start-up and allows the addresses to be re-used when no longer needed.
* ***SLAAC*** - A method that allows a device to obtain its IPv6 addressing information without using a DHCPv6 server.
#### Email
* ***SMTP*** - Enables clients to send email to a mail server and enables servers to send email to other servers.
* ***PoP3*** - Enables clients to retrieve email from a mail server and download the email to the client's local mail application.
* ***IMAP*** - Enables clients to access email stored on a mail server as well as maintaining email on the server.
#### File Transfer
* ***FTP*** - Sets the rules that enable a user on one host to access and transfer files to and from another host over a network .
* ***SFTP*** - SSH File Transfer Protocol. Can be used to establish a secure file transfer session in which the file transfer is encrypted.
#### Web & Web Service
* ***HTTP*** - A set of rules for exchanging text, graphic images, sound, video, and other multimedia files on the World Wide Web.
* ***HTTPS*** - A secure form of HTTP that encrypts the data that is exchanged over the World Wide Web.
* ***REST*** - Representational State Transfer. Use application programming interfaces (APIs) and HTTP requests to create web applications.

### - Transport Layer

Consist of 2 Parts : Connection-Oriented and Connectionless

#### Connection-Oriented
* ***TCP*** -  Enables reliable communication between processes running on separate hosts, that confirm successful delivery.
#### Connectionless
* ***UDP*** -  Enables a process running on one host to send packets to a process running on another host. UDP does not confirm successful datagram transmission.

### - Internet Layer

Consist of 3 main Parts : Internet protocol / Messaging / Routing Protocols

#### Internet Protocol
* ***IPv4***
* ***IPv6***
* ***NAT*** - Translates IPv4 addresses from a private network into globally unique public IPv4 addresses.
#### Messaging
* ***ICMPv4/6*** - Provides feedback from a destination host to a source host about errors in packet delivery.
#### Routing Protocols
* ***OSPF*** -  Uses a hierarchical design based on areas. OSPF is an open standard interior routing protocol.
* ***EIGRP*** - Uses a composite metric based on bandwidth, delay, load and reliability.
* ***BGP*** - Used between Internet Service Providers (ISPs).

### Network Access Layer

Consist of 2 Parts : Address Resolotion / Data Link Protocols

#### Address Resolotion
* ***ARP*** - Provides dynamic address mapping between an IPv4 address and a hardware address. (He may be also in The internet layer)
#### Data Link Protocols
* ***Ethernet***
* ***WLAN***
* 
