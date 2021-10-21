1.  What is  `iwconfig`
**iwconfig it's showing for us what we have wireless adapter in our machine and it showing the name of the adapter**

2.  How can we enabling monitor mode manually.

**-  let's use  `iwconfig wlan0`  command, as we can see,  `wlan0`  is now in managed mode.**
**-  we need to disconnect the card  `ifconfig wlan0 down`.**
**- Now, the next command will be to enable monitor mode on the card `iwconfig wlan0 mode monitor`.**
**-If there are no errors, we can enable the card again  `ifconfig wlan0 up`**

3.  Why, when we enable monitor mode, the card will lose its connection.
**When you switch to monitor mode you start passively and not actively treating signals and hence you lose the connection.**
