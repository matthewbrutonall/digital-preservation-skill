---
name: digital-preservation
description: >
  Expert digital preservation guidance for archivists, records managers, museums, and
  heritage staff. Use whenever the user asks about born-digital or digitised content:
  appraisal, accessioning, deposit agreements, virus checking, write blockers, disk imaging,
  checksums/fixity, file manifests, digital asset registers, DROID/Siegfried/PRONOM,
  preferred formats, format migration, emulation, OAIS, PREMIS, METS, BagIt, DPC RAM,
  NDSA Levels, SIP/AIP/DIP, storage planning, IT/vendor due diligence, email archiving,
  web archiving/WARC, sensitive data, copyright/IPR, access restrictions, user needs,
  accessibility, access copies, access workstations, digital preservation policy,
  retention schedules, legal holds, or trusted digital repositories.
---

# Digital Preservation

**Scope**: Bitstream preservation through to access — beginner to intermediate level
**Audience**: Archivists, records managers, digital preservation practitioners

---

## Core Principle

> "The series of managed activities necessary to ensure continued access to digital materials for as long as necessary." - *Digital Preservation Handbook*

Digital preservation is **proactive, ongoing, and organisational** - not a one-off technical fix. The three legs that must stand together:
- **Organisation**: policy, strategy, procedures, staffing
- **Technology**: storage, tools, repository systems, security
- **Resources**: funding, sustainability, staff skills

If any leg is short, the stool falls.

---

## Key Models

### DPM 3-Legged Stool
Five organisational maturity levels:
1. **Acknowledge** - recognise digital preservation as a local concern
2. **Act** - initiate projects
3. **Consolidate** - move from projects to programmes
4. **Institutionalize** - incorporate the broader environment
5. **Externalize** - inter-institutional collaboration

Use this to locate where an organisation stands and to advocate for resources.

### DPC RAM (Rapid Assessment Model)
Eleven capability areas for benchmarking without prescribing solutions:
1. **Organisational Viability** - leadership, staffing, sustainability, governance
2. **Policy and Strategy** - documented direction, scope, responsibilities, review cycle
3. **Legal Basis** - authority to preserve, copy, migrate, restrict, and provide access
4. **IT Capacity** - infrastructure, security, resilience, and operational support
5. **Continuous Improvement** - training, review, lessons learned, evidence of progress
6. **Community Watch** - monitoring standards, tools, formats, peer practice, and supplier risk
7. **Acquisition, Transfer and Ingest** - how content arrives, is checked, documented, and controlled
8. **Bitstream Preservation** - storage, redundancy, integrity checking, refresh, disaster planning
9. **Content Preservation** - format risk monitoring, migration, emulation, and preservation planning
10. **Metadata** - capture and maintenance of descriptive, technical, administrative, structural, and preservation metadata
11. **Discovery and Access** - how users find, understand, request, and use preserved content

Use RAM to set goals, benchmark progress, identify weak areas, and structure digital preservation planning from scratch.

### NDSA Levels of Digital Preservation
Compact, one-page model focused on storage, fixity, information security, metadata, and file formats. Good for technical conversations with IT and for showing incremental progress.

### OAIS (ISO 14721)
High-level reference model - not an implementation spec. Covers functional model, information model, and environment model. Understand it conceptually; do not try to implement OAIS verbatim as a first step.

---

## Environmental Sustainability (Green DP)

Digital preservation has an environmental cost. Storing multiple copies of high-resolution files indefinitely consumes energy and hardware resources.

**Practical "Green DP" steps:**
- **Appraise rigorously**: Do not keep what has no value. Selection is the most effective sustainability action.
- **Tiered storage**: Move less-accessed content to low-energy storage (tape or "cold" cloud tiers).
- **Format choice**: Use compressed but lossless formats (like FLAC or compressed TIFF) to reduce storage volume without losing data.
- **Review fixity frequency**: High-frequency checking of stable media consumes unnecessary energy. Match frequency to risk.
- **Advocate for green IT**: Prefer vendors and data centres with high renewable energy usage and efficient cooling.

---

## Bitstream vs Content Preservation

| | Bitstream Preservation | Content Preservation |
|---|---|---|
| Goal | Keep the bits intact | Keep meaning/functionality accessible |
| Risks | Media failure, bit rot, disaster, human error | Format obsolescence, software dependency |
| Actions | Multiple copies, integrity checks, storage refresh | Technology watch, migration, emulation |
| Scope | Foundation practice | Advanced / ongoing |

**Start with bitstream.** You cannot do content preservation if you have lost the bits.

---

## The Four Workflows

Read `references/workflows.md` for full step-by-step detail on each.

### 1. Select and Transfer
Set up equipment -> Select & appraise -> Virus check -> Transfer -> Checksums

### 2. Ingest
Understand what you have (DROID) -> Validate content -> Analyse & investigate -> Describe -> Appraise -> Apply access restrictions

### 3. Preserve
Set up storage -> Move to storage -> Integrity checking -> Monitor storage -> Monitor content

### 4. Access
User needs analysis -> Accessibility -> Resource discovery -> User guidance -> Sensitive data -> IPR -> Access copies -> Access workstation

Each workflow has **essential** steps (must do) and optional steps (do when capacity allows). The essential ones give you a minimum viable preservation programme.

---

## File Format Risk

**Risks to manage:**
- Obsolescence (formats/software phased out)
- Lossy vs lossless compression - use lossless for archival masters
- Proliferation - many formats for the same content type
- Closed/proprietary specifications - harder to validate or reverse-engineer

**Preferred format selection process:**
1. Audit what you already have and expect to receive
2. Check what similar organisations use and share lists where possible
3. Consult IT on system compatibility, storage impact, and support burden
4. Draft list with "preferred" and "acceptable" tiers
5. Review periodically - technology changes

**Format openness hierarchy (best to worst for preservation):**
- Open source / open specification (TIFF, WAV, FLAC, PDF/A, CSV)
- Proprietary but openly documented (DOCX, XLSX)
- Proprietary and closed (old DOC, camera RAW, PSD)

---

## Integrity Checking (Fixity)

A checksum is a near-unique string that acts as a digital fingerprint. Any change to the file changes the checksum completely.

**When to check:**
- On receipt from depositor
- After transfer between media or storage locations
- On a regular schedule as part of monitoring
- Before and after any preservation action

**Algorithm choice:**
- **MD5** - fast, sufficient for detecting corruption/loss
- **SHA-1** - intermediate; still seen in legacy workflows
- **SHA-256** - stronger; use when detecting malicious change or for higher-assurance workflows

**The three-copy recovery process:**
1. Keep 3 copies on 3 different storage instances and ideally 2 technologies
2. Run periodic integrity checks across all copies
3. If one checksum diverges -> investigate -> discard damaged copy -> replace from good copy

### Command-Line Checksum Examples

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

Record the output in a manifest and keep that manifest with the transfer metadata.

---

## Metadata

Five types needed for digital preservation:
- **Administrative** - rights, access conditions, provenance
- **Technical** - file format, size, checksum, encoding
- **Descriptive** - content description (ISAD(G), Dublin Core, MARC)
- **Preservation** - actions taken, migration history, validation outcomes
- **Structural** - relationships between files

**Start lean.** A minimum metadata approach is better than a complex schema you cannot sustain.

### Key Standards
- **PREMIS** - preservation metadata, events, agents, rights
- **METS** - structural metadata wrapper (XML-based; often wraps PREMIS)
- **BagIt** - packages files plus a manifest into a bag; tool: Bagger

### Two Essential Metadata Documents
1. **Verifiable File Manifest** - file-level list of filename, path, checksum, and optional identification output. This is the minimum viable fixity record.
2. **Digital Asset Register (DAR)** - collection-level record used to manage risk, ownership, value, and preservation responsibility.

### Digital Asset Register (DAR)

The DAR is a management tool, not just a catalogue. It helps you answer "what do we hold, why does it matter, what risks does it carry, and who is responsible for it?"

**Minimum useful DAR fields:**
- Collection or accession title
- Unique identifier / accession number
- Creator or depositor
- Responsible team or owner
- Date range
- Size and number of files
- Storage location(s)
- Formats present
- Rights / IPR position
- Access restrictions and sensitive data risks
- Retention or collecting decision
- Software or hardware dependencies
- Preservation priority / business value
- Key risks and required actions
- Date last reviewed

Use the DAR to prioritise work, support business cases, brief IT, and show where unmanaged risk is building up.

---

## DROID and Characterisation

**DROID** (UK National Archives) is a free tool for automated batch file format identification (characterisation). It uses the PRONOM registry.

Three identification methods (best to least reliable):
1. **Container** - opens the file and checks embedded signatures
2. **Signature** - matches byte sequences against PRONOM
3. **Extension** - least reliable; can be spoofed

DROID can output: filename, size, last modified, path, format name, version, PUID, checksum, identification method, and status.

**Other characterisation tools:** Apache Tika, ExifTool, FITS, JHOVE, Siegfried

Use characterisation to answer:
- What file formats do we actually have?
- Which files are unidentified or low-confidence?
- Which formats appear on a preferred-format or risk watchlist?
- What metadata can we reuse in manifests, registers, or catalogue records?

---

## Ingest Workstation Setup

**Hardware:**
- Highest-spec PC available
- External media readers: CD/DVD, floppy (3.5" and 5 1/4"), Zip, tape, HDD caddy
- Write blockers (hardware preferred; placed between workstation and source media)

**Minimum software stack:**

| Purpose | Options |
|---------|---------|
| Copying | Teracopy, DataAccessioner, robocopy |
| Virus checking | ClamAV, organisational AV |
| Integrity checking | Fixity, Checksum by Corz, DROID plus CSV review |
| Characterisation | DROID, FITS, Apache Tika |

**Intermediate additions:** FTK Imager Lite, VeraCrypt, CSV Validator, VLC

**Advanced:** Bagger, JHOVE, VeraPDF, ePADD, migration tools, repository system

---

## Depositor Guidance

Good transfer starts before media arrives. Give depositors simple instructions:
- Do not rename, reorganise, or de-duplicate files unless agreed
- Keep original folder structures where possible
- Supply a content list and basic context: who created the material, when, and why
- Flag passwords, encryption, unusual software, and any known restrictions
- Separate transfer metadata from the content itself if possible
- Provide checksums or use a packaging tool such as Exactly or Bagger if they can
- State any rights, privacy, confidentiality, or closure issues up front

Ask for "good enough" documentation, not perfection. The aim is to preserve context before it is lost.

---

## Storage Planning

**The 3-2-1 rule (baseline):**
- 3 copies
- 2 different storage technologies
- 1 copy offsite with a different disaster profile

**Never rely on a single vendor or technology.** Common mode failure means one event can wipe all copies.

**Storage types:**
- **Hard disk** - fast access, moderate cost, around 3-5 year lifespan
- **Magnetic tape** - lower cost, slower access, good for less-used content
- **Cloud** - convenient, but verify SLAs, extraction routes, and exit plan

**Refresh cycle:** review storage every 3-5 years and migrate before failure risk rises.

---

## Providing Access

Access is preservation's proof of success. If users cannot discover, understand, or use content, preservation has not met its purpose.

**Adrian Brown's five access models (simple to advanced):**
1. Copy and forget - provide bitstream only
2. Informed download - bitstream plus technical metadata and software guidance
3. Viewer-friendly formats - convert to PDF or other open, accessible formats
4. Provide viewer - embedded player or on-site workstation
5. Provide reuse tools - allow manipulation and reuse

**DLF Levels of Born-Digital Access** provide staged ways to build access in five areas: Accessibility, Description, Research Support, Security, and Tools. Level One is a practical starting point.

Fuller access guidance is in `references/access.md`.

### Access Good Practice Checks
- Start with user needs, not technology
- Keep the archival master separate from the access copy
- Make access copies clearly labelled derivatives
- Explain software requirements and any limits on reuse
- Build accessibility in early rather than treating it as an afterthought
- Record restrictions, redactions, and rights decisions

---

## Talking to IT

Archivists and IT colleagues often use the same words differently:
- "Archive" to IT may mean inactive storage
- "Long-term" to IT may mean 5 years; to archivists it may mean 20+ years

**Preparation steps:**
1. Choose a shared framework such as DPC RAM, NDSA Levels, or OAIS
2. Read relevant IT policies and organisational strategy
3. Know your numbers: storage volume, growth rate, access speed, integrity check frequency
4. Propose a digital preservation working group - collaborative, not adversarial

**Key questions for IT or vendors:**
- What storage copies exist and how are they monitored?
- What is the backup strategy and what does backup not cover?
- How are integrity checks logged and reviewed?
- What are the service levels and exit arrangements?
- Can we preserve metadata, folder structure, and checksums during transfer?

---

## Anti-Patterns

- **"Just keep everything"** - storage is cheap; unmanaged accumulation is not. Appraise and select.
- **"Buying a repository solves it"** - a system is one component; you still need policy, workflows, and staff.
- **"We'll digitise it and then it's safe"** - digitisation is not preservation. The digital outputs still need preserving.
- **"Best practice"** - aim for *good* practice. Good enough now beats waiting for perfect.
- **"DP is just a technical problem"** - the hardest changes are often organisational and cultural.
- **"One person can do it all"** - collaborate with IT, legal, records management, and depositors.
- **"MD5 is always enough"** - fine for corruption detection; not the whole answer for every risk.

---

## Topic Index

- **Access copies** → Providing Access, `references/access.md`
- **Access workstation** → `references/access.md`
- **Accession / accessioning** → The Four Workflows, Depositor Guidance
- **Appraisal** → The Four Workflows, `references/workflows.md`
- **BagIt / Bagger** → Metadata, `references/workflows.md`
- **Bitstream preservation** → Bitstream vs Content Preservation
- **Characterisation** → DROID and Characterisation
- **Checksums / fixity** → Integrity Checking
- **Content preservation** → Bitstream vs Content Preservation, `references/file-formats.md`
- **DAR (Digital Asset Register)** → Metadata → Digital Asset Register
- **Depositor guidance** → Depositor Guidance, `references/workflows.md`
- **DROID / Siegfried / PRONOM** → DROID and Characterisation
- **DPC RAM** → Key Models
- **File formats** → File Format Risk, `references/file-formats.md`
- **File manifests** → Metadata → Two Essential Metadata Documents
- **Ingest** → The Four Workflows, `references/workflows.md`
- **Integrity checking / fixity** → Integrity Checking
- **IPR / copyright** → `references/access.md`
- **IT collaboration** → Talking to IT
- **Metadata (PREMIS / METS)** → Metadata
- **Migration / emulation** → `references/file-formats.md`
- **Records management / retention schedules** → `references/records-management.md`
- **Retention schedules / disposal** → `references/records-management.md`
- **Legal holds** → `references/records-management.md`
- **Appraisal (records management)** → `references/records-management.md`
- **Crawl / seed / scope / replay** → `references/web-archiving.md`
- **Email preservation / email archiving** → `references/tools.md`
- **Vital records** → `references/records-management.md`
- **Records continuum model** → `references/records-management.md`
- **Web archiving / WARC** → `references/web-archiving.md`
- **NDSA Levels** → Key Models
- **OAIS** → Key Models
- **Policy and strategy** → Key Models (DPC RAM)
- **Preferred formats** → File Format Risk, `references/file-formats.md`
- **Sensitive data** → Depositor Guidance, `references/access.md`
- **Storage** → Storage Planning
- **Technology watch** → `references/file-formats.md`
- **User needs analysis** → `references/access.md`
- **Verifiable file manifest** → Metadata
- **Workflows (full step-by-step)** → `references/workflows.md`
- **Write blockers** → Ingest Workstation Setup, `references/workflows.md`

## Supporting Files

- [references/workflows.md](references/workflows.md) — full four-workflow steps with essential/optional flags
- [references/file-formats.md](references/file-formats.md) — format risk, preferred formats, content preservation, migration and emulation
- [references/access.md](references/access.md) — access provision in depth: user needs, accessibility, IPR, sensitive data, access copies, workstation setup
- [references/tools.md](references/tools.md) — tools reference by function, email and web archiving, command examples, community resources by country
- [references/web-archiving.md](references/web-archiving.md) — web archiving in depth: crawl tools, WARC, replay, workflows, rights
- [references/records-management.md](references/records-management.md) — retention schedules, disposal, legal holds, appraisal, file plans, vital records, standards
- [references/glossary.md](references/glossary.md) — concise definitions of key terms
- [cheatsheet.md](cheatsheet.md) — one-page quick reference
