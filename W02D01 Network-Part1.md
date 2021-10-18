# Network

## High Level Goals

By the end of this lesson, you will be familiar with the following:
1. what is network
2. Connecting to a wireless adapter
3. MAC addresses
4. Wireless modes - managed and monitor
5. Enabling monitor mode manually
6. Enabling monitor mode using airmon-ng

## What is network 
A network is a collection of computers, servers, mainframes, network devices, peripherals, or other devices connected to allow data sharing. An example of a network is the Internet, which connects millions of people all over the world.

##  Connecting to a wireless adapter

we will connect adapter to kali by using the following steps:
1. open VirtualBox and click on the machine that we want to connect the USB adapter to.
2. Go to settings in USB, and make sure that **Enable USB Controller** is checked 

![USB1](/img/USB1.png)

3. We need to pick the USB hardware type that is used by our adapter, go to the `+` sign and click on it.

![USB2](/img/USB2.png)

4. Now, click in the name of your USB adapter in my case it is `Realtek 802.11n WLAN Adapter [0200]` 

![USB3](/img/USB3.png)
