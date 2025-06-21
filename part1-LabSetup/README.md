# The Lab Setup Overview

This lab is done on VMWare on a Windows 11 host. The below are the machines.

1. Kali Linux (The attacker)
2. Windows Server (Active Directory)
3. Windows 10 Client PC
4. Windows 11 Client PC
5. Ubuntu Server that runs OSWAP Juice Shop on Docker

The idea is to leave Kali Linux out as the attacker while using Active Directory to centralize and control other machines. In this scenerio, I assumed that the attacker got side the internal network through a VPN.

The reason that I use both Windows 10 and Windows 11 as clients is because I want to simulate the system where it is near the EoL of Windows 10 so the corporate starting to upgrade their PCs to Windows 11, but sometimes, there are some legacy software that does not support the newest update. While it is possible that some companies may still keep their legacy Windows such as Windows 7 or Windows XP, I will focus on just Windows 10 because it is widely used while it is in the transitioning phase to upgrade to Windows 11.

Note that in the video reference by The Cyber Mentor, he used 2 Windows 10 Client PCs, but I use 1 Windows 10 and 1 Windows 11 instead. Also, in my lab I added Ubuntu Server into the mix when the video did not feature it.

The OSWARP Juice Shop is a website for ethical hacking practice. I added it to my Ubuntu Server so I don't have to build a website from scratch. In addition to that, I can also use it to practice my ethical hacking after I am done with the setup without having to setup another lab separately.
