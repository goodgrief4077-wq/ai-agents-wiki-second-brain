---
source_kind: web
url: https://github.com/andrewyng/openworker/blob/main/docs/openshell.md
retrieved: 2026-10-27T10:31:00+09:00
licence_note: "MIT per the repository licence; summarised, nothing quoted"
archive_status: none
body_sha256: ab8160395395c9b94076cda6ea064d37780ca121af508fde50fe43cdf5635caf
read_via: raw
verify_by: hash
---
Documentation page in the OpenWorker repository on running an agent's shell and file tools inside an NVIDIA OpenShell sandbox. It says each agent gets one Linux container created from a pinned image, with only the session's folders mounted, an allow-listed network, and no keys or home folder inside; the agent loop, model keys and connectors stay outside. Requirements listed are Linux (or a Mac with Docker Desktop), Docker or Podman, and OpenShell 0.1.2. The page does not mention LXC or Incus. A setup command is described that asks before each change, including enabling user-session linger and bind mounts in the gateway configuration.
