# Burp Suite

## High Level Goals

By the end of this lesson, you will be familiar with the following:

1. What Burp Suite.
2. Overview of the available tools in Burp Suite.
3. Navigating and configuring Burp Suite.

## What Burp Suite

Burp Suite is a framework written in Java that aims to provide a one-stop-shop for web application penetration testing and Its various tools work seamlessly together to support the entire testing process, from initial mapping and analysis of an application’s attack surface, through to finding and exploiting security vulnerabilities.

In its simplest form, **Burp Suite** can be classified as an Interception Proxy. While browsing their target application, a penetration tester can configure their internet browser to route traffic through the **Burp Suite** proxy server.

## Overview of the available tools in Burp Suite

Whilst Burp Community has a relatively limited feature-set compared to the Professional edition, it still has many superb tools available. These include:

| Features  | Used for                                                                                                                                                                                                                                                                                                                       |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Proxy     | The Burp Proxy allows us to intercept and modify requests/responses when interacting with web applications.                                                                                                                                                                                                                    |
| Repeater  | allows us to capture, modify, then resend the same request numerous times. This feature can be absolutely invaluable, especially when we need to craft a payload through trial and error (e.g. in an SQL i -- **S**tructured **Q**uery **L**anguage **I**njection) or when testing the functionality of an endpoint for flaws. |
| Intruder  | allows us to spray an endpoint with requests. This is often used for brute force attacks or to fuzz endpoints.                                                                                                                                                                                                                 |
| Decoder   | Decoder still provides a valuable service when transforming data either in terms of decoding captured information, or encoding a payload prior to sending it to the target                                                                                                                                                     |
| Compare   | allows us to compare two pieces of data at either word or byte level.                                                                                                                                                                                                                                                          |
| Sequencer | We usually use Sequencer when assessing the randomness of tokens such as session cookie values or other supposedly random generated data                                                                                                                                                                                       |

## Navigating and configuring Burp Suite

- let's start the Burp Suite open terminal and typing this command

      burpsuite

**If** you get these issue

![burp1](/img/burp1.png)

click in `OK`.

Navigating around the Burp Suite GUI by default is done entirely using the top menu bars:

![b-1](/img/b-1.png)

In addition to the menu bar, Burp Suite also has keyboard shortcuts that allow quick navigation to key tabs. By default, these are:

| **Shortcut**       | **Does**                   |
| ------------------ | -------------------------- |
| `Ctrl + Shift + D` | Switch to the Dashboard    |
| `Ctrl + Shift + T` | Switch to the Target tab   |
| `Ctrl + Shift + P` | Switch to the Proxy tab    |
| `Ctrl + Shift + I` | Switch to the Intruder tab |
| `Ctrl + Shift + R` | Switch to the Repeater tab |

### User options tab

The options provided in the User options tab will apply every time we open Burp Suite. In contrast, the Project options will only apply to the _current_ project. Given that we can't save projects in Burp Community, this means that our project options will reset every time we close Burp.

![b-2 here](/img/b-2.png)

> The settings here apply globally (i.e. they control the Burp Suite application -- not just the project). That said, many of them can be overwritten in the project settings.

There are four main subsections of the User options tab:

- The options in the **Connections** sub-tab allow us to control how Burp makes connections to targets. For example, we can set a proxy for Burp Suite to connect through; this is very useful if we want to use Burp Suite through a network pivot.

- The **TLS** sub-tab allows us to enable and disable various TLS (**T**ransport **L**ayer **S**ecurity) options, as well as giving us a place to upload client certificates should a web app require us to use one for connections.

- An essential set of options: **Display** allows us to change how Burp Suite looks. The options here include things like changing the font and scale, as well as setting the theme for the framework (e.g. dark mode) and configuring various options to do with the rendering engine in Repeater (we will toke about this later).

- The Misc sub-tab contains a wide variety of settings, including the keybinding table (Hotkeys), which allowing us to view and alter the keyboard shortcuts used by Burp Suite. Familiarizing yourself with these settings would be advisable, as using the key binds can speed up your workflow massively.

### Project options tab

There are five sub-tabs here:

- **Connections** holds many of the same options as the equivalent section of the User options tab: these can be used to override the application-wide settings.

- The **HTTP** sub-tab defines how Burp handles various aspects of the HTTP protocol: for example, whether it follows redirects or how to handle unusual response codes.

- **TLS** allows us to override application-wide TLS options, as well as showing us a list of public server certificates for sites that we have visited.

- The **Sessions** tab provides us with options for handling sessions. It allows us to define how Burp obtains, saves, and uses session cookies that it receives from target sites. It also allows us to define macros which we can use to automate things such as logging into web applications (giving us an instant authenticated session, assuming we have valid credentials).

- There are fewer options in the **Misc** sub-tab than in the equivalent tab for the "User options" section.

### Proxy and configuration

The Burp Proxy is the most fundamental (and most important!) of the tools available in Burp Suite. It allows us to capture requests and responses between ourselves and our target. These can then be manipulated or sent to other tools for further processing before being allowed to continue to their destination.

![burp5](/img/burp5.png)

![burp6](/img/burp6.png)

![burp7](/img/burp7.png)

- know start our Firefox

![burp8](/img/burp8.png)

![burp9](/img/burp9.png)

make sure to select `Manual proxy configuration` and write these sitting
in **HTTP Proxy:** `127.0.0.1` **PORT:** `8080` and click in **Also use this proxy for FTP and HTTPS**

![burp10](/img/burp10.png)

Now when we visit any website called http we can get information in our burp but when we visit websites called https like facebook we will get issue secure, because the burp certificate it's not in our browser we need to add it by following this steps
A. Go to `http://burp`

![burp11](/img/burp11.png)

now download the certificate and go again in Firefox setting go to **Privacy & Security** scroll down tell we get option called **Certificates** click in `view certificate` and import the file we downloaded it and select it `cacert.der` then you will see the popup

![burp12](/img/burp12.png)

### Burp Intercept

The Intercept tab is used to display and modify HTTP and WebSocket messages that pass between your browser and web servers. The ability to monitor, intercept and modify all messages is a core part of Burp's user-driven workflow.

#### Controls

| Name                       | For what                                                                                                                                                 |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Forward**                | When you have reviewed and (if required) edited the message, click "Forward" to send the message on to the server or browser                             |
| **Drop**                   | Use this to abandon the message so that it is not forwarded.                                                                                             |
| **Interception is on/off** | This button is used to toggle all interception on and off.                                                                                               |
| **Action**                 | This shows a menu of available actions that can be performed on the currently displayed message.                                                         |
| **Comment field**          | This lets you add a comment to interesting items, to easily identify them later.                                                                         |
| **Highlight**              | his lets you apply a colored highlight to interesting items. As with comments, highlights will appear in the Proxy history and on intercepted responses. |
