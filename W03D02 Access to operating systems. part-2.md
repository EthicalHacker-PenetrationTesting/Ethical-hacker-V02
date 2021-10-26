# Access to operating systems

## Client side

First things we want to run Kali and Window 10,  we will use **Veil - Framework**.

The Veil Framework is a collection of tools designed for use during offensive security testing. When the time calls for it, Mandiant’s Red Team will use the Veil-Framework to help achieve their objective.  The most commonly used tool is Veil-Evasion, which can turn an arbitrary script or piece of shellcode into a Windows executable that will evade detections by common antivirus products.

We can use it by following this steps:

1. Go to the terminal and write, `rm -rf /root/.config/wine/vei` 
2. In the terminal write cd `cd /usr/share/vril/config`
3. Then write `./setup.py --force --silent`
4. Finally, `cd ..` and write `./veil.py`
