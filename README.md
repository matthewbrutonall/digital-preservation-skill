# Digital Preservation Skill

![Digital records being checked, stored in multiple copies, and prepared for access](assets/digital-preservation-skill.png)

Digital files need continuing care if people are to open and understand them years from now. This **agent skill** helps an assistant give practical digital preservation guidance, from receiving files through checking, storing, documenting, and making them accessible.

For example, if a donor offers a hard drive, you can ask the agent how to receive it safely. It can help you plan what to record about the transfer, how to check for malware, how to avoid changing the original files, and what to check before making access copies. This is guidance for a workflow; the skill does not itself run those checks or preserve the drive.

It is for archivists, records managers, museum staff, librarians, and heritage workers, including people new to digital preservation. You can ask an ordinary question and request a checklist suited to your collection and resources.

## What it helps with

- **Receiving and checking files:** plan transfers, virus checks, inventories, and checksums. A checksum is a value used to detect changes in file bytes.
- **Keeping files usable:** choose storage copies, monitor file formats, and plan migration when a format becomes hard to open.
- **Documenting decisions:** record preservation actions, responsibilities, rights, restrictions, and the information needed to understand the material.
- **Providing access:** plan access copies, accessibility, sensitive-data review, and user needs.
- **Building a programme:** develop policy, staffing, budgets, disaster plans, and records-management procedures.

The skill contains written guidance and reference files. It does not include a preservation system, scan files, make backups, or decide whether access is lawful in a particular case. Check recommendations against your institution's policy and the law that applies to your records.

## Set it up with your AI agent

Copy and paste this into your agent:

```text
Install the Digital Preservation skill from https://github.com/matthewbrutonall/digital-preservation-skill using your agent's supported skill installation method. Use the packaged skill or keep the complete `digital-preservation` directory, including its reference files, together. Confirm the skill is available and tell me how to invoke it. Do not inspect my records yet.
```

Once installed, you might ask: “We have received 200 photographs on a USB drive. Give me a first-week intake checklist and say which decisions need an archivist.”

## Professional topics in the guide

- **Frameworks and models** — DPC RAM, OAIS, NDSA Levels, DPM 3-Legged Stool
- **Bitstream preservation** — integrity checking, fixity, checksums, storage planning, 3-2-1 rule
- **File formats** — format risk, preferred formats by content type, migration vs emulation, born-digital vs digitised
- **Ingest workflows** — workstation setup, write blockers, virus checking, characterisation, DROID/Siegfried
- **Metadata** — PREMIS, METS, BagIt, verifiable file manifests, Digital Asset Registers
- **Select and transfer** — depositor guidance, appraisal, selection
- **Storage** — hard disk, tape, cloud, refresh cycles, disaster planning
- **Access** — user needs, accessibility, IPR, sensitive data, access copies, access workstations
- **Web archiving** — WARC, crawl tools, replay, workflow
- **Records management** — retention schedules, disposal, legal holds, appraisal, vital records
- **Tools reference** — characterisation, integrity, copying, disk imaging, validation, email preservation
- **Glossary** — key terms defined

Includes jurisdiction notes for UK, Ireland, USA, Australia, and EU.

## Installation files

The packaged [`digital-preservation.skill`](digital-preservation.skill) file and the complete `digital-preservation/` directory are both provided. Use your agent's supported skill installation method and keep the reference files together.

## Usage

Once installed, ask your agent about digital preservation topics. For example:

- *"How do I set up an ingest workstation?"*
- *"What checksum algorithm should I use?"*
- *"What formats should I use for scanned images?"*
- *"How do I write a retention schedule?"*
- *"What is OAIS?"*
- *"How do I start a web archiving programme?"*

## Skill Structure

```
digital-preservation/
├── SKILL.md                        # Core frameworks and topic index
├── cheatsheet.md                   # One-page quick reference
└── references/
    ├── workflows.md                # Four-workflow steps (Select & Transfer, Ingest, Preserve, Access)
    ├── file-formats.md             # Format risk, preferred formats, migration, emulation
    ├── access.md                   # Access provision in depth
    ├── web-archiving.md            # Web archiving: WARC, tools, workflow
    ├── records-management.md       # Retention, disposal, legal holds, appraisal
    ├── tools.md                    # Tools reference by function
    └── glossary.md                 # Key term definitions
```

## Audience

Designed for anyone responsible for digital preservation who is not necessarily a technical specialist — archivists, records managers, museum curators, local studies librarians, heritage staff. Covers both the "why" and the "how", with practical checklists and decision frameworks throughout.

## Standards Covered

OAIS (ISO 14721), PREMIS, METS, BagIt, DPC RAM v2.0, NDSA Levels of Digital Preservation, DLF Levels of Born-Digital Access, ISO 15489 (Records Management), WARC (ISO 28500), PRONOM, and more.

## Reviews

Independent reviews from other archivists, practitioners, and AI researchers are very welcome — please open an issue or pull request.

## Licence

[MIT](LICENSE)

## Author

[Matthew Bruton](https://github.com/matthewbrutonall) — contract archivist and digital preservation practitioner.
