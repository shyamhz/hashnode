---
title: "TCP Working: 3-Way Handshake & Reliable Communication"
datePublished: Fri Jan 30 2026 15:08:21 GMT+0000 (Coordinated Universal Time)
cuid: cml10pmpb001i02ky4zsu6i26
slug: tcp-working-3-way-handshake
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769785079592/df5c809a-8b04-471a-995f-2cbe59490eee.png
tags: tcp, chaiaurcode, chaicode, chaicohort, tcp-handshake, tcp-3-way-handshake, chaicode-webdev-cohort-2026, tcp-working-3-way-handshake-and-reliable-communication

---

In [previous blog](https://blog.shyamhz.dev/tcp-vs-udp) we learnt about TCP and UDP protocols and how they relate to HTTP protocol. Today in this blog we are going to learn in details about TCP and how it ensures all the promises like accuracy, order, integrity are kept.  
As usual with simple and beginner friendly language let’s understand how a TCP communication is reliable, accurate and safe.

## What is TCP and it’s need

TCP or Transmission Control Protocol is one of the most used Transmission protocol used acrossed the Internet. TCP ensures data sent in chunks or packets in the right order, to the correct destination in a reliable and safe manner.

TCP is needed because it solves some crucial problems, data is never send in a bulk size on the Internet, it is broken into multiple chunks with some extra meta data with it’s ordering info along with other additional data.  
These packets may get lost or disarranged on the way or there might be some repetition or may get corrupted totally, to ensure data reaches In correct order, exactly once, to the correct place and accurately TCP protocol was created.

## Three way handshake

TCP protocol performs three steps to confirm it can reliably send data to the destination while maintaining all the safety , order and accuracy.

* First the sender sends a Synchronization or SYN message to the receiver.
    
* Then if the receiver got the SYN message it sends a Synchronization Acknowledgement or SYN-ACK back to the sender.
    
* And when the sender receives a SYN-ACK it returns a final Acknowledgement signal ACK to the receiver.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769785137720/3c9ae660-f3a5-42aa-8eb5-6a907d1a4aff.png align="center")

This is what essentially known as the three-way-handshake because total of three transmission happens between the sender and the receiver before the actual transmission even starts.

## Actual data transfer

Once the handshake is done finally the actual data transfer starts. Each data packet or chunk carries some additional meta data about it’s order and sequence. If receiver misses a packet or a packet it lost on the way receiver just asks the sender to send it again.

For each packet receiver sends acknowledgement to the sender so no repetition happens. And all the data is rearrange in proper order with help of the meta data.

## Closing a TCP connection

When data transfer is done the sender sends a `FIN` signal to the receiver telling it that “I am done sending data”. Then the receiver replies wit `ACK` for the senders `FIN` and sends it own `FIN` . After receiving sender’s `FIN` client sends back it’s `ACK` and that is how a TCP connection is terminated.

## Conclusion

TCP is the most safest and powerful transmission or transport protocol in terms of safety, reliability, integrity. And all of it’s magic lies in it’s `three-way-handshake` and a graceful termination of the connection.

So hopefully you now understand how TCP works behind the scenes to maintain a reliable and safe and accurate data transmission.