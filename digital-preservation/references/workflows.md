# UK National Archives Exemplar Workflows - Full Steps

Marked **[E]** = Essential | unmarked = optional/recommended

---

## Before Workflow 1: Depositor Preparation

This is not a formal fifth workflow, but it often determines whether transfer and ingest go smoothly.

- Ask the depositor for a content list or box/file inventory
- Ask who created the files, when, and in what system or software
- Ask for rights, sensitivity, closure, and reuse information up front
- Ask whether files have been exported, re-saved, compressed, or renamed
- Ask about passwords, encryption, unusual software, or missing dependencies
- Ask for checksums or a BagIt/Exactly package if the depositor can provide one
- Tell the depositor not to tidy the files unless agreed; original order and filenames may have evidential value

---

## Workflow 1: Select and Transfer

### 1. Set Up Equipment [E]
- Dedicated workstation if possible
- Media readers: CD/DVD, floppy (3.5" and 5 1/4"), Zip, tape, HDD caddy
- Hardware write blocker between workstation and any incoming media
- Encryption software if handling sensitive content
- A place to save transfer reports, manifests, and characterisation output

### 2. Select and Appraise [E]
- Confirm content fits collecting policy, retention schedule, or business need
- Capture IPR, access restrictions, and depositor requirements
- Ask depositor to provide a content list and contextual information
- Carry out basic appraisal if appropriate
- Assign accession number or identifier and link to DAR entry
- Create a clear folder structure on the ingest workstation

### 3. Virus Check [E]
- Scan with up-to-date AV software
- Quarantine infected content and decide whether to repair, isolate, or request a clean copy
- Ideally quarantine all content for a defined period and re-scan before proceeding
- Save AV reports as evidence of what was checked and when

### 4. Transfer [E]
- Connect media via write blocker where applicable
- Scan media with AV before transfer if possible
- Transfer using copying software that logs activity and preserves attributes
- Alternative: ask depositor to use Bagger or Exactly before transfer
- Alternative: disk image the media with FTK Imager Lite when the carrier itself has evidential value or complex structure

### 5. Checksums [E]
- If depositor provided checksums, verify them now
- If not, generate checksums and save them in a metadata or documentation folder
- Create a protected original transfer copy
- Create a working copy for the next ingest workflow

---

## Workflow 2: Ingest

### 1. Understand What You Have [E]
- Run DROID or equivalent to identify formats and create a file list
- Save output as CSV or XML alongside the transfer documentation
- Capture filename, path, size, format, version, PUID, last modified, identification method, and checksum if available

### 2. Validate Content
- Use validation software to check whether files conform to format specifications
- Flag corrupt, malformed, or potentially risky files
- Especially useful for digitised content and preservation masters
- Tools: JHOVE, VeraPDF, FITS

### 3. Analyse and Investigate
- Review DROID output for unidentified formats, encrypted files, archives, zero-byte files, and password-protected content
- Note software or hardware dependencies
- Contact depositor if clarification is needed
- Flag formats that may need migration or future watch-list monitoring

### 4. Describe [E]
- Minimum: add a high-level description in the DAR
- Optional: create fuller catalogue or accession metadata
- Record enough context for a future user or colleague to understand the material
- Save descriptions in a sustainable format such as CSV or XML where possible

### 5. Appraise
- This may happen in Workflow 1 or be revisited here
- Identify exact duplicates using checksums, not filenames alone
- Decide whether duplicates have contextual value before deleting them
- Record any appraisal decisions that affect completeness or order

### 6. Apply Access Restrictions
- Identify personal, sensitive, confidential, or otherwise restricted content
- Use depositor information, catalogue review, and analysis tools
- Record restrictions and the reason for them in metadata
- Separate preservation access from public access decisions

---

## Workflow 3: Preserve

### 1. Set Up Storage [E]
- If no dedicated preservation storage exists, use managed organisational storage as an interim step
- Plan for 3-2-1: 3 copies, 2 technologies, 1 offsite
- Use NDSA Levels of Preservation to structure the conversation
- Document who can read, write, or delete each copy

### 2. Move to Storage [E]
- Store documentation with the preserved content or in a reliably linked location
- Optional: package content with Bagger
- Use copying software that preserves timestamps and logs activity where possible
- Run an integrity check immediately after the move
- Record storage location in the DAR or CMS

### 3. Integrity Checking [E]
- Run regular checksum checks across all copies
- Investigate any mismatch before overwriting anything
- Replace damaged copies only from verified good copies
- Log actions and review logs periodically

### 4. Monitor Storage [E]
- Review storage health every 3-5 years or sooner if risk changes
- Track vendor end-of-life announcements and hardware condition
- Refresh or migrate content before storage failure becomes likely

### 5. Monitor Content
- Watch for file format obsolescence and dependency risk
- Review preferred-format lists and community guidance
- If risk rises, consider migration, emulation, or other content preservation actions

### 6. Disaster Planning
- At minimum: document where all copies are, who has access, and what the recovery sequence is
- Offsite copy is only useful if you know how and how quickly you can retrieve it — test this
- If a copy is lost or damaged: do not overwrite remaining copies; investigate first; replace from a verified good copy
- Notify IT and management immediately if a significant loss is suspected
- Review and test the disaster plan on the same cycle as storage monitoring (every 3–5 years)

---

## Workflow 4: Access

### 1. User Needs Analysis
- Identify who your users are and what they are trying to do
- Check their technical confidence, software access, and likely research methods
- Use questionnaires, interviews, help-desk patterns, or usability testing
- Use findings to decide whether simple download, guided access, or workstation access is appropriate

### 2. Accessibility
- Ensure access arrangements work for users with disabilities
- Consider WCAG, keyboard access, captions/transcripts, readable guidance, and accessible file formats
- Accessibility also includes language, confidence, and digital skills barriers

### 3. Resource Discovery
- Collection-level description is an acceptable starting point
- Online catalogue, finding aid, or portal can be added as capacity allows
- Users need to know the material exists before they can request it

### 4. User Guidance
- Explain what files are available, what software opens them, and any restrictions
- Provide plain-language guidance for download, viewing, and requesting help
- Informed download is often the most realistic early access model

### 5. Managing Sensitive Data
- Review for personal data, confidentiality, safeguarding, or other access risks
- Restrict, redact, or mediate access as needed
- Record the decision, the reason, and the review point

### 6. Managing IPR
- Confirm whether you have permission to preserve, copy, migrate, and provide access
- Deposit agreements should cover preservation actions as well as transfer
- Record rights status even when it is uncertain

### 7. Creating Access Copies
- Keep the preservation master unchanged
- Create derivative files that are easier to use and more accessible
- Prefer open, common formats for access where possible
- Label access copies clearly so users do not mistake them for the preservation master

### 8. Access Workstation Setup
- Install common, well-supported software
- Provide a safe environment that cannot alter preserved content
- Document what is installed and how users can request assistance
- This can be a practical Level 1 access offer while online delivery is still limited
