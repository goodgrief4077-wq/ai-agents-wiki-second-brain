---
source_kind: web
url: https://pnpm.io/settings/dependency-resolution
retrieved: 2026-10-24T13:47:30+09:00
licence_note: "unknown; settings reference summarised, nothing quoted"
archive_status: saved
archive_url: http://web.archive.org/web/20261016215243/https://pnpm.io/settings/dependency-resolution
archive_timestamp: 2026-10-16T21:52:43+00:00
body_sha256: b728d1f33bd07412a709ca4e6194f2bf8687df535223cc885cddde374d733cbd
read_via: raw
verify_by: hash
---
pnpm settings reference for dependency resolution. minimumReleaseAge sets how many minutes must pass after a version is published before pnpm installs it, for direct and transitive dependencies, with an exclude list for packages that must always resolve to the newest version. trustPolicy (added in v10.21.0, default off) set to no-downgrade makes installs fail when a package's trust evidence is weaker than an earlier-published version, for example losing trusted-publisher status. blockExoticSubdeps (added in v10.26.0, default true) lets only direct dependencies come from exotic sources such as git repositories or tarball URLs.
