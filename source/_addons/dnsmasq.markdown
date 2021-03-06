---
layout: page
title: "Dnsmasq"
description: "A simple dns server with benefits."
date: 2017-04-30 13:28
sidebar: true
comments: false
sharing: true
footer: true
---

Setup and manage a [Dnsmasq](http://thekelleys.org.uk/dnsmasq/doc.html) dns server. This allow your to manipulate some dns requests. I.e. that inside your network, your homeassistant domain will resolve with a internal address.

<p class='note info'>
`interface` options are for resinos based installation. On other system you can set it to `""`, for listen on every interface.
</p>

```json
{
  "defaults": ["8.8.8.8", "8.8.4.4"],
  "forwards": [
    {"domain": "mystuff.local", "server": "192.168.1.40"}
  ],
  "hosts": [
    {"host": "home.mydomain.io", "ip": "192.168.1.10"}
  ],
  "interface": "eth1"
}
```

Configuration variables:

- **defaults** (*Required*): A list of dns server to forward default requests.
- **forwards** (*Optional*): A list of domains that will forward to a specific server.
- **hosts** (*Optional*): A list of hosts to resolve it static.
- **interface** (*Optional*): If a interface is set, it listen only on this interface. Need to set for resinos.
