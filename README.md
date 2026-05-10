# Active Directory Home Lab

A structured home lab for learning and documenting Active Directory penetration testing techniques. Built across progressive parts — lab environment setup first, then offensive attack chain practice.

The lab environment mirrors the enterprise Active Directory infrastructure I encountered professionally at the Synchrotron Light Research Institute, where I supported Windows endpoint deployment and domain join operations. Building this lab from scratch as the administrator deepened that hands-on familiarity from both sides of the environment.

For the offensive techniques, this lab follows TCM Security's AD penetration testing curriculum loosely as a structured foundation, with personal variations in configuration.
Reference video: [AD Pentest by The Cyber Mentor](https://youtu.be/VXxH4n684HE?si=feCTe7oTs0s6NbSZ)

---

## Lab Structure

| Part | Folder | Status |
| --- | --- | --- |
| Part 1 — Lab Setup | `part1-LabSetup` | 🔄 In Progress |
| Part 2 — Attack Chain Practice | `part2-Hacking` | 🔄 In Progress |

---

## Part 1 — Lab Setup

Covers building the full virtual AD environment from scratch using VMware and VirtualBox:

+ Windows Server configured as Active Directory Domain Controller (ADDC)
+ Domain join for Windows endpoints
+ Network configuration across VMs to simulate an enterprise environment

This setup mirrors the kind of AD environment found in real enterprise deployments — the same infrastructure SOC analysts monitor and defend.

---

## Part 2 — Attack Chain Practice *(In Progress)*

Will cover offensive techniques against the lab environment following industry-standard AD attack methodology:

+ Initial access and enumeration
+ Privilege escalation
+ Lateral movement
+ Domain compromise

Each technique will be documented with step-by-step notes and tooling used. A professional-style report will be produced at the end of the full attack chain.

---

## Disclaimer

Windows Defender is disabled in this lab environment. This follows TCM Security's teaching approach — the focus here is on core AD attack fundamentals, not AV evasion. AV evasion techniques may be covered in a future lab (ActiveDirectory-HomeLab 2 or similar).

---

## About

This is ActiveDirectory-HomeLab 1. Future labs will build on the fundamentals documented here.
