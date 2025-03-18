# AD Lab Setup

## Host Machine Info

1. **Virtualization Software:** VMWare
2. **RAM:** 16 GB
3. **OS:** Windows 11

I found that different OSes and software versions effect the performances, experiences, and compatibility so I decided to document all of this information.

I used to use VirtualBox on a Linux machine with 12 GB of RAM so this time the experience will be different.

## VMs

1. Windows 11 as client 1
2. Windows 10 as client 2
3. Windows Server 2022 as Domain Controller (DC)
4. Kali Linux as the attacker

The reason why I include Windows 11 in this lab is because Windows 10 is getting closer to its end of life. I believe that more companies will start to migrate to Windows 11. It is important that I, as an aspiring Penetration Tester takes this information into account.

We, Cybersecurity Professionals, keep advicing others to always update their systems to the latest security patch or latest version for security reason, we also responsible to keep up to date with the new techniques and new software update as well.

I, as an aspiring Penetration Tester, feel the responsible of doing so as well. While I cannot jump into the more advance topics right away, this is the step I take to ensure I am keeping up to date as well as being adventurous enough to take a step into the territory that I am not yet familiar with but still within the realm of fundamental concepts.

Learning this in a lab ensuring that I will gain some familiarity of the new setup that include Windows 11 making me less likely to mess my future clients' main system that include both Windows 10 and Windows 11 because I have gained some familiarity of them from the lab.

I follow most of the setup from the Cyber Mentor's YouTube video. In this lab, I will mainly talk about the things that I do different than his setup. Otherwise, most of the setup will be just like his.

I will also add my personal experiences such as the things that I have learned along the way.

## Kali Linux Installation

I downloaded Kali Linux VMWare image from the official Kali Linux website.

I checked the SHA256SUM hash of the downloaded image. Always check the hash because you will never know if the file is being tampered with or not without checking.

While you might think you have downloaded the image from their official website, it should be trust worthy, which I agree, however, in my personal experience, I have downloaded an iso image of a Linux distro (not Kali) from their official website and still got the hash mismatch.

As much as I trust the official website, the error can happen during the download process that is difficult to describe. It is safer to check and if the hash is mismatch, you won't have to waste your time installing it and then having to deal with a lot of annoying troubleshoots.

![Check Kali Hash](KaliSetup/Kali-SHA256SUM-Check-PS.png)

As you can see I used PowerShell to check the hash. The command is `Get-FileHash <file>`. You can drag and drop the file to the PowerShell.

***Sangsongthong***
| ***Hexterika Cyber Lab***
| ***Founder, CEO, and Sole Worker***
