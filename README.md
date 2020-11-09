# Getting Started

### Protocol and Ports
In this lesson, we will learn a few new concepts to better understand and talk about setting up a web-server.

- port
- protocol
- HTTP

#### Protocol
A protocol is a standard set of rules that allow electronic devices to communicate with each other. These rules include what type of data may be transmitted, what commands are used to send and receive data, and how data transfers are confirmed. You can think of a protocol as a spoken language. Each language has its own rules and vocabulary. If two people share the same language, they can communicate effectively. Similarly, if two hardware devices support the same protocol, they can communicate with each other, regardless of the manufacturer or type of device. For example, an Apple iPhone can send an email to an Android device using a standard mail protocol. A Windows-based PC can load a webpage from a Unix-based web server using a standard web protocol.

Protocols exist for several different applications. Examples include wired networking (e.g., Ethernet), wireless networking (e.g., 802.11ac), and Internet communication (e.g., IP). The Internet protocol suite, which is used for transmitting data over the Internet, contains dozens of protocols. These protocols may be broken up into four catagories:

- Link layer - PPP, DSL, Wi-Fi, etc.
- Internet layer - IPv4, IPv6, etc.
- Transport layer - TCP, UDP, etc.
- Application layer - HTTP, IMAP, FTP, etc.

Link-layer protocols establish communication between devices at a hardware level. In order to transmit data from one device to another, each device's hardware must support the same link layer protocol. Internet layer protocols are used to initiate data transfers and route them over the Internet. Transport layer protocols define how packets are sent, received, and confirmed. Application layer protocols contain commands for specific applications. For example, a web browser uses HTTPS to securely download the contents of a webpage from a web server. An email client uses SMTP to send email messages through a mail server.

Protocols are a fundamental aspect of digital communication. In most cases, protocols operate in the background, so it is not necessary for typical users to know how each protocol works. Still, it may be helpful to familiarize yourself with some common protocols so you can better understand settings in software programs, such as web browsers and email clients.

Internet Port Number
All data transmitted over the internet is sent and received using a specific set of commands, also known as a protocol. Each protocol is assigned a specific port number. For example, all website data transferred over HTTP uses port 80. Data sent over HTTPS uses port 443. Other common ports include:

- Port 20 - FTP (file transfer protocol)
- Port 22 - SSH and SFTP
- Port 25 - SMTP (outgoing email)
- Port 465 - SMTP over SSL
- Port 143 - IMAP (incoming email)
- Port 993 - IMAP over SSL

Port numbers are similar to wireless channels in that they prevent conflicts between different protocols. They also provide a simple way to implement network security measures, since it is possible to allow or block specific protocols.

HTTP
Stands for "Hypertext Transfer Protocol." HTTP is the protocol used to transfer data over the web. It is part of the Internet protocol suite and defines commands and services used for transmitting webpage data.

HTTP uses a server-client model. A client, for example, may be a home computer, laptop, or mobile device. The HTTP server is typically a web host running web server software, such as Apache or IIS. When you access a website, your browser sends a request to the corresponding web server and it responds with an HTTP status code. If the URL is valid and the connection is granted, the server will send your browser the webpage and related files.

Some common HTTP status codes include:

- 200 - successful request (the webpage exists)
- 301 - moved permanently (often forwarded to a new URL)
- 401 - unauthorized request (authorization required)
- 403 - forbidden (access is not allowed to the page or directory)
- 500 - internal server error (often caused by an incorrect server configuration)

HTTP also defines commands such as GET and POST, which are used to handle form submissions on websites. The CONNECT command is used to facilitate a secure connection that is encrypted using SSL. Encrypted HTTP connections take place over HTTPS, an extension of HTTP designed for secure data transmissions.

NOTE: URLs that begin with "http://" are accessed over the standard hypertext transfer protocol and use port 80 by default. URLs that start with "https://" are accessed over a secure HTTPS connection and often use port 443.

