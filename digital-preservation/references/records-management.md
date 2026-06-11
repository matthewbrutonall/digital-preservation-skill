# Records Management and Digital Preservation

## The Relationship Between the Two

Records management and digital preservation are distinct disciplines that overlap significantly in practice. Understanding where they differ helps you avoid gaps.

| | Records Management | Digital Preservation |
|---|---|---|
| Primary concern | Controlling records through their lifecycle | Ensuring long-term access to content |
| Timeframe | Active and semi-active phases; disposal | Long-term and permanent retention |
| Key question | What do we need to keep, for how long, and why? | How do we keep it accessible over time? |
| Typical outputs | Retention schedules, disposal authorities, file plans | Preservation policies, workflows, storage plans |
| Legal driver | Accountability, compliance, FOI, data protection | Cultural heritage, evidence, research value |

Neither discipline replaces the other. Records management decisions determine what enters long-term preservation; digital preservation decisions determine whether it survives.

---

## Retention Schedules

A retention schedule (also called a records retention schedule, disposal schedule, or records control schedule) is a formal document that sets out:
- What categories of records exist
- How long each category must be kept
- What happens at the end of the retention period (destroy, transfer to archive, review)
- The legal, regulatory, or business authority for each decision

### Why retention schedules matter for digital preservation

Without a retention schedule, you cannot make principled decisions about what to preserve. Keeping everything indefinitely is not a preservation strategy — it is a storage problem that grows without bound.

A good retention schedule gives you:
- Authority to dispose of records that do not need permanent preservation
- Authority to transfer records of long-term value to the archive
- A basis for prioritising preservation effort

### Structure of a retention schedule entry

| Field | Purpose |
|-------|---------|
| Record series / function | What the records are and what business activity they relate to |
| Retention period | How long to keep from creation, closure, or last action |
| Trigger event | What starts the clock (e.g. date of creation, date of project closure, date of last review) |
| Action at end | Destroy, review, transfer to archive, transfer to another body |
| Authority | Legal, regulatory, or policy basis for the decision |
| Review date | When this schedule entry should itself be reviewed |

### Retention periods — common sources of authority

- **Statute of limitations** — determines minimum retention for records needed in legal proceedings
- **Regulatory requirements** — sector-specific (healthcare, financial, education, local government)
- **Freedom of information / access to information legislation** — records must exist to be disclosed
- **Data protection law** — personal data should not be kept longer than necessary (purpose limitation)
- **Administrative need** — operational records kept for internal reference
- **Historical / archival value** — records of long-term cultural, evidential, or research significance

---

## Disposal

Disposal is the action taken at the end of a retention period. It does not always mean destruction.

**Dispose by destruction** — delete or physically destroy records with no long-term value. For digital records, deletion must be verifiable. Document what was destroyed, by whom, on what date, and under what authority.

**Dispose by transfer** — move records of long-term value to an archive or designated repository. This is the entry point for digital preservation.

**Dispose by review** — some records cannot be disposed of without a further appraisal decision. Schedule a review rather than a fixed action.

### Secure deletion of digital records

Deletion from a file system does not securely remove data. For records that must be irretrievably destroyed:
- Overwrite with dedicated software (e.g. Eraser, shred on Linux)
- For storage being decommissioned: physical destruction or degaussing for magnetic media
- For cloud storage: confirm provider's data deletion and certification process
- Document the method and retain a destruction certificate

---

## Legal Holds

A legal hold (also called a litigation hold, disposal freeze, or preservation order) is a direction to suspend normal disposal or destruction of records because they are, or may be, relevant to legal proceedings, regulatory investigation, audit, or a formal information request.

### When a legal hold applies
- Actual or anticipated litigation
- Regulatory investigation or audit
- Freedom of information, access to information, or subject access requests where disposal would prejudice the request
- Internal investigation

### Practical steps when a legal hold is triggered
1. Identify the scope — which record categories, systems, custodians, and date ranges are potentially relevant
2. Issue written notification to relevant staff immediately — do not rely on verbal instruction
3. Suspend any automated disposal or deletion processes that might affect in-scope records
4. Preserve a snapshot or copy of in-scope content if it is at risk of change
5. Document what was placed on hold, when, and why
6. Review and lift the hold when the legal matter concludes — do not leave holds running indefinitely
7. Resume normal disposal for out-of-scope records

**A legal hold overrides a retention schedule.** Records that would normally be destroyed must be kept until the hold is lifted.

---

## Appraisal

Appraisal is the process of determining the value of records and deciding whether and for how long to keep them. It feeds directly into retention scheduling and transfer decisions.

### Appraisal frameworks

**Macro-appraisal** — assess the functions and activities of the creating body first, then evaluate records by how well they document those functions. Developed by the National Archives of Canada; widely adopted.

**Functional appraisal** — similar to macro-appraisal; evaluates records against the business functions they support rather than their physical content.

**Content-based appraisal** — review individual records or series for evidential, informational, or research value. Time-intensive; best for smaller collections or high-value material.

### Appraisal criteria to consider
- **Evidential value** — documents the organisation's mandate, structure, functions, and activities
- **Informational value** — contains information of value to researchers or the public
- **Intrinsic value** — the physical or digital object itself has value (e.g. original signatures, unique media)
- **Administrative value** — still needed for ongoing business
- **Legal value** — required for legal compliance or proceedings
- **Relationship to other holdings** — fills a gap or complements existing holdings

---

## File Plans and Classification

A file plan (or records classification scheme) organises records into a logical hierarchy based on the functions and activities of the creating body. It provides:
- Consistent filing locations so records can be found
- A structure for applying retention periods systematically
- A basis for access controls and sensitivity classification

For digital records, file plan structure is often implemented as folder hierarchies or metadata categories in a document management system. The structure should reflect business functions, not the organisational chart (which changes; functions are more stable).

---

## Vital Records

Vital records are those essential to the continued functioning of an organisation in an emergency or disaster. They must be identified, prioritised, and protected separately.

Examples: financial authorisations, legal agreements, staff records, client or beneficiary data, key operational procedures.

For digital vital records:
- Maintain an up-to-date list
- Ensure multiple copies exist (ideally offsite)
- Test that they can be accessed and used in a recovery scenario
- Review the list regularly — vital records change as the organisation changes

---

## The Records Continuum and Digital Preservation

The records continuum model (developed in Australia, particularly by Frank Upward) treats records not as objects that move through a lifecycle but as entities that exist simultaneously in multiple dimensions of use: creation, capture, organisation, and pluralisation (sharing across communities over time). Unlike the lifecycle model, it does not treat archival preservation as the end of a process — it treats it as an ongoing relationship.

For practical digital preservation work, the key insight is: decisions made at the point of record creation (format, metadata, structure, access controls) have long-term consequences. Engaging with records creators early — before transfer — produces better preservation outcomes than trying to reconstruct context after the fact.

---

## Standards and Guidance

| Standard / Resource | Scope |
|--------------------|----|
| **ISO 15489** (Records Management) | International standard for records management principles and practices |
| **ISO 16175** | Processes and functional requirements for digital records management systems |
| **ISO 23081** | Metadata for records; supports authenticity, context, and records controls over time |
| **MoReq / MoReq2010** (EU) | European specification for records systems; historically influential, especially in procurement and system design |
| **DoD 5015.02** (USA) | US Department of Defense records management design criteria; still encountered as a procurement and compliance reference |
| **NARA guidance** (USA) | National Archives and Records Administration; detailed guidance for US federal records |
| **The National Archives (UK)** | Functional requirements, retention guidance, and disposal authorities for UK public sector |
| **ARMA International** | Professional body for records managers; GARP principles (Generally Accepted Recordkeeping Principles) |
| **SAA** | Society of American Archivists; standards and guidance across archives and records |
