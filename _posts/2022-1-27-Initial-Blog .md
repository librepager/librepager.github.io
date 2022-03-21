---
layout: post
title: "LibrePager Opening Blog"
subtitle: "A website opening years in the making."
date: 2022-02-26 12:00:00 -0400
background: '/img/froggy.jpg'
---

LibrePager is an idea that I have been working on for a couple of years now. Basically, it is a “pager” like the thing your dad carried in his pocket to get radio txt messages in the 1980s, only now using the magic of Lora Chirp Spread Spectrum Modulation and mesh networked transceivers, it can be a two way messaging system, that is independent of the telecoms and can be free, both as in beer and as in liberty.

Shortly after I started it occurred to me just what a huge expanse of technology this would cover. The radio frequency technologies were one huge part. The basic design of handsets and repeaters, how long they work on batteries and solar cells, their range and bandwidth, are one big area. Design of the human interface is another daunting area. The social and legal structure, including software license type, FCC compliance and limits on the uses of the devices for the mutual protection of the user community, are yet a third huge area that needs to be established for LibrePager to become a useful public standard and reach the potential of the technology.

The last two years have been interesting, for lack of a better term. On two separate occasions, I thought that I adequately surveyed the available resources and open source projects similar to my concept, and started to develop hardware and software, only to find that I had missed open source projects that were doing what I was doing, and doing it better to boot. Luckily, in the open source development arena, you don’t need to beat your competitors to market. You get to join them as a collaborator and everyone wins.

The first technology that I had missed was Meshtastic , and open source, two way text communications device that uses mesh networked transceiver for off grid communications. It is different than the LibrePager concept in that Meshtastic is intended for use between groups of people, like hikers and skiers, who will be out of cell tower range and need to keep in touch anyway. It can be stand alone, but in most designs it is a bluetooth dongle extending your smart phone. Meshtastic by default transmits your GPS coordinates to others in your group, so you can use Google Maps to see the location of all devices in meshed range. It is also intended for short term use, or possibly, for communication in the event of a disaster.

The second technology that I missed was the user interface. After thinking over available input/output designs for the LibrePager, I decided that the best interface was the touch screen, just like the interface used for SMS texting on smartphones. I found the Bodmer libraries for using touch screens and actually had my own keyboard widget 90% designed when I found the opensource LVGL library. As of this date, I have ported the LVGL Library to ESP32 dev boards, and I have written a preliminary version of a graphic user interface, like Android SMS texting software, to enter the messages and display the conversations. It uses LVGL's built-in keyboard widget and a screen I called a "conversation" to display alternating sent and received messages in balloon like objects of contrasting color.   It has the potential to be a pretty good (alpha level) User Interface for Meshtastic as a standalone device, and in the future, for LibrePager.

The need to reach out to other in the Meshtastic community to share this software and get their help in tying it into their software is why I am making this blog now. I have also discovered that I have been ploughing forward with hardware and software design for 2 years with totally inadequate documentation. Posting about development for others will create badly needed records for myself as well.

In the next post, I will get into some of the issues involved in choosing LVGL for the User Interface.

