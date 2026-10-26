---
title: Uptime Kuma
type: tool
sources:
  - 26-10-26-1125-uptime-kuma @ README
  - 26-10-26-1125-uptime-kuma-releases @ releases
updated: 2026-10-26T11:31:09+09:00
status: draft
tool_version: 2.5.7
---
Uptime Kuma is a self-hosted monitoring tool with a web dashboard that checks whether services are up and sends alerts when they are not.

## What it does
The README lists these monitor types: HTTP(s), TCP, HTTP(s) keyword, HTTP(s) JSON query, websocket, ping, DNS record, push, Steam game server and Docker containers. Alerts go out through notification services such as Telegram, Discord, Gotify, Slack, Pushover and email (SMTP). It runs from a Docker image or from a Node.js install kept running with pm2. The licence is MIT. For a service that has a network port, a TCP or HTTP(s) monitor shows that the service answers, while a ping monitor only shows that the host answers (unsourced; own reasoning). In practice a monitor stays unalerted until a notification channel is attached to it, and the tool cannot alert when it or its own host is down (unsourced; general experience). See [[uptime-kuma-ping-in-unprivileged-lxc]] for a known ping problem.

## Limits
Version taken from the GitHub releases page on 2026-10-26: the highest 2.5 tag listed was 2.5.7. This page covers the repository README only, not the wiki or the docs pages.

## Disagreements
None found.
