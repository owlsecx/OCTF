# 🦉 OCTF

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux%20%2F%20Windows-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OUtils%20%2F%20CTF%20Toolkit-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/No%20Dependencies-Stdlib%20Only-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OCTF** is a CTF Swiss Knife — Base16/32/64/85/91 auto-decode, frequency analysis with IC scoring, magic byte file identification, JWT decoding, URL/HTML encoding, Hex/String/Binary conversion, ROT brute-force, hash identification, and single-byte XOR key finder.

---

## 📌 Overview

OCTF bundles the most common CTF encoding, analysis, and brute-force tasks into a single offline CLI tool. Each module exports results as JSON, TXT, or appended log. The tool is split into two sections in the menu: **Encoding & Analysis** (modules 1–6) and **Brute Force & Identification** (modules 7–9).

---

## 🖥️ Modules

### [1] Base Encodings

Encode and decode across five base standards, plus auto-decode mode.

| Option | Operation |
|--------|-----------|
| `1` | Base16 Encode / Decode |
| `2` | Base32 Encode / Decode |
| `3` | Base64 Encode / Decode |
| `4` | Base85 Encode / Decode |
| `5` | Base91 Encode / Decode |
| `6` | **Auto-Decode** — tries all 5 simultaneously and flags printable results with `[✔]` |

---

### [2] Frequency Analysis

Letter frequency table against English reference, plus Index of Coincidence scoring:

| IC Value | Interpretation |
|----------|---------------|
| > 0.06 | Monoalphabetic cipher (Caesar, Atbash) |
| 0.04–0.06 | Polyalphabetic cipher (Vigenère) |
| < 0.04 | Random / encrypted |

Displays top-15 letters with count, cipher %, English %, and colour-coded bar. Automatically suggests a Caesar shift based on the most frequent letter.

---

### [3] Magic Bytes — File Signature Detector

Identifies file types from the first bytes. Accepts a file path or a raw hex string.

| Signature | File Type | Extension |
|-----------|-----------|-----------|
| `FF D8 FF` | JPEG Image | `.jpg` |
| `89 50 4E 47` | PNG Image | `.png` |
| `47 49 46 38` | GIF Image | `.gif` |
| `25 50 44 46` | PDF Document | `.pdf` |
| `50 4B 03 04` | ZIP Archive | `.zip` |
| `1F 8B` | GZIP Archive | `.gz` |
| `42 5A 68` | BZIP2 Archive | `.bz2` |
| `52 61 72 21` | RAR Archive | `.rar` |
| `7F 45 4C 46` | ELF Executable | `.elf` |
| `4D 5A` | Windows PE/EXE | `.exe` |
| `CA FE BA BE` | Java Class File | `.class` |
| `ID3` | MP3 Audio | `.mp3` |
| `52 49 46 46` | WAV/AVI Media | `.wav` |
| `4F 67 67 53` | OGG Audio | `.ogg` |
| `66 4C 61 43` | FLAC Audio | `.flac` |
| `53 51 4C 69 74 65` | SQLite Database | `.db` |
| `2D 2D 2D 2D 2D 42 45 47 49 4E` | PEM Certificate/Key | `.pem` |
| `EF BB BF` | UTF-8 BOM Text | `.txt` |
| `3C 21 44 4F 43` | HTML Document | `.html` |
| `3C 3F 78 6D 6C` | XML Document | `.xml` |
| `42 4D` | BMP Image | `.bmp` |

---

### [4] JWT Decoder

Decodes JWT tokens into header, payload, and signature hex — without signature verification.

- All header fields displayed with algorithm highlighted
- Payload timestamp fields (`exp`, `iat`, `nbf`) converted to human-readable UTC
- `alg: none` flagged with a prominent `[⚠]` warning

---

### [5] URL / HTML

| Option | Operation |
|--------|-----------|
| `1` | URL Encode |
| `2` | URL Decode |
| `3` | HTML Encode |
| `4` | HTML Decode |
| `5` | Double URL Encode |
| `6` | **All at once** — shows all 5 transformations side by side |

---

### [6] Hex ↔ String ↔ Binary

| Option | Conversion |
|--------|-----------|
| `1` | String → Hex |
| `2` | Hex → String |
| `3` | String → Binary (8-bit per char) |
| `4` | Binary → String |
| `5` | Hex → Binary |
| `6` | Binary → Hex |
| `7` | **All formats at once** — shows Hex, Binary, Octal, and Decimal simultaneously |

---

### [7] ROT Brute Force

Tries all 25 Caesar rotations and displays each result. Automatically flags:

- Shifts where common English words (`the`, `and`, `for`, `flag`, `ctf`) appear in the output
- ROT13 with a dedicated `← ROT13` marker

---

### [8] Hash Identifier

Identifies hash type from length and prefix patterns:

**By prefix:**

| Prefix | Type |
|--------|------|
| `$2a$` / `$2b$` | bcrypt |
| `$1$` | MD5-crypt (Linux shadow) |
| `$5$` | SHA-256-crypt (Linux shadow) |
| `$6$` | SHA-512-crypt (Linux shadow) |
| `$apr1$` | Apache MD5 (.htpasswd) |
| `pbkdf2_sha256$` | Django PBKDF2 |
| `sha1$` | Django SHA-1 |

**By hex length:**

| Length | Possible Types |
|--------|---------------|
| 8 | CRC-32 |
| 32 | MD5 · NTLM · MD4 |
| 40 | SHA-1 · MySQL 4.1+ |
| 56 | SHA-224 |
| 60 | bcrypt |
| 64 | SHA-256 · Blake2s-256 |
| 96 | SHA-384 |
| 128 | SHA-512 · Whirlpool |

---

### [9] XOR Brute Force

Single-byte XOR key finder — accepts hex string or raw text input. Tries all 256 key values and ranks by printable character ratio. Top 15 candidates displayed with:

- Key value (hex + decimal)
- Printable score %
- 45-character preview
- `◀◀ FLAG/CTF DETECTED!` marker when `ctf{`, `CTF{`, `flag`, or `the` appears in output

---

## 📤 Export

After every operation:

| Option | Output |
|--------|--------|
| **[J] JSON** | `octf_<module>_YYYYMMDD_HHMMSS.json` |
| **[T] TXT** | `octf_<module>_YYYYMMDD_HHMMSS.txt` |
| **[L] Log** | Appended to `octf_log.txt` with timestamp |
| **[N] No** | Skip export |

---

## ⚙️ Requirements

- **Linux or Windows**
- **No Python installation needed** — runs as a standalone executable
- **No external dependencies** — stdlib only

---

## 🚀 Usage

```bash
./OCTF
```

---

## 🔗 Companion Tools

| Tool | Role |
|------|------|
| **OCrypt** | Modern encryption — AES, RSA, ChaCha20 |
| **OClassic** | Classical cipher encoding |
| **OSteg** | Steganography |
| **OFreq** | Advanced frequency analysis and Kasiski test |

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
