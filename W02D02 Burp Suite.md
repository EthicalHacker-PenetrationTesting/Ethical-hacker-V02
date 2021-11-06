# Burp Suite

## High Level Goals

By the end of this lesson, you will be familiar with the following:

1. What Burp Suite.
2. Overview of the available tools in Burp Suite.
3. Installing Burp Suite.
4. Navigating and configuring Burp Suite.

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
