# webOwie Research Profile Refresh Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Refresh `research.webowie.com` so David Puchalla's current research identity, webOwie Research affiliation, persistent identifiers, research output, selected qualifications, and current research themes are represented clearly, consistently, and verifiably.

**Architecture:** Preserve the existing static GitHub Pages/Jekyll site and its dark webOwie visual language. Update the homepage for fast identity verification, keep the detailed researcher profile as the canonical personal research record, index the Zenodo preprint as a prepared record until public publication is independently confirmed, and synchronize repository-level metadata without overstating institutional status.

**Tech Stack:** GitHub Pages, Jekyll, Markdown, static HTML, CSS, JSON-LD, Citation File Format (CFF/YAML).

## Global Constraints

- Preserve the current dark webOwie Research design language.
- Keep homepage identity concise and put detailed qualifications and concepts on the researcher profile.
- Use `Independent Researcher · System Architect` and `webOwie Research`; do not claim university, governmental, intelligence-service, or other unsupported institutional affiliation.
- The affiliation statement must be: `David Puchalla conducts independent research within webOwie Research, a researcher-led independent research initiative focused on intelligence systems, AI-assisted research and digital information analysis.`
- Research profile URL: `https://research.webowie.com/people/david-puchalla/`.
- Identity verification URL: `https://research.webowie.com/#identity`.
- ORCID: `0009-0002-0223-0929`.
- ResearchID: `rid166406`.
- Zenodo DOI: `10.5281/zenodo.21967847`.
- Until the DOI resolves as a public Zenodo record without preview mode, label it `Preprint record prepared · DOI reserved`, not `Published`.
- Do not represent credentials as academic degrees.
- Do not add unsupported metrics, rankings, citation counts, employment claims, or academic titles.
- Keep verification links plain and accessible.
- No unrelated refactoring.

---

### Task 1: Strengthen the homepage identity and verification layer

**Files:**
- Modify: `index.html`
- Modify only if needed for layout: `assets/css/site.css`

**Interfaces:**
- Consumes: existing `#identity` anchor and site design classes.
- Produces: a reviewer-readable identity block, visible affiliation wording, research focus summary, DOI/preprint status, and machine-readable Person/Organization metadata.

- [ ] **Step 1: Capture the current identity behavior**

Verify that `index.html` currently contains `section id="identity"`, links to `/people/david-puchalla/`, and the existing title `System Architect · Researcher · OSINT / Cybersecurity`.

Expected current state: identity exists but does not explicitly state `Independent Researcher`, `webOwie Research` affiliation, or the current DOI.

- [ ] **Step 2: Replace the researcher summary with the approved affiliation wording**

Update the visible identity block to contain exactly these core claims:

```html
<div class="meta">Primary researcher · webOwie Research</div>
<h3>David Puchalla</h3>
<p><strong>Independent Researcher · System Architect</strong></p>
<p>David Puchalla conducts independent research within webOwie Research, a researcher-led independent research initiative focused on intelligence systems, AI-assisted research and digital information analysis.</p>
```

Add a concise focus line containing OSINT, SOCMINT, Marketing Intelligence, AI-assisted Research, Intelligence Orchestration, Digital Risk & Information Integrity, Cybersecurity, Local-first AI, Research Automation, Secure Infrastructure, and Systems Architecture.

- [ ] **Step 3: Add current research-output verification to the identity area**

Add a visible identity link/card for:

```text
Preprint v1.0
Von OSINT zu Marketing Intelligence
DOI 10.5281/zenodo.21967847
Status: Preprint record prepared · DOI reserved
```

Link to `https://doi.org/10.5281/zenodo.21967847` but do not call it published until public resolution is verified.

- [ ] **Step 4: Add JSON-LD matching visible claims**

Insert one `application/ld+json` block in `<head>` containing an `@graph` with:

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "https://research.webowie.com/#organization",
      "name": "webOwie Research",
      "url": "https://research.webowie.com/",
      "description": "Researcher-led independent research initiative focused on intelligence systems, AI-assisted research and digital information analysis."
    },
    {
      "@type": "Person",
      "@id": "https://research.webowie.com/people/david-puchalla/#person",
      "name": "David Puchalla",
      "jobTitle": "Independent Researcher · System Architect",
      "url": "https://research.webowie.com/people/david-puchalla/",
      "affiliation": {"@id": "https://research.webowie.com/#organization"},
      "sameAs": [
        "https://orcid.org/0009-0002-0223-0929",
        "https://researchid.co/rid166406",
        "https://research.webowie.com/#identity"
      ]
    }
  ]
}
```

- [ ] **Step 5: Verify homepage consistency**

Confirm that the visible role, affiliation, ORCID/ResearchID links, profile link, DOI, and JSON-LD all agree exactly. Confirm `#identity` remains present and mobile-safe under the existing CSS grid.

- [ ] **Step 6: Commit**

```bash
git add index.html assets/css/site.css
git commit -m "feat: strengthen research identity verification"
```

---

### Task 2: Expand the canonical researcher profile

**Files:**
- Modify: `people/david-puchalla/index.md`
- Modify: `people/david-puchalla.md`

**Interfaces:**
- Consumes: approved canonical role, identifiers, research areas, concepts, qualifications, DOI status.
- Produces: the canonical detailed research identity record used by the homepage and reviewers.

- [ ] **Step 1: Replace the profile header and biography**

Use:

```markdown
# David Puchalla

**Independent Researcher · System Architect**  
**Research affiliation: webOwie Research**

David Puchalla conducts independent research within webOwie Research, a researcher-led independent research initiative focused on intelligence systems, AI-assisted research and digital information analysis. His current work connects Open Source Intelligence, Social Media Intelligence, Marketing Intelligence, AI-assisted research, intelligence orchestration, cybersecurity and local-first systems engineering.
```

Preserve the existing research portrait in the Jekyll profile.

- [ ] **Step 2: Synchronize persistent identifiers and research record**

Include:

```markdown
- ORCID: 0009-0002-0223-0929
- ResearchID: rid166406
- Research portal: https://research.webowie.com/
- Identity verification: https://research.webowie.com/#identity
- Current preprint DOI: 10.5281/zenodo.21967847
- DOI status: Preprint record prepared · DOI reserved
```

- [ ] **Step 3: Replace the research-area list with the canonical current list**

Use these areas:

```text
Open Source Intelligence (OSINT)
Social Media Intelligence (SOCMINT)
Marketing Intelligence
AI-assisted Research
Intelligence Orchestration
Human-AI Teaming
Digital Risk & Information Integrity
Cybersecurity & Digital Resilience
Local-first Artificial Intelligence
Research Automation
Secure Infrastructure
Systems Architecture
```

- [ ] **Step 4: Add research concepts and systems**

Add neutral descriptions:

```markdown
- **DIBA** — acquisition, evidence, provenance and source-quality architecture for digital research.
- **webOwie** — reference implementation and research environment for intelligence-oriented workflows.
- **Silent Hunter** — intelligence-first decision concept that prioritizes observation, evidence fusion, relevance and timing before communication.
- **Intelligence-to-Content** — closed-loop model connecting acquisition, evidence, intelligence, decisioning, generation, activation and feedback.
- **The Orchestra** — orchestration model coordinating specialized research, analysis and action components while preserving role boundaries.
```

- [ ] **Step 5: Add selected qualifications and continuing education**

Use verifiable labels without turning credentials into academic degrees:

```markdown
## Selected qualifications and continuing education

- **AI Search Operating System**, Semrush Academy, August 2026 — [Verify credential](https://static.semrush.com/academy/certificates/d9bd3fcaf2/david-puchalla_2.pdf)
- **AI Visibility**, Semrush Academy, August 2026 — [Verify credential](https://static.semrush.com/academy/certificates/2bd0cd75e1/david-puchalla_37.pdf)
- **Generative AI in Marketing**, Semrush Academy, August 2026 — [Verify credential](https://static.semrush.com/academy/certificates/6d19183135/david-puchalla_26.pdf)
- **SEO Grundlagen (Deutsch)**, Semrush Academy, August 2026 — [Verify credential](https://static.semrush.com/academy/certificates/42da17dcba/david-puchalla_4.pdf)
- **IP-Führerschein – Markenrecht**, PROvendis GmbH, August 2026 — documented qualification
- **IP-Führerschein – Geschäftsgeheimnisgesetz (GeschGehG)**, PROvendis GmbH, August 2026 — documented qualification
```

Do not add a public verification link for a credential where none is available.

- [ ] **Step 6: Replace the integrity note**

Use exactly:

```text
This profile documents only affiliations, identifiers, research outputs and qualifications that can be represented by a source record or a webOwie-controlled organizational record. It does not claim academic, governmental or other institutional affiliations not independently supported by evidence.
```

- [ ] **Step 7: Keep both profile sources synchronized and commit**

```bash
git add people/david-puchalla/index.md people/david-puchalla.md
git commit -m "feat: expand David Puchalla research profile"
```

---

### Task 3: Index the current preprint without overstating publication status

**Files:**
- Modify: `publications/index.md`
- Modify: `publications/README.md`

**Interfaces:**
- Consumes: DOI `10.5281/zenodo.21967847`, title, author, date, version, license and public-status rule.
- Produces: one verifiable research-output record that can later be switched from prepared/reserved to published without restructuring the page.

- [ ] **Step 1: Remove the empty-index placeholder**

Delete `No publication record is indexed here yet.` and replace it with the first indexed research output.

- [ ] **Step 2: Add the preprint record**

Use:

```markdown
## Von OSINT zu Marketing Intelligence

**Full title:** Von OSINT zu Marketing Intelligence: Entwurf und Forschungsagenda einer agentischen All-Source-Architektur für adaptive digitale Marktkommunikation am Beispiel webOwie/DIBA  
**Author:** David Puchalla  
**Type:** Preprint  
**Version:** 1.0  
**Date:** 2026-08-16  
**Status:** Preprint record prepared · DOI reserved  
**DOI:** [10.5281/zenodo.21967847](https://doi.org/10.5281/zenodo.21967847)  
**ORCID:** [0009-0002-0223-0929](https://orcid.org/0009-0002-0223-0929)  
**License:** CC BY 4.0
```

Add a concise summary explaining that the work formalizes an adaptive intelligence-to-content architecture connecting OSINT, SOCMINT, provenance, decisioning, feedback and governance.

- [ ] **Step 3: Add recommended citation and historical artifact note**

Recommended citation:

```text
Puchalla, D. (2026). Von OSINT zu Marketing Intelligence: Entwurf und Forschungsagenda einer agentischen All-Source-Architektur für adaptive digitale Marktkommunikation am Beispiel webOwie/DIBA. Preprint v1.0. Zenodo. https://doi.org/10.5281/zenodo.21967847
```

Add `OSINT ist die neue BWL` only as a conceptual/historical project artifact, not as peer-reviewed research.

- [ ] **Step 4: Synchronize `publications/README.md` and commit**

```bash
git add publications/index.md publications/README.md
git commit -m "docs: index current webOwie research preprint"
```

---

### Task 4: Synchronize repository identity and citation metadata

**Files:**
- Modify: `README.md`
- Modify: `CITATION.cff`

**Interfaces:**
- Consumes: canonical identity wording, identifiers, research areas and publication record.
- Produces: repository-level identity and machine-readable repository citation metadata consistent with the website.

- [ ] **Step 1: Update the README identity**

Replace `System Architect · Researcher · OSINT / Cybersecurity` with:

```text
Independent Researcher · System Architect
Research affiliation: webOwie Research
```

Add the DOI and current preprint status under Research outputs.

- [ ] **Step 2: Expand README research areas**

Use the same canonical list as the profile. Keep active R&D separate from completed outputs.

- [ ] **Step 3: Update `CITATION.cff` keywords only**

Preserve title `webOwie Research`, type `software`, author, ORCID, URL, repository URL and AGPL license. Set keywords to:

```yaml
keywords:
  - OSINT
  - SOCMINT
  - marketing intelligence
  - intelligence orchestration
  - AI-assisted research
  - local AI
  - cybersecurity
  - research automation
  - research infrastructure
  - systems engineering
```

Do not replace the repository citation with the Zenodo paper citation.

- [ ] **Step 4: Validate CFF/YAML shape and commit**

Confirm indentation is two spaces under `authors` and `keywords`, no tabs exist, and the ORCID remains a full HTTPS URL.

```bash
git add README.md CITATION.cff
git commit -m "docs: synchronize research identity metadata"
```

---

### Task 5: Verify navigation, sitemap and release readiness

**Files:**
- Review: `sitemap.xml`
- Review: `_config.yml`
- Review: `assets/css/site.css`
- Review all modified files.

**Interfaces:**
- Consumes: all changes from Tasks 1–4.
- Produces: merge-ready branch with consistent visible and machine-readable identity.

- [ ] **Step 1: Verify sitemap coverage**

Confirm `https://research.webowie.com/`, `/people/david-puchalla/`, and `/publications/` are represented. Modify `sitemap.xml` only if one is missing.

- [ ] **Step 2: Verify identity anchor and internal links**

Confirm:

```text
/#identity
/people/david-puchalla/
/publications/
/CITATION.cff
```

all remain linked from the site.

- [ ] **Step 3: Verify external identifiers**

Confirm exact URLs:

```text
https://orcid.org/0009-0002-0223-0929
https://researchid.co/rid166406
https://doi.org/10.5281/zenodo.21967847
```

- [ ] **Step 4: Verify claim boundaries**

Search modified content for unsupported claims such as `BND`, `Bundesnachrichtendienst`, `university`, `professor`, `published` or unverifiable citation/impact metrics. The only acceptable `published` wording is generic process documentation, not a false status claim for the current DOI.

- [ ] **Step 5: Compare the implementation branch against `main`**

Review the changed-file list and confirm the diff is limited to identity, publication, metadata, design/plan documentation and any strictly necessary sitemap/CSS changes.

- [ ] **Step 6: Final commit if verification required corrections**

```bash
git add -A
git commit -m "chore: verify research profile refresh"
```

- [ ] **Step 7: Merge only after verification**

Fast-forward or merge `research-profile-refresh` into `main` once all checks pass.
