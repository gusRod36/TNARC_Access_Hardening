## Lab 2 TNARC Financial HQ: Access Hardening

Builds on [Lab 1: Three-Tier Campus](https://github.com/gusRod36/TNARC_HQ_Lab_01)

## The Problem

Before TNARC expands to new branches, an internal security review audits the HQ network. As a financial company, TNARC handles sensitive client data, so the review declared the findings unacceptable. Leadership wants every finding closed before any new site goes live.

## Audit Findings

| ID | Finding | Risk | Severity |
|----|---------|------|----------|
| F1 | Devices are managed over Telnet | Credentials are sent in clear text. Anyone capturing traffic on a user VLAN could obtain admin credentials and take control of the network. | High |
| F2 | Admins share one local password | Changes can't be traced to a person, which breaks accountability and audit trails. A departing employee keeps access until the shared password is changed everywhere. | High |
| F3 | No protection against rogue DHCP servers on user ports | A rogue server could hand clients a malicious gateway or DNS server, routing finance traffic through an attacker, or cause outages by handing out bad addresses. | High |
| F4 | No Protection against ARP spoofing on user VLANs | An attacker on the same VLAN could impersonate the default gateway and intercept or alter other users' traffic, including sessions to internal finance systems | High |
| F5 | Any device can connect into any user port | Unapproved personal or attacker devices can join internal VLANs with full access to department networks and services | Medium |
| F6 | User ports don't block spanning-tree BPDUs | A switch connected to a user port could take part in spanning-tree, possibly becoming root bridge. That could cause network-wide disruption or redirect traffic through an unauthorized device. | Medium |
| F7 | Device management is reachable from every user VLAN | Any user, or any compromised workstation, can attempt to log in to network devices. That widens the attack surface for bruteforce attacks and other exploits. | Medium |
| F8 | Passwords are stored in plain text or with reversible encryption | Anyone who sees the configuration file (a backup, a support ticket, a repository) can read device passwords directly. | Medium |
| F9 | No idle session timout or login attempt limits | unattended admin sessions stay open for anyone to use, and unlimited login attempts allow bruteforce attacks. | Low |
| F10 | No warning banner before login | Without notice that access is restricted and monitored, enforcing policy or taking action against misuse becomes difficult | Low |

## Controls Applied

| ID | Control | Applied to | Evidence |
|----|---------|------------|----------|

## Topology Changes

## Key Decisions
1. Which ports does DHCP snooping trust, and why those?

2. Port security: how many MACs per port, sticky or static, and which violation mode?

3. TACACS+ or RADIUS for device logins, and why?

4. What happens to admin access if the AAA server is unreachable?

5. Who is allowed to SSH to network devices, and how is that enforced?

6. Why does dynamic ARP inspection depend on DHCP snooping? What about devices with static IPs?

## Verification
| Test | Finding | Expected | Result |
|------|---------|----------|--------|

## Challenges and Fixes

## Limitations

## What I'd Do Next
