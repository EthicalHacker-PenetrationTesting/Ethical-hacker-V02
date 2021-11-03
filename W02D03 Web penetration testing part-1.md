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