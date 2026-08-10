# webOwie Research Hub Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a production-ready static GitHub Pages research portal for webOwie at `https://research.webowie.com`.

**Architecture:** Static HTML/CSS served from GitHub Pages on `main`, with a custom domain via `CNAME`. The site exposes a canonical research identity layer, project index, research-output indexes, and citation metadata without a JavaScript framework or tracking scripts.

**Tech Stack:** HTML5, CSS3, Markdown, GitHub Pages, CFF 1.2.0.

## Global Constraints

- Custom domain: `research.webowie.com`.
- Repository: `webOwie/research`.
- No heavy JavaScript framework.
- No tracking scripts by default.
- Dark/black base, restrained cyan accents, high contrast.
- No fabricated publications, affiliations, metrics, datasets, releases, or credentials.
- Code remains under GNU AGPL v3.0 unless explicitly stated otherwise.
- Research outputs may declare their own licenses later.
- External identifiers: ORCID `0009-0002-0223-0929`, ResearchID `rid166406`.

---

### Task 1: Core metadata and repository documentation

**Files:**
- Modify: `README.md`
- Create: `CITATION.cff`
- Create: `CNAME`
- Create: `_config.yml`

- [ ] Replace the minimal README with the canonical project description, research areas, identities, outputs, licensing and site links.
- [ ] Add valid CFF 1.2.0 citation metadata for David Puchalla and webOwie Research.
- [ ] Add `CNAME` containing only `research.webowie.com`.
- [ ] Add minimal Jekyll/GitHub Pages configuration and exclude internal planning docs from generated navigation.
- [ ] Verify all identifiers and URLs are internally consistent.

### Task 2: Production home page and visual system

**Files:**
- Create: `index.html`
- Create: `assets/css/site.css`

- [ ] Build a semantic HTML5 home page with hero, research identity, research areas, active R&D, research outputs, external identities, principles and citation sections.
- [ ] Add canonical, Open Graph and descriptive metadata.
- [ ] Add responsive CSS using the established black/cyan webOwie identity.
- [ ] Ensure accessible focus states, contrast and responsive layouts.
- [ ] Verify every internal navigation target exists or is an external canonical URL.

### Task 3: Researcher identity

**Files:**
- Create: `people/david-puchalla.md`

- [ ] Publish a concise researcher profile separating personal identity from the webOwie organization.
- [ ] Include ORCID and ResearchID canonical and resolver links.
- [ ] Describe research areas without adding unverifiable affiliations or claims.

### Task 4: Project index and initial project records

**Files:**
- Create: `projects/README.md`
- Create: `projects/infrastructure-client.md`
- Create: `projects/proxmox-management.md`
- Create: `projects/osint-research-stack.md`
- Create: `projects/local-ai-infrastructure.md`

- [ ] Create an index that clearly labels projects as active R&D rather than completed publications.
- [ ] Add purpose, scope and current status to each project page.
- [ ] Keep claims limited to documented project intent and current development scope.

### Task 5: Research output indexes

**Files:**
- Create: `publications/README.md`
- Create: `software/README.md`
- Create: `datasets/README.md`
- Create: `methods/README.md`
- Create: `research-notes/README.md`

- [ ] Create useful, non-empty index pages describing what each section will contain.
- [ ] Explicitly state when no indexed output has been published yet instead of inventing records.
- [ ] Define minimum metadata expected for future additions.

### Task 6: Verification and review

**Files:**
- Review all files created or modified above.

- [ ] Fetch the final files from the feature branch and verify canonical URLs, identifiers and navigation.
- [ ] Compare the feature branch against `main` and inspect the changed-file set.
- [ ] Open a pull request with a concise scope summary and verification checklist.
