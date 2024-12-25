---
title: How to Configure DNS over HTTPS (DoH) on Windows 11
date: 2024-12-23
last_modified_at: 2024-12-24
tags: dns https cybersecurity
excerpt: One of the easiest and most effective ways to protect your online activities is by using DNS over HTTPS (DoH).
---

# Introduction
By default, DNS queries and responses are sent in plaintext (via UDP), which means they can be read by networks, ISPs, or anybody able to monitor transmissions. In an era where privacy and security are paramount, one of the easiest and most effective ways to protect your online activities is by using DNS over HTTPS (DoH). This method encrypts your DNS requests, preventing third parties from eavesdropping [1, 2].

Fortunately, Windows 11 provides support for DNS over HTTPS. Here's a step-by-step guide to help you secure your DNS traffic using DNS over HTTPS (DoH). 

# What is DNS over HTTPS?

DNS over HTTPS (DoH) is a protocol that encrypts DNS queries and responses between your device and a DNS server. Unlike traditional DNS, which sends queries over an unencrypted connection, DoH encrypts these queries to ensure they can't be intercepted or manipulated by third parties. This improves privacy and security, preventing man-in-the-middle attacks and making it more difficult to track your online activities.

# Benefits of DNS over HTTPS

- **Privacy Protection**: Prevents unauthorized access to your browsing history.
- **Security**: Protects your DNS traffic from interception or alteration.
- **Bypasses DNS Censorship**: Some governments or organizations block certain websites via DNS. DoH can help bypass this censorship by encrypting DNS queries.


# Configure DNS over HTTPS on Windows 11
At this time, Windows 11 only supports a certain set of free DNS services. You can view this list by running the following command:

```bash
netsh dns show encryption
```

Below is a list of currently supported public DNS servers. It's best to choose two separate providers for primary and secondary services. 

## IPv4 Addresses

| DNS Service | Address |
|-|-|
| Google Primary | 8.8.8.8 |
| Google Secondary | 8.8.4.4 |
| Cloudflare Primary | 1.1.1.1 |
| Cloudflare Secondary | 1.0.0.1 |
| Quad9 Primary | 9.9.9.9 |
| Quad9 Secondary | 149.112.112.112 |

## IPv6 Addresses

| DNS Service | Address |
|-|-|
| Google Primary | 2001:4860:4860::8888 |
| Google Secondary | 2001:4860:4860::8844 |
| Cloudflare Primary | 2606:4700:4700::1111 |
| Cloudflare Secondary | 2606:4700:4700::1001 |
| Quad9 Primary | 2620:fe::fe |
| Quad9 Secondary | 2620:fe::fe:9 |


You can configure DNS over HTTPS via by following the steps below:

1. Right click on the Start menu and select **Settings**
2. Click on **Network & Internet** in the left sidebar
3. Select your network adapter — either **Wi-Fi** or **Ethernet**
4. Click **Hardware Properties**
5. Under **DNS Server Assignment**, click **Edit**
6. Select **Manual** DNS configuration
7. Set your preferred and alternate DNS servers for IPv4 and IPv6 
8. Under **DNS over HTTPS** make sure to enable the option for **On (automatic template)**

![Configure DNS over HTTPS part1](/assets/images/2024-12-23_dns_over_https-1.png)

![Configure DNS over HTTPS part2](/assets/images/2024-12-23_dns_over_https-2.png)

![Configure DNS over HTTPS part3](/assets/images/2024-12-23_dns_over_https-3.png)

To check if DNS over HTTPS is working properly:
1. Open a browser and visit [https://1.1.1.1/help](https://1.1.1.1/help).
2. This site will tell you if DoH is successfully configured and functioning on your system.
   
If everything is set up correctly, it should show "Yes" for DNS over HTTPS support.

## Troubleshooting

If you encounter issues, here are a few things to check:
1. **DNS Service Not Responding**: Ensure that the DNS provider you've selected supports DoH.
2. **Network Conflicts**: Temporarily disable any VPN or other network management software.
3. **Check Firewall Settings**: Make sure that your firewall allows encrypted DNS traffic.

# Conclusion

Configuring DNS over HTTPS on Windows 11 is a straightforward process that significantly improves your security and privacy online. By following the steps above, you can ensure that your DNS queries are encrypted and protected from prying eyes, enhancing your browsing experience. With the rising importance of cybersecurity and privacy, switching to DNS over HTTPS (DoH) is a small but impactful step toward securing your online activities.

# References 
[[1] Secure DNS Client over HTTPS (DoH)](https://learn.microsoft.com/en-us/windows-server/networking/dns/doh-client-support)

[[2] Cloudflare DNS over HTTPS](https://www.cloudflare.com/learning/dns/what-is-dns-over-https/)

[[3] Firefox DNS over HTTPS](https://support.mozilla.org/en-US/kb/firefox-dns-over-https)


