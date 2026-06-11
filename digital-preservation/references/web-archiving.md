# Web Archiving

## What Web Archiving Is

Web archiving is the process of capturing and preserving web content — pages, sites, social media, dynamic applications — so it remains accessible after the live version changes or disappears. It is a distinct preservation workflow from handling files received from depositors: you are capturing content from a live environment, not receiving a transfer.

Web content is among the most volatile digital material. If you have a collecting mandate that includes websites, social media, or online publications, you need an active capture strategy.

---

## Key Concepts

**Crawl** — an automated process that follows links across a website, downloading pages and resources. The quality of a crawl depends heavily on configuration and the technical complexity of the target site.

**WARC (Web ARChive)** — the standard preservation format for web captures (ISO 28500). A WARC file bundles the captured content with HTTP response headers and metadata. It is the format you should be creating and preserving.

**Replay** — playing back a captured WARC file so it looks and behaves like the original site. Replay quality varies; complex, JavaScript-heavy sites are the hardest to replay accurately.

**Seed** — a starting URL for a crawl. One seed may result in thousands of captured pages if the crawler follows links.

**Scope** — the rules that define what the crawler will and will not follow. A poorly scoped crawl will either miss content or capture far more than intended.

---

## Capture Tools

| Tool | Type | Notes |
|------|------|-------|
| **Heritrix** | Server-based crawler | Internet Archive's open-source tool; powerful but requires technical setup; outputs WARC |
| **Browsertrix** | Cloud-based / Docker | Webrecorder's modern browser-based crawler; handles JavaScript-heavy sites better than traditional crawlers; outputs WARC |
| **ArchiveWeb.page** | Browser extension / desktop app | Interactive capture tool for individual pages or sessions; good for login-required or highly interactive content |
| **HTTrack** | Desktop | Older tool; simpler setup; does not produce WARC; use for basic site mirroring only |
| **Archive-It** | Subscription service | Internet Archive's managed service for institutions; handles infrastructure; good starting point if you lack technical capacity |
| **Wget** | Command-line | Can produce WARC output with `--warc-file` flag; lightweight for simple sites |

```bash
# Basic wget WARC capture
wget --warc-file=capture --recursive --level=2 --wait=1 https://example.com
```

---

## WARC Format

WARC files contain:
- The raw HTTP responses (HTML, CSS, images, scripts, etc.)
- Request and response headers
- Capture metadata (date, IP address, WARC record type)

A single crawl typically produces multiple WARC files. Keep all of them — splitting is by size, not by completeness.

**Companion files produced by most crawlers:**
- **CDX index** — a sorted index of all URLs captured, used for replay and deduplication
- **Crawl log** — record of what was fetched, redirected, or failed

Keep CDX indexes alongside WARCs. Without them, replay is significantly slower.

---

## Replay Tools

| Tool | Notes |
|------|-------|
| **PyWb** | Python-based; most actively maintained; use for local replay and as a base for hosted access |
| **OpenWayback** | Java-based; older; still widely deployed but less actively developed |
| **ReplayWeb.page** | Browser-based replay; useful for local viewing, sharing, and embedding access to specific captures |
| **Webrecorder Player** | Desktop replay of individual web archive packages; useful for access copies and offline use |

Replay quality is never guaranteed. Always verify captures immediately after crawl, especially for important sites.

---

## Workflow

### Before Crawling
- Define scope: what sites, what depth, what frequency?
- Run a small test crawl before a full capture - it is the fastest way to spot missing assets, bad scope rules, and crawler traps
- Check robots.txt — respect crawl exclusion rules unless you have explicit permission or a legal mandate
- Confirm you have the right to crawl and preserve (see Rights below)
- Identify obvious crawler traps and exclusions up front: calendars, faceted search, infinite scroll, and third-party domains
- Set up a schedule for recurring captures if the site changes regularly

### During and After Crawling
1. Run the crawl; monitor for errors and scope drift
2. Verify the capture: replay key pages immediately and check for missing content
3. Generate checksums for all WARC files
4. Record: seed URLs, crawl date and time, tool and version, scope rules, file sizes and checksums
5. Store WARCs with CDX indexes and crawl metadata

### Quality Checks
- Does the front page render correctly?
- Are images, CSS, and scripts loading?
- Do key internal links resolve within the capture?
- Is dynamic or JavaScript-rendered content captured (or noted as not captured)?

Document any significant gaps — this is part of the preservation record.

---

## Common Challenges

**JavaScript-heavy sites** — traditional crawlers fetch HTML but may not execute JavaScript, missing dynamically loaded content. Use Browsertrix or ArchiveWeb.page for these.

**Login-required content** — public crawlers cannot access content behind authentication. ArchiveWeb.page can capture authenticated sessions.

**Social media** — platforms actively block crawlers. Tools like Browsertrix have partial support; manual capture or platform-specific tools (e.g. Twitter/X archiving via API before API restrictions) may be needed.

**Large sites** — set sensible depth and page limits. A seed pointing to a large CMS can generate millions of URLs. Crawl selectively.

**Embedded third-party content** — video players, maps, analytics scripts, fonts hosted elsewhere. These may not be captured or may not replay correctly. Document what is and is not preserved.

---

## Rights and Legal Considerations

Web content is subject to copyright by default. Before archiving, consider:
- **Deposit agreements or permissions** — does a deposit agreement or explicit permission cover web capture?
- **Legal deposit** — some national libraries have legal deposit powers covering web content (UK, Ireland, France, Australia). If you are a legal deposit library, your mandate may cover this.
- **robots.txt** — not legally binding in most jurisdictions, but disregarding it without a mandate creates reputational and ethical risk
- **Personal data** — web captures may include personal data; GDPR and equivalent laws apply to how you store and provide access to it

---

## Metadata to Capture

At minimum record per crawl:
- Seed URL(s)
- Crawl date and time (with timezone)
- Tool name and version
- Scope rules applied
- Number of WARC files and total size
- Checksums for each WARC file
- Known gaps or failures

---

## Community and Guidance

- **IIPC (International Internet Preservation Consortium)** — primary community body; publishes guidance and tools (netpreserve.org)
- **Archive-It** — Internet Archive subscription service; also publishes partner training materials
- **DPC Technology Watch** — has published reports on social media archiving and web archiving
- **Webrecorder project** — active development of modern capture and replay tools (webrecorder.net)
