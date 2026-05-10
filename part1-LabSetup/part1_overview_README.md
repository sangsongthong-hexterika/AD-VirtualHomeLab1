# Part 1: Lab Setup Overview

This lab is done on VMWare on a Windows 11 host. The below are the machines.

1. Kali Linux (The attacker)
2. Windows Server (Active Directory)
3. Windows 10 Client PC
4. Windows 11 Client PC

The idea is to leave Kali Linux out as the attacker while using Active Directory to centralize and control other machines. In this scenerio, I assumed that the attacker got side the internal network through a VPN.

The reason that I use both Windows 10 and Windows 11 as clients is because I want to simulate the system where it is near the EoL of Windows 10 so the corporate starting to upgrade their PCs to Windows 11, but sometimes, there are some legacy software that does not support the newest update. While it is possible that some companies may still keep their legacy Windows such as Windows 7 or Windows XP, I will focus on just Windows 10 because it is widely used while it is in the transitioning phase to upgrade to Windows 11.

Note that in the video reference by The Cyber Mentor, he used 2 Windows 10 Client PCs, but I use 1 Windows 10 and 1 Windows 11 instead.

## Joining the VMs

After setting up each individual VM, there will be a separate step to join each of the clients PCs to the Active Directory Domain Controller.
