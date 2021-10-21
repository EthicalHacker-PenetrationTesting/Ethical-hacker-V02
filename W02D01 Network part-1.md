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

## Wireless modes - managed and monitor


First, we need to know what is the default mode in our wireless card if we use `iwconfig` we will see that waln0 has a default mode called managed mode

[add image]

Basically, in this mode, the wireless device will only receive packets, or will
only try to capture packets that have our device's MAC address as the destination MAC. It will only capture packets that are actually directed to our computer.

first tools we will use it is `airmon-ng`

[image for `airmon-ng`]

we will start monitor mode on `wlan0` by using 

	airmon-ng start wlan0

`airmon-ng` is the name of the program, `start` initializes monitor mode, and `wlan0` is the wireless card name.

[image]

We now have monitor mode enabled on `mon0`, whenever we want to use monitor mode, we will specify `mon0` as the interface.

> All interfaces might not have the same name, so it will probably be called
`wlan0mon` or something else, it doesn't matter, just make sure to use the name that monitor mode is enabled on.

If we use `iwconfig wlan0mon`, we will see that the mode is now monitor mode instead of managed mode

[image `iwconfig wlan0mon`]

This means that we can use this card to capture any packet within our range,
even if the packet is not directed to our device, and even if it doesn't have the
MAC address of our device as the destination MAC.

**Important Notes:**

- when we enable monitor mode, the card will lose its connection.
- The next thing is to make sure to use the name that monitor mode is
enabled on.
- The third note is that if we enable monitor mode and run an attack in the
future, and get unexpected results, we can come back and try one of the
other methods for enabling monitor mode.

> If we want to stop monitor mode, we can use the `airmon-ng stop wlan0mon` command

## Enabling monitor mode manually

With the latest update of `aircrack-ng`, `airmon-ng` stopped working for some wireless cards. So now we want to make it manually by using this steps:

1. let's use `iwconfig wlan0` command, as we can see `wlan0` is now in managed mode.

[image `iwconfig wlan0`]

2. we need to disconnect the card `ifconfig wlan0 down`

3. Now, the next command will be to enable monitor mode on the card

		iwconfig wlan0 mode monitor

4. If there are no errors, we can enable the card again `ifconfig wlan0 up`

> When we use this part of monitor mode the name will be `wlan0`  not `wlan0mon,`

## Enabling monitor mode using airmon-ng

it is easy to use it, only use these steps:

1. let's disconnected the card `ifconfig wlan0 down`
2. this command will be kill any service that might interfere with enabling monitor mode `airmon-ng check kill`

[image  `airmon-ng check kill`]

3.  we will enable monitor mode in the same way that we did in the first method, using the `airmon-ng start wlan0`

4. Now, as monitor mode has been started on `wlan0mon`, which is a virtual wireless interface, we can use the `iwconfig` command to check. Then, it will be in monitor mode.

[images `iwconfig`]

> In the future, we're going to use monitor mode in different attacks. If an attack doesn't work, all we have to do is unplug the card, plug it back in, and try another method for enabling monitor mode.

## Practice 

1. What is `iwconfig` 

> Helpfull [link](https://koayyongcett.medium.com/part-4-kali-linux-basics-learn-common-network-commands-with-simple-command-line-a3dc315f8537)

2. How can we enabling monitor mode manually.

3. Why, when we enable monitor mode, the card will lose its connection.