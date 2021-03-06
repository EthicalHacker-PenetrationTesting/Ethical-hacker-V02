# Build up your Lap

## High Level Goals

By the end of this lesson, you will be familiar with the following:

- what is our lap
- VirtualBox
- Kali Linux
- Run Kali in VirtualBox 
- OWASP & installation 
- Metasploitable & installation
- windows & installation 

##  VirtualBox

### what is VirtualBox

Oracle VM VirtualBox is cross-platform virtualization software. It **allows users to extend their existing computer to run multiple operating systems** including Microsoft Windows, Mac OS X, Linux, and Oracle Solaria, at the same time.

### install VirtualBox

Go to [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads) and click on Windows hosts

![vBoxDownload](./img/VMBox-download.png)

Then open the `VirtualBox-6.1.26-145957-Win` setup and download it.


## Kali Linux

### What is Kali Linux

Kali Linux (formerly known as Backtrack Linux) is an open-source, Debian-based Linux distribution aimed at advanced Penetration Testing and Security Auditing. Kali Linux contains several hundred tools targeted towards various information security tasks, such as Penetration Testing, Security Research, Computer Forensics and Reverse Engineering. Kali Linux is a multi platform solution, accessible and freely available to information security professionals and hobbyists.

## Kali Linux Installation

- Go to [https://www.kali.org/get-kali](https://www.kali.org/get-kali) and click in Recommended

![Recommended](./img/kaliLunx-2.png)

- Finally click in the download button

![downloadButton](./img/kaliLunx-3.png)


## Run Kali in VirtualBox 

### we will change some setting in VirtualBox before install the Kali-linux

1. Create new machine:

   - Click in `new`.
   - In the `Name` section write `Kali`.
   - In the `Type` section select `Linux`.
   - In the `Version` section select `Debian (64-bit)`.
   - Change the `1024` to `2024`.
   - Press next and in the `File location size` change the `8.00 GB` to `50.0 GB`.

2. now we must change some setting

   - Go to `Settings`.
   - On the left side go to `Storage` and press in `Controller: IDE O+` and click in `Add` then chose the `kali-linux.iso file` and press ok.
   - Go to the `Network` and select `Attached to` and choose `Nat network`.

- Nat network issue 

 select `file` in VirtualBox choose `Preferense` then go to network and press in add button

- Note: to read more about the Network in VirtualBox, visit [link](https://www.nakivo.com/blog/virtualbox-network-setting-guide)

### Now we are going to install Kali-linux

1.  Click `Start`.
2.  Press in `Graphical install`.

3.  Select language:

- ![installKali1](./img/install-kali-1.png)
- ![installKali2](./img/install-kali-2.png)
- ![installKali3](./img/install-kali-3.png)
- ![installKali4](./img/install-kali-4.png)

4. In configure the network:

   - `Hostname` write `Kali`.
   - `Domainname` make it empty.

5. set up the users and passwords:

   - `Full name for the new user` write `anything you like`.
   - `user for the account` make it default.
   - `password` make it `root`.

6. Partition disk:

   - `Partitioning methoud` should be `Guided-use entire disk`.
   - `Select disk to partition` make it default.
   - `Partitioning schema` choose `All files in one partition (recommended for new users)`.
   - `write change to diske` make sure to be `Yes`.

7. Software selection: - choose software to install:
   ![kaliLunx-4](./img/kaliLunx-4.png)

8. Install the GRUB bootloader
   - `Install the GRUB boot loader to your primary drive` make sure it is `Yes`.
   - `Device for boot loader installaion` choose the `/dev/sda (ata-VBOX_HARDDISK_VB894idi83-a88d4993)`.

**Now our Kali-linux are ready, make sure you have like picture**

![completeInstall](./img/completeInstallion.png).

### Creating and using snapshots

A virtual machine snapshot is **just an image of the state and data of a virtual machine, captured and stored at a given point in time**. A virtual machine's data includes all files from disk, in memory and on other supported storage devices. A VM snapshot does not have any impact on the virtual machine itself.

1. click in 

![snapshots1](./img/snpshots1.png)

2. Select **snapshots** 
3. Press in **Take**

**Note:** use the username and the password that you add it in the installation.

## OWASP & installation 

### What is OWASP 

The Open Web Application Security Project is an online community that produces freely-available articles, methodologies, documentation, tools, and technologies in the field of web application security. The Open Web Application Security Project provides free and open resources.

### Install OWASP

1. Go to [https://sourceforge.net/projects/owaspbwa](https://sourceforge.net/projects/owaspbwa).

![OWASP-1](./img/Screenshot_1.png)

2. Extract the file, then open your VirtualBox.

3. OWASPBWA installation:

- Click in `New`.

- In the `Name` write `OWSPBWA` and in the `Type` select, `Linux` finally in the `Version` choose `Other Linux (64-bit)`.

- In the `Memory size` make sure it is `1024`.

- In the `Hardesk selector` choose `Use an existing virtual hard disk file`, then do like the images:

![OWASP-2](./img/Screenshot_2.png)

![OWASP-3](./img/Screenshot_3.png)

![OWASP-4](./img/Screenshot_4.png)

- Select the file you are download it `OWASP_Broken_Web_Apps_VM_1.2`.

![OWASP-5](./img/Screenshot_5.png)

- Choose the first one `OWASP Broken Web Apps-cl1`.

![OWASP-6](./img/Screenshot_6.png)

- Finally, press create.

4. Run the `OWASPBWA`:

- make sure the `Network` Attached to `Host-only` before you start

- Now Click in `Start`

- You should have like this

![OWASP-7](./img/Screenshot_7.png)

- Now for `login` write `root` and the `password` is `owaspbwa`

![OWASP-8](./img/Screenshot_8.png)

- Now you can visit this IP address `[OWASP IP]` in your browser

![OWASP-9](./img/Screenshot_9.png)

## Metasploitable & installation 

Go to the [Metasploitable](https://information.rapid7.com/download-metasploitable-2017-thanks.html) website, and press Download, then extract the file. Finally, follow this steps:

1. Go to virtual box and click in `new`
2. make the `name` Metasploitable 
3. in the `Type` make it **Linux**
4. `version` make it **other-(64)**
5. make the ram `1024` then click next
6. click to **use an existing virtual hard disk,**  choose the Metasploitable download directory.
7. go to setting make the network `nat network` finally click to start

> Note the user is **msfadmin** and the password **msfadmin**
