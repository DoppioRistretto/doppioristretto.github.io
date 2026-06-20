---
layout: single
title: Projects
---

### [TARDIS](./tardis)

_Tar Dis and Untar Dat_ &mdash; Go &middot; cross-platform

A Go utility for quickly archiving and unarchiving files and directories during incident response. Supports multiple compression algorithms and optional deletion of source files, designed to expedite triage file collection and eradication of suspicious files.

_Velociraptor artifact coming soon._

---

### Velociraptor Artifacts

#### [Docker.Image.Export](https://docs.velociraptor.app/exchange/artifacts/pages/docker.image.export/)

Uses the Docker UNIX socket to export a Docker image to a temporary file and upload it to Velociraptor. Useful for capturing container state during forensic triage.

#### [MacOS.ParallelsVM.SuspendedMemory](https://docs.velociraptor.app/exchange/artifacts/pages/macos.parallelsvm.suspendedmemory/)

Locates suspended Parallels VMs owned by any user on a macOS system and optionally uploads the virtual memory files to Velociraptor for analysis.
