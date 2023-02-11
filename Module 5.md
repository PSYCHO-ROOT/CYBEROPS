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

