# Digital Preservation Tools Reference

All tools listed are free unless noted otherwise.

---

## Characterisation / Format Identification

| Tool | Description | Notes |
|------|-------------|-------|
| **DROID** | Batch format identification; GUI; uses PRONOM | Best starting point; UK National Archives |
| **Siegfried** | Command-line DROID equivalent; fast for large batches | Good when GUI tools become slow |
| **MediaInfo** | Technical metadata for audio/video | Essential for AV analysis |
| **Apache Tika** | Extracts metadata and text from many formats | Useful for text extraction as well as metadata |
| **ExifTool** | Metadata extraction; especially strong for image and AV | Command-line |
| **FITS** | Wraps multiple tools (DROID, Tika, ExifTool etc.) | Aggregates output |
| **JHOVE** | Validation and characterisation | Good for images, PDFs, some AV |

---

## Integrity Checking / Checksums

| Tool | Description | Notes |
|------|-------------|-------|
| **Fixity** | Dedicated checksum monitoring tool | GUI; good for scheduled checking |
| **Checksum by Corz** | Checksum generation and verification | GUI |
| **HashMyFiles** | Checksum generator | Windows GUI |
| **DROID** | Generates checksums during characterisation | Multi-function |
| **md5sum / sha256sum** | Command-line checksum tools | Built into many Linux/macOS environments |
| **certutil** | Windows built-in checksum command | Useful when you cannot install extra tools |
| **Get-FileHash** | PowerShell checksum command | Windows built-in |

### Command-Line Examples

**Linux / macOS**
```bash
md5sum file.ext
sha256sum file.ext
find . -type f -print0 | xargs -0 sha256sum > manifest-sha256.txt
sha256sum -c manifest-sha256.txt
```

**Windows**
```powershell
certutil -hashfile C:\path\to\file.ext MD5
certutil -hashfile C:\path\to\file.ext SHA256
Get-FileHash C:\path\to\file.ext -Algorithm SHA256
```

---

## File Transfer / Copying

| Tool | Description | Notes |
|------|-------------|-------|
| **Teracopy** | Safe copying with verification | Popular with archivists |
| **DataAccessioner** | Transfer tool with basic metadata capture | GUI |
| **robocopy** | Windows built-in robust copy | Command-line; widely available |
| **rsync** | Robust copy for Linux/macOS | Command-line; preserves attributes |
| **Bagger** | BagIt packaging tool from Library of Congress | Creates bags with manifest |
| **Exactly** | Bagging and transfer support for depositors | No longer actively maintained; Bagger or manual BagIt is a safer choice |

### Useful Copy Commands

```bash
rsync -avh source/ destination/
robocopy C:\source D:\destination /E /COPY:DAT /R:1 /W:1
```

---

## Content Migration / Transformation

| Tool | Description | Notes |
|------|-------------|-------|
| **ffmpeg** | Swiss-army knife for audio and video conversion | Command-line; industry standard |
| **Ghostscript** | PDF manipulation and conversion | Command-line |
| **ImageMagick** | Batch image processing and conversion | Command-line |
| **LibreOffice** | Headless mode for batch document conversion | Useful for Office -> PDF/A |

---

## Disk Imaging / Forensic Transfer

| Tool | Description | Notes |
|------|-------------|-------|
| **FTK Imager Lite** | Disk imaging; preserves original carrier structure | Good GUI entry point |
| **BitCurator** | Full digital forensics environment | Linux; includes many specialist tools |
| **dd** | Unix disk imaging command | Powerful; requires care |
| **Guymager** | Forensic imaging tool | GUI option in some environments |

Use imaging when the carrier structure, deleted files, slack space, or original media context matters.

---

## Validation

| Tool | Description | Notes |
|------|-------------|-------|
| **JHOVE** | Validates AIFF, GIF, HTML, JPEG, JPEG2000, PDF, TIFF, WAVE, XML | Widely used |
| **VeraPDF** | PDF/A validation | Thorough and focused |
| **CSV Validator** | Validates CSV against schema | UK National Archives |
| **FITS** | Includes some validation output | Aggregates multiple tools |

---

## Virus Checking

| Tool | Description | Notes |
|------|-------------|-------|
| **ClamAV** | Open source; cross-platform | Command-line; ClamTk provides GUI |
| **AVG Free** | Windows/Mac AV | Free version available |
| *Organisational AV* | Existing enterprise AV | Often easiest operational option |

---

## Encryption / Sensitive Data

| Tool | Description | Notes |
|------|-------------|-------|
| **bulk_extractor** | Scans for PII (emails, credit cards, etc.) | Very fast; command-line |
| **VeraCrypt** | Strong encryption | Open source |
| **BitLocker** | Windows built-in encryption | Common in enterprise environments |

---

## Deduplication / Analysis

| Tool | Description | Notes |
|------|-------------|-------|
| **CSV Validator** | Can compare outputs for deduplication | Useful when working from DROID data |
| **TreeSize Free** | Visualise directories; find large content | Windows |
| **HxD Hex Editor** | Low-level file analysis | Advanced use |

---

## Packaging / Repository

| Tool | Description | Notes |
|------|-------------|-------|
| **Bagger** | Library of Congress BagIt GUI | Creates bags with manifest |
| **Archivematica** | Open-source digital preservation system | Integrates many tools and workflows |
| **DSpace** | Open-source repository | Research/institutional focus |
| **ePADD** | Email processing and preservation | Stanford |
| **VLC** | Media player for playback and appraisal | Free; broad format support |

---

## Email Preservation

Email is among the most at-risk and most neglected content type in digital preservation. Key considerations:

- **Preferred formats**: MBOX (open, widely supported) and EML (individual messages). Avoid PST as a preservation format — it is proprietary and fragile.
- **Context matters**: preserve threading, attachments, headers (From, To, Date, Subject, Message-ID), and folder structure where possible.
- **Volume and sensitivity**: email collections are often large, personally sensitive, and legally complex. Appraise before preserving.
- **Processing tools**: ePADD (Stanford) — ingest, appraisal, processing, and discovery of email archives. Mailbag — packages email collections into BagIt bags with structured metadata.
- **Guidance**: Library of Congress email preservation guidance; DPC Technology Watch report on email.

---

## Web Archiving

- **Capture tools**: Heritrix (Internet Archive's open-source crawler), Browsertrix (Webrecorder's browser-based crawler), ArchiveWeb.page for individual pages or logged-in sessions.
- **Preservation format**: WARC (Web ARChive) is the standard container for web captures. ISO 28500.
- **Replay**: PyWb, ReplayWeb.page, and OpenWayback for serving and replaying web archive files.
- **Key challenge**: dynamic and JavaScript-heavy sites are difficult to capture fully. Verify captures immediately after crawl.
- **Guidance**: International Internet Preservation Consortium (IIPC); Archive-It (Internet Archive subscription service for institutions without their own infrastructure).

---

## Key Registries / Community Resources

| Resource | Country / Scope | Purpose |
|----------|----------------|---------|
| **PRONOM** | UK / international | File format registry used by DROID and Siegfried |
| **COPTR** | International | Community tool registry |
| **DPC Handbook** | International | Practical digital preservation guidance (dpconline.org) |
| **DPC RAM** | International | Maturity assessment model |
| **NDSA Levels** | USA / international | Storage and preservation framework |
| **LoC Recommended Formats Statement** | USA | Library of Congress format guidance by content type |
| **NARA Guidance** | USA | US National Archives preservation guidance |
| **SAA / CoSA** | USA | Society of American Archivists; Council of State Archivists |
| **NLA / NLI / BnF** | Australia / Ireland / France | National library digital preservation guidance |

Choose tools that fit local skills and capacity. Good practice beats over-engineering.
