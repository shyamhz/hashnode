---
title: "A Complete Guide to Different DNS Record Types"
datePublished: Fri Jan 30 2026 12:56:30 GMT+0000 (Coordinated Universal Time)
cuid: cml0w02vm000n02l22d7g8ddz
slug: dns-record-types
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769777710850/b6dbf5bd-9daa-416d-8521-7f96aff8d100.png
tags: dns-records, chaiaurcode, chaicode, chaicohort, chaicode-webdev-cohort-2026

---

As we learnt in the [previous blog](https://blog.shyamhz.dev/understanding-dns-how-domain-name-system-resolution-works) DNS is the phonebook of the Internet. Without DNS it would not be possible to find the actual address of the websites and servers. If you want to know more about what DNS is and how they are resolved read the [last blog](https://blog.shyamhz.dev/understanding-dns-how-domain-name-system-resolution-works), in this blog you will learn about different types of DNS records and why they exist. So without a due let’s jump into it.

## What are DNS records

DNS records are a list of entries that associate a Hostname to an address. Now this address can be a different hostname, an actual IPv4 or IPv6 address depending on what type of record it is. When you spin up a server somewhere you get it’s IP address you need to manually connect it to your custom Domain name via a DNS record at your Domain manager’s site (e.g. Cloudflare, Namecheap, Hostinger etc. are few of many available options).

### A record

This is the final public IP address that is resolved at the end of DNS queries usually. An `A record` is always a **IPv4 address** record. For example A record for `google.com` contains \``142.250.183.142`\`.

### AAAA record

This record also contains the actual IP address associated with the domain or the target destination server. Only difference between an `A record` and `AAAA record` is AAAA record contains IPv6 address instead of IPv4. An example of IPv6 record could be `2001:0db8:85a3:0000:0000:8a2e:0370:7334` .

### CNAME record

A CNAME records contains another domain name instead of a IP address , basically it associates one domain or subdomain with another domain or subdomain. To get the A or AAAA record for that second domain it needs to be resolved via an Authoritative NS.

If someone has their blog subdomain mapped to a blogging site like `hasnode.com` then the CNAME record for that will look like

| Type | Name | Content | TTL |
| --- | --- | --- | --- |
| CNAME | blog | hashnode.network | Auto |

here blog is the subdomain for the actual domain that is being associated with the CNAME `blog.example.com → hashnode.network` .

### MX record

MX records stands for mail exchange record. These records are responsible for routing mails to correct destination mail server according to the SMTP server. There can be multiple MX records for same mail server.

| Type | Name | Priority | Content | TTL |
| --- | --- | --- | --- | --- |
| MX | mail | 20 | [mailhost1.example.com](http://mailhost2.example.com) | Auto |
| MX | mail | 10 | [mailhost2.example.com](http://mailhost2.example.com) | Auto |

### TXT record

DNS TXT records were originally introduced to add text information to DNS. These let DNS administrators put additional information for their domains, one domain can have many TXT records. Nowadays these text record help domain owners put additional info in their domain’s DNS so it is more harder for malicious practitioners to spoof or fake sender’s domain in e-mails.

| Type | Content | TTL |
| --- | --- | --- |
| TXT | “domain=authentic” | Auto |

### NS record

NS records are used to specify a different authoritative NS for a domain different from the registrar of that domain. For example if you bought your domain from Namecheap but want to manage your Domain and it’s records on Cloudflare you can do that by putting a NS record in Namecheap that contains Nameservers of Cloudflare.

| Type | Name | Content | TTL |
| --- | --- | --- | --- |
| CNAME | sub-domain or @ for root | Actual Name Servers | Auto |

## Summary

The DNS records are bones and muscles of the who DNS. They tell DNS resolvers where to look for the domains and how to get to them. Each and every record type play a particular role in DNS resolution as mentioned above.

Hopefully now you understand what each DNS record exist and why they are needed and how they are used.