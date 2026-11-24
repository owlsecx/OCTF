# 🦉 OCTF

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-2.0-cyan?style=flat-square"/>
</p>

> **OCTF** — CTF Swiss Knife Tool

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OCTF is a CTF Swiss-army tool that bundles the encodings, classical-cipher attacks and analysis helpers commonly needed during capture-the-flag challenges. It handles base encodings, URL/HTML, hex/string/binary conversions, JWT decoding, magic-byte identification, ROT and XOR brute force, frequency analysis and hash identification. Several operations are available non-interactively for quick one-liners.

---

## ✨ Features

- Base, URL/HTML, hex, string and binary encoding/decoding
- JWT decoding and magic-byte file identification
- ROT-N and XOR brute force
- Frequency analysis and hash-type identification
- Morse encoding and quick one-shot CLI operations
- Safe offline demo mode

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OCTF --rot "Uryyb"
./OCTF --hashid 5f4dcc3b5aa765d61d8327deb882cf99
./OCTF --morse "SOS"
./OCTF --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OCTF --help   # watch every network call
firejail --net=none ./OCTF --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
