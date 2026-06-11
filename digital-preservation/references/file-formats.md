# File Formats and Content Preservation

## Why File Formats Matter

Every digital file encodes its content according to a format specification. Without the correct software to interpret that encoding, the bitstream is unreadable — even if the bits are intact. File format knowledge is therefore central to both bitstream and content preservation.

---

## Format Openness — Why It Matters

| Type | Description | Preservation Risk |
|------|-------------|-------------------|
| Open / open specification | Community-developed; spec is public | Lowest — anyone can implement a reader |
| Proprietary but open | Vendor-controlled but specification published | Medium — dependent on vendor willingness |
| Proprietary and closed | Spec not published; tied to licensed software | Highest — reverse engineering needed if software discontinued |

Open formats are preferable because you can validate files against the specification, build tools independently, and are not locked to a single vendor's roadmap.

---

## Lossless vs Lossy Compression

**Lossless** — compresses without discarding any data. The original can be reconstructed exactly.
**Lossy** — discards data to reduce file size. Quality degrades irreversibly; the original cannot be recovered.

Rule of thumb: **lossless for archival masters, lossy only for access/delivery copies.**

Examples:
- Image: TIFF (lossless master) → JPEG (lossy access copy)
- Audio: WAV or FLAC (lossless master) → MP3 (lossy access)
- Video: uncompressed or lossless codec master → H.264/H.265 access

Never use a lossy access copy as the source for further migration. Always go back to the master.

---

## Common File Format Risks

### Obsolescence
Formats become obsolete when the software that renders them is discontinued or no longer supports backward compatibility. This can happen with:
- Proprietary formats tied to one vendor (e.g. early Microsoft Office formats)
- Niche scientific or instrument formats
- Early web formats and interactive content

Obsolescence is often slower than originally feared for mainstream formats. Regularly used open formats (TIFF, PDF/A, CSV, WAV) have remained stable for decades.

### Proliferation
Receiving content in many different formats for the same content type creates management and workflow complexity. Having 12 document formats in a collection is harder to manage than 2–3 preferred options.

Manage proliferation by:
- Establishing a preferred format list
- Providing depositor guidance before content arrives
- Normalising to preferred formats at ingest where practical

### Significant Properties
The properties of a digital object that must be maintained for it to remain authentic and usable. These vary by content type:
- **Text documents**: reading order, structure, layout, embedded links, formulae in spreadsheets
- **Images**: resolution, colour space, bit depth
- **Audio/video**: playback timing, synchronisation, channel configuration
- **Datasets**: column structure, encoding, null value conventions
- **Interactive/dynamic content**: functional behaviour, not just static rendering

When migrating formats, identify the significant properties first. Verify they are preserved after migration.

---

## Preferred Formats by Content Type

These represent broadly accepted good practice. Adapt to your context.

| Content Type | Preferred (archival master) | Acceptable | Avoid for long-term |
|---|---|---|---|
| Still images | TIFF (uncompressed) | JPEG 2000 (lossless), PNG | JPEG (lossy), BMP, GIF |
| Documents | PDF/A-1b or PDF/A-2b | PDF/A-3 (embeds attachments), ODT | DOC, DOCX (as master), RTF |
| Spreadsheet / tabular data | CSV, TSV | ODS, XLSX | XLS, proprietary BI formats |
| Audio | WAV (PCM), FLAC | AIFF, MP3 (320kbps as interim) | WMA, AAC, OGG (as master) |
| Video | FFV1 in MKV, uncompressed AVI | MPEG-4 (H.264) | WMV, FLV, proprietary codec masters |
| Email | MBOX, EML | PST (with migration plan) | Proprietary closed formats |
| 3D / CAD | OBJ, STL, X3D | Industry formats with open spec | Vendor-locked formats without spec |
| Web content | WARC | — | Live HTML without capture |
| Databases | SQL dump, CSV export | SQLite | Proprietary .mdb, .accdb |

Review this list periodically. PRONOM, the DPC Handbook, and the Library of Congress Recommended Formats Statement are authoritative sources for current format risk assessments.

**PDF/A variants:**
- PDF/A-1b — baseline; most widely supported; safest long-term choice for simple documents
- PDF/A-2b — adds JPEG 2000 compression, transparency, and attachments in PDF/A format
- PDF/A-3 — allows embedding any file type as an attachment; useful when you need to keep the source alongside the rendered PDF but carries higher complexity
- PDF/A-4 — latest standard (ISO 19005-4:2020); simplifies variants and supports 3D and form fields better; watch for increasing tool support

---

## Born-Digital vs Digitised Content

These require different handling at several points in the workflow.

**Born-digital content** was created in digital form and has no analogue original. The digital object is the primary record. Handle with care to preserve original file structure, metadata, and context.

**Digitised content** is a digital surrogate of an analogue original. The analogue original usually still exists. The digitised file needs to meet a defined quality standard and the relationship to the original must be documented.

Key differences in practice:

| Consideration | Born-digital | Digitised |
|---|---|---|
| Original | The file itself | Analogue item |
| Quality standard | Preserve as received | Defined at capture (resolution, bit depth, colour profile) |
| Metadata | May carry embedded technical metadata | Technical metadata recorded at scanning |
| Format | May arrive in any format; appraise and normalise | You choose the format at point of digitisation |
| Authenticity | Chain of custody from creation | Fidelity to the analogue original |
| Master file | The transferred file (write-protected) | The highest-quality scan, kept unaltered |

For digitised masters: keep the raw scan as the archival master. Do not apply enhancements, cropping, or colour correction to the master — do that only on derivatives.

---

## Building a Preferred Format List

1. **Audit your current holdings** — run DROID across all collections to see what you actually have
2. **Identify your main content types** — prioritise by volume and risk
3. **Consult similar organisations** — many have published their lists; do not start from scratch
4. **Involve IT** — they can advise on system compatibility and storage impact
5. **Draft two tiers** — "preferred" (what you want) and "acceptable" (what you can work with)
6. **Be realistic** — do not set requirements you cannot enforce or sustain
7. **Publish and share** — helps depositors and creates accountability
8. **Review on a cycle** — annually or when a significant technology change occurs

---

## Technology Watch

Technology watch is the ongoing monitoring of the technical environment to identify risks to digital content before they become critical. It covers:
- Format version changes and backward compatibility issues
- Software end-of-life or vendor discontinuation
- Hardware obsolescence (e.g. playback devices, media readers)
- Changes to standards or community guidance
- New tools or approaches that affect existing workflows

**Practical sources for technology watch:**
- DPC Technology Watch reports (dpconline.org)
- PRONOM updates (nationalarchives.gov.uk/PRONOM)
- OPF blog and community lists (openpreservation.org)
- #digipres community (Twitter/Mastodon)
- COPTR tool updates (coptr.digipres.org)

Technology watch feeds directly into preservation planning. When a risk is identified, a response is needed.

---

## Content Preservation: Migration vs Emulation

When format obsolescence risk is confirmed, there are two main responses:

### Migration
Convert digital content from one format to another to maintain access.
- **Version migration**: e.g. upgrading from an old proprietary format to a current open one
- **Format normalisation**: converting diverse incoming formats to a standard preferred format
- **Refreshing**: moving content to new storage (this is bitstream-level, not content migration)

**Risks with migration:**
- Quality loss if not handled carefully
- Significant properties may not survive
- Requires validation and quality assurance after each migration event
- Creates a version history that must be documented

**Documentation required:** what was migrated, from what format and version, to what format and version, using which tool and version, by whom, on what date, and what quality checks were applied.

### Emulation
Recreate the original software environment in which content was created, rather than converting the content itself. The original files remain unchanged; the emulator makes them accessible.

- Preserves original look, feel, and functionality better than migration in many cases
- Complex to implement and maintain
- Often necessary for interactive, dynamic, or software-dependent content (games, websites, databases)
- Growing community of practice and tooling (e.g. bwFLA, Emulation as a Service)

**When to prefer emulation over migration:**
- Significant properties depend on original behaviour that cannot be reproduced in a new format
- The content is itself about the original software environment (e.g. born-digital games, art software)
- Migration would require unacceptable quality loss

### In practice
Most organisations start with migration for common formats and use emulation selectively for complex or high-value content where migration is insufficient. The decision should be driven by a preservation plan, not ad hoc.

---

## Format Validation

Validation checks whether a file conforms to its format specification. A file can be identified correctly but still be malformed.

**Why validate:**
- Malformed files may cause rendering failures later
- Validation catches problems before they become undetectable
- For digitised content, validation confirms quality standards were met

**Validation tools:**
- **JHOVE** — AIFF, GIF, HTML, JPEG, JPEG 2000, PDF, TIFF, WAVE, XML
- **VeraPDF** — PDF/A specifically; the authoritative PDF/A validator
- **FITS** — aggregates output from multiple validation tools
- **MediaInfo** — audio and video format metadata and basic validation

Validation is not always possible for every format. Where no validator exists, document the limitation.

---

## PRONOM and Format Identification

PRONOM (nationalarchives.gov.uk/PRONOM) is the UK National Archives' technical registry for file formats. Each format has a unique PUID (PRONOM Unique Identifier).

DROID and Siegfried use PRONOM signatures to identify formats. When DROID gives you a PUID, you can look up:
- The full format name and version history
- Whether a specification is available and where
- Compression and encoding details
- Known software products that create or read it

PUIDs are stable references — use them in manifests and preservation metadata to make format records unambiguous. A filename extension is not a format identification.
