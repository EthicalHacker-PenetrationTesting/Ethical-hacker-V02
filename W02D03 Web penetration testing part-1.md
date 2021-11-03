# Web Penetration  Testing

## Introductory Networking

## High Level Goals

By the end of this stage, you will be familiar with the following:
1. The OSI Model.
2. The TCP/IP Model.
3. An introduction to basic networking tools.

## The OSI Model

The OSI (**O**pen **S**ystems **I**nterconnection) Model is a standardized model which we use to demonstrate the theory behind computer networking. In practice, it's actually the more compact TCP/IP model that real-world networking is based off; however the OSI model, in many ways, is easier to get an initial understanding from.

The OSI model consists of seven layers:

| OSI | layers |
|--|--|
| Application  | Layer 7: -- The application layer of the OSI model essentially provides networking options to programs running on a computer. |
| Presentation  | Layer 6: -- The presentation layer receives data from the application layer |
| Session  | Layer 5: -- When the session layer receives the correctly formatted data from the presentation layer, it looks to see if it can set up a connection with the other computer across the network. |
| Transport | Layer 4: -- The transport layer is a very interesting layer that serves numerous important functions |
| Network  | Layer 3 -- The network layer is responsible for locating the destination of your request. |
| Data Link | Layer 2 -- The data link layer focuses on the _physical_ addressing of the transmission. |
| Physical  | Layer 1 -- The physical layer is right down to the hardware of the computer. |


## The TCP/IP Model

The TCP/IP model is, in many ways, very similar to the OSI model. It's a few years older, and serves as the basis for real-world networking. The TCP/IP model consists of four layers: Application, Transport, Internet and Network Interface. Between them, these cover the same range of functions as the seven layers of the OSI Model.

> _**Note:** Some recent sources split the TCP/IP model into five layers -- breaking the Network Interface layer into Data Link and Physical layers (as with the OSI model). This is accepted and well-known; however, it is not officially defined (unlike the original four layers which are defined in RFC1122). It's up to you which version you use -- both are generally considered valid._

![image-3](./img/image-3.png)

The processes of encapsulation and de-encapsulation work in exactly the same way with the TCP/IP model as they do with the OSI model. At each layer of the TCP/IP model a header is added during encapsulation, and removed during
 de-encapsulation.


When you attempt to make a connection, your computer first sends a special request to the remote server indicating that it wants to initialize a connection. This request contains something called a _SYN_ (short for Synchronize) bit, which essentially makes first contact in starting the connection process. The server will then respond with a packet containing the SYN bit, as well as another "acknowledgement" bit, called _ACK_. Finally, your computer will send a packet that contains the ACK bit by itself, confirming that the connection has been set up successfully. With the three-way handshake successfully completed, data can be reliably transmitted between the two computers. Any data that is lost or corrupted on transmission is re-sent, thus leading to a connection which appears to be lossless.

![SYN/ACK](/img/SYN/ACK.png)