# 🦉 OCTF

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
