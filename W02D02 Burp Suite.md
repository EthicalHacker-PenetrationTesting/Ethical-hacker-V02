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

To configuration your Burepsuite follow these steps:

1. let's start to configure **proxy** for our Firefox

- First open terminal and start our burepsuite, we can do that by typing this command

      burpsuite

**If** you get these issue

![burp1](/img/burp1.png)

click in `OK`, then do these steps

![burp2](/img/burp2.png)

![burp3](/img/burp3.png)

![burp4](/img/burp4.png)

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

Now if you check again, you can visit the websites with https, you can visit Facebook
