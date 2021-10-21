# Pre-Connection Attacks

## High Level Goals

By the end of this lesson, you will be familiar with the following:

1. Network Sniffer Tool
2. Network traffic analysis
3. Deauthentication attack
4. Fake access point

## Network Sniffer Tool

A network sniffer, also known as a packet analyzer, is either software or hardware that can intercept data packets as they travel across a network. Admins use network sniffers to monitor network traffic at the packet level, helping ensure network health and security.

First things, we will use our Wi-Fi card in monitor mode,

	airodump-ng wlan0

[image `airodump-ng wlan0`]

let's analyze the output:

| parameters name | what it does |
|--|--|
| `BSSID` | The `BSSID` is the MAC address for the AP |
| `PWR` |The power is how far the AP from our Wi-Fi card |
| `Test` | The test router that we will be running a few attacks against |
| `Beacons` | The signals that the AP sends |
