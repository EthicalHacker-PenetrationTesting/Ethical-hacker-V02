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

**Note:** Before starting the virtual machine, you should disconnect the wireless adapter, then start the kali machine, once the kali is open, connect the wireless adapter.

## MAC addresses 
A media access control address (MAC address) is a unique identifier assigned to a network interface controller (NIC) for use as a network address in communications within a network segment.

Changing your MAC address can help you to either connect to a network by being on a whitelist, or to bypass a blacklist.

> The only way to change the MAC address is to change it in the RAM so it will only be changed for the current session, and when you restart, you will have to change it again.

We have five important steps to change the MAC address:-\

1. We need to know what is the Wi-Fi card's name by using this command

		iwconfig

[add the image]

> `iwconfig` is used to set the parameters of the network interface that are particular to the wireless operation

2. Disable the wireless card, using this command

		ifconfig wlan0 down

3. Changing the MAC address by using tools called `macchanger` this tools have many options, let's know them 

| options | used for |
|--|--|
| -h, -v | show the help and version |
| -s | to show our current MAC address |
| -e | set random vendor MAC of the same kind |
| -A | set random vendor MAC of any kind |
| -p | Reset to original |
| -r | set fully random MAC |
| -l | print known vendor |
| -b | pretend to be a burmed-in-address  |

know for changing the MAC address, we can use `--r or --random`

	macchanger --r wlan0

[add the image]

4. Enable the wireless card 

		ifconfig wlan0 up

[add image for `ifconfig wlan0`]
