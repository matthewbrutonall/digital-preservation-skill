# Digital Preservation Quick Reference

## Storage Rule
**3-2-1**: 3 copies · 2 different technologies · 1 offsite (different disaster profile)  
Never rely on one vendor. Review storage every **3-5 years**.

## Checksum Algorithm Decision
| Use case | Algorithm |
|----------|-----------|
| Detecting corruption/loss | MD5 (fast, sufficient) |
| Higher-assurance integrity / malicious change concern | SHA-256 |
| Legacy interoperability | MD5 or SHA-1 |

## Checksum Commands
```bash
md5sum file.ext
sha256sum file.ext
sha256sum -c manifest-sha256.txt
certutil -hashfile C:\path\to\file.ext SHA256
```

## Useful AV Commands
```bash
# Get technical metadata
ffprobe -v quiet -show_format -show_streams input.mp4

# Convert to preservation format (example)
ffmpeg -i input.mov -c:v ffv1 -level 3 -g 1 -c:a pcm_s16le output.mkv
```

## File Format Risk Hierarchy
1. Open specification, well-supported (TIFF, PDF/A, FLAC, CSV) - **prefer**
2. Proprietary but open spec (DOCX, XLSX) - **acceptable**
3. Proprietary, closed spec (old DOC, camera RAW, PSD) - **avoid / watch / migrate**

Lossless for archival masters. Lossy only for access and delivery copies.

## Ingest Minimum Checklist
- [ ] Virus check before transfer/use
- [ ] Generate or verify checksums on receipt
- [ ] Run DROID characterisation
- [ ] Save DROID output and checksum manifest
- [ ] Create or update DAR record
- [ ] Record rights, restrictions, and sensitive data issues
- [ ] Integrity check after move to storage
- [ ] Record storage location and review date

## Depositor Guidance - Minimum Ask
- [ ] Keep original filenames and folder structure
- [ ] Provide a content list and basic context
- [ ] Flag passwords, encryption, and specialist software
- [ ] State rights, confidentiality, and closure issues
- [ ] Provide checksums or use bagging if possible

## DROID Identification Methods (reliability order)
1. **Container** - opens file, checks embedded signatures
2. **Signature** - matches byte sequence in header
3. **Extension** - filename only; can be spoofed

## Metadata Documents - Two Essentials
| Document | Level | Contains |
|----------|-------|----------|
| Verifiable File Manifest | File | Filename + path + checksum [+ optional format ID] |
| Digital Asset Register (DAR) | Collection | Identifier, owner, formats, risks, rights, storage, value |

## DAR - Minimum Fields
- Identifier / accession number
- Title or collection name
- Depositor / creator
- Responsible owner
- Size and file count
- Storage location
- Formats present
- Rights / access restrictions
- Key risks / dependencies
- Last review date

## Models at a Glance
| Model | Use for |
|-------|---------|
| DPM 3-Legged Stool | Explaining organisation + technology + resources |
| DPC RAM | Benchmarking and planning across 11 capability areas |
| NDSA Levels | Quick storage/fixity/security check; IT conversations |
| OAIS | Shared conceptual language with IT/vendors |

## DPC RAM - 11 Areas
1. Organisational Viability
2. Policy and Strategy
3. Legal Basis
4. IT Capacity
5. Continuous Improvement
6. Community Watch
7. Acquisition, Transfer and Ingest
8. Bitstream Preservation
9. Content Preservation
10. Metadata
11. Discovery and Access

## Standards Stack
- **PREMIS** - preservation metadata, events, rights
- **METS** - structural wrapper
- **BagIt** - packages files + manifest
- **PRONOM** - format registry

## Access Models (simple -> complex)
1. Copy and forget
2. Informed download
3. Viewer-friendly / open-format delivery
4. Provide viewer or access workstation
5. Provide reuse tools

## Access Red Flags
- Personal or sensitive data
- Unclear copyright / IPR
- Obscure file formats or dependencies
- Accessibility barriers
- No user guidance

## Anti-Patterns
- "Just keep everything" -> appraise and select
- "A repository system solves it" -> tools are not a whole programme
- "Digitisation = preservation" -> digitised files still need DP
- "Best practice" -> aim for good practice
- "IT will sort it" -> DP needs archival, records, legal, and IT input
