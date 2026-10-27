---
title: Uptime Kuma ping monitors in an unprivileged LXC container
type: synthesis
sources:
  - 26-10-26-1125-proxmox-lxc-unprivileged-ping @ thread
  - 26-10-26-1125-uptime-kuma @ README
updated: 2026-10-26T11:31:09+09:00
status: draft
tier: core
---
Ping monitors in [[uptime-kuma]] can stay pending or red inside an unprivileged LXC container even though the targets are reachable. This page records the cause and the fixes seen on one host (unsourced; own test, one host).

## Symptom
Monitors show pending, and the service log shows a permission error on opening a socket and a missing raw-network capability (unsourced; own test, one host). The same ping run by root, or by hand, succeeds.

## Cause
A forum thread reports the same error for a normal user in an unprivileged container, with root unaffected (src: 26-10-26-1125-proxmox-lxc-unprivileged-ping @ thread). The thread is about Proxmox VE 5.1 and Debian Stretch, predates Kuma 2 and never mentions Kuma (src: 26-10-26-1125-proxmox-lxc-unprivileged-ping @ thread). On the one host tested on 2026-10-26, Kuma ran as a non-root service user, and the container's allowed group range for unprivileged ping sockets excluded that user (unsourced; own test, one host).

## Fixes seen
- **File capability on the ping binary:** the thread discusses granting the raw-network capability to ping. On the tested host this did not help, because the systemd unit set no-new-privileges, which makes the kernel ignore file capabilities at launch. The grant would also be lost when the ping package is upgraded (unsourced; own test and package behaviour).
- **Kernel setting for ping sockets (kept):** setting the container's ping group range so it includes the service user's group, in a sysctl drop-in file, then restarting the service. Ping then uses unprivileged sockets, needs no capability, and leaves no-new-privileges on (unsourced; own test, one host).

## Other things that also turn monitors red
- A per-container firewall that allows outbound traffic to a short list of addresses needs a rule for each new monitored address (unsourced; own test).
- The monitored host's firewall must accept ICMP from the monitor (unsourced; own test).

## Disagreements
None found.
