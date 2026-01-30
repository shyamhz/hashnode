---
title: "Understanding DNS: How Domain Name System Resolution Works"
seoTitle: "Understanding DNS: How Domain Name System Resolution Works"
datePublished: Fri Jan 30 2026 09:52:08 GMT+0000 (Coordinated Universal Time)
cuid: cml0peyz1000h02kwd0x85xyu
slug: domain-name-system-resolution
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769766558374/a26c70a6-e006-4cc7-b323-e6c1c6d3e189.png
tags: dns-resolver, chaiaurcode, dns-resolution, chaicohort, chaicode-webdev-cohort-2026

---

All of us are familiar with many domains like google.com, netflix.com, wikipedia.org, facebook.com etc. But none of them are real address of those sites, they are just names or if you want to say it formally then “domain names”. Each individual website that you visit are located in a server somewhere that has It’s own unique public IP address. And **Domain Name System (DNS) servers** store and resolve which domain name belongs to which IP address, simply the address of the host server. You can think DNS as the phone-book of the Internet. In this blog you are going to learn about different kind of DNS servers and how DNS queries are resolved.

DNS exists because a fundamental difference between us and the Computers , Computers are good at numbers and we are good with word or rather names. It is hard for us to remember every single IP address for all the sites we want to visit but Computers need actual address to take us to that exact server’s contents. That is why DNS resolution process takes the domain name or hostname and finally returns the server’s true IP address.

## Inspecting DNS resolution

DNS resolution is not as simple or straightforward as it sounds at start, it happens in multiple servers, multiple server to server hops are involved for each resolution request. But luckily for us we have a tool available for us that can be used to diagnose the resolution process. The tool is a command-line utility called `dig`.

With this command we can understand the DNS resolution flow easily. For that we need to understand how dig command works first.

### Starting from the Root

Every DNS resolution starts from the Root Servers that are the Root entries or top most level servers in the whole Domain Name System. Every domain contains a TLD (e.g. .com, .org, .us, .ai, .in etc) we need those TLD server’s address first and to get them we need to know how to reach Root server first.

`dig . NS` gives list of all the Root servers. `.` here represents “Root” and fetches all the Root servers.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769759159515/9e0b58f8-2cad-4048-add4-bf9183e4ab5d.png align="center")

These Root servers are starting point of every domain name lookup or DNS resolution process.

### The TLD servers

TLD servers are responsible for knowing further information related to domain with a specific TLD like .com , .org etc. These TLD Name Servers are responsible for knowing Authoritative NS (Name Server) for the domain that is being looked up for and has a specific TLD like `.com` in `google.com` . We can ask the Root servers, that which TLD servers can resolve a particular TLD e.g. `.com` .

To know the TLD NS use `dig com NS` command. This command will list the TLD servers list. This list is fetched from the Root servers that we got in previous step and store only Authoritative NS for `com` TLD domains only.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769759597901/34fdec2b-f5d5-45e2-99c2-a8aa6cc83512.png align="center")

### Authoritative Server

Our next stop in DNS resolution query is Authoritative NS. Only an Authoritative Name server can tell the actual IP address for the domain for which the whole resolution is happening, from Root NS to TLD NS to Authoritative NS all this tour was to finally reach the actual IP address of the Server.

Continuing with our `dig` example from Root name servers we got TLD NS for `.com` TLD then from those TLD servers we will go to authoritative NS for google.com.

we can use `dig google.com NS` command to finally do that.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769760218511/80671634-21f3-4fa5-b490-b0b554b13660.png align="center")

As you can see the `ns1.google.com` and other are the authoritative server for `google.com` domain that dig command fetched from us from TLD servers of `com` TLD.

### The final destination

Now that we have multiple Authoritative NS for `google.com` we can finally ask them for the actual IP address for `google.com` .

for that we do `dig @`[`ns1.google.com`](http://ns1.google.com) [`google.com`](http://google.com) `A` . This command returns the true IP address of `google.com`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769760880431/a6c65da2-5123-4902-8806-d22541e67a26.png align="center")

As you can see in the answer section the IP address for `google.com` . You can directly enter that IP `142.250.183.142` in you favorite browser’s URL bar and it will surely take you to [google.com](https://google.com).

## Summary

So you saw how we recursively resolved DNS query for `google.com` using the dig command. But browsers do not use `dig` command instead Browser uses something called Recursive DNS resolver.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769762087322/c492b0a8-a1df-48a9-9e09-3b7a29c8f4c8.png align="center")

A recursive resolver takes the target hostname and resolves the IP address of it for the browser. As you can see in the diagram each query originates and ends at the recursive resolver and the resolver itself queries each and every server in the step and finally returns the IP address. From Root NS to the final Authoritative NS it pinpoints the IP address for exact domain name it is resolving for just like we find for files in directories and sub-directories recursively.

## Conclusion

Hopefully it is clear to you now how step by step DNS is resolved behind the scenes and how Browsers fetch the actual IP address for any domain name and fetches the content of those servers.