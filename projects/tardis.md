---
layout: project
title: TARDIS
permalink: /projects/tardis/
language: Go
platform: cross-platform
github: https://github.com/DoppioRistretto/tardis
---

**Tar Dis and Untar Dat.** A command-line utility for quickly archiving and extracting files and directories. Built for incident response workflows where you need to package triage evidence or eradicate suspicious files fast, without fighting tar flags.

---

### Features

- Cross-platform — Windows, macOS, and Linux
- Archive one file, multiple files, or entire directories in a single command
- Optional deletion of source files/directories after a successful archive
- Recursive archive extraction
- Compression with gzip; decompression of gzip and bzip2 archives
- Delete protection for `/` and `C:\` — won't let you nuke the root

---

### Usage

#### Create an archive

Append `.gz`, `.tgz`, or `.gzip` to the archive name to enable gzip compression.

Archive a single file or directory:
```
tardis create -a <archive.tar> -p <path>
```

Archive multiple paths:
```
tardis create -a <archive.tar> -p <file> -p <directory>
```

Archive and delete source files on success:
```
tardis create -a <archive.tar> -p <file> -p <directory> --delete
```

#### Extract an archive

Extension detection is automatic — `.tar`, `.tar.gz` / `.tgz`, and `.tar.bz2` / `.tbz2` are all supported:
```
tardis extract -f <archive.tar> -d <destination-directory>
```

#### Verbose output

Add `-v` to any command for verbose output:
```
tardis create -v -a <archive.tar> -p <path>
```

---

### Build from Source

Requires [Go](https://go.dev/dl/) 1.24+.

```
git clone https://github.com/DoppioRistretto/tardis.git
cd tardis
go build -o tardis
```
