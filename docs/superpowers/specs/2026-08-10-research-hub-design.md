# webOwie Research Hub — Design Specification

Date: 2026-08-10
Status: Approved design baseline
Target repository: `webOwie/research`
Target domain: `https://research.webowie.com`

## 1. Purpose

`research.webowie.com` is the canonical research and technical identity hub for the webOwie ecosystem. It consolidates research identities, projects, publications, software, datasets, methods and citation metadata under a domain controlled by webOwie while linking to external authority profiles and platforms.

The site is not a redirect and not a generic corporate landing page. It is an auditable research index and publication surface.

## 2. Primary goals

1. Establish a canonical research identity layer under `webowie.com`.
2. Link webOwie research activity with ORCID, ResearchID, GitHub and LinkedIn.
3. Publish project descriptions, software outputs, technical reports, research notes, datasets and methods.
4. Provide machine-readable citation metadata through `CITATION.cff` and structured page metadata.
5. Keep the platform static, transparent, portable and easy to host through GitHub Pages.
6. Preserve local-first, privacy-aware and operator-controlled design principles.

## 3. Canonical identity topology

- Main website: `https://webowie.com`
- Research hub: `https://research.webowie.com`
- GitHub resolver: `https://github.webowie.com`
- LinkedIn resolver: `https://linkedin.webowie.com`
- ORCID resolver: `https://orcid.webowie.com`
- ResearchID resolver: `https://researchid.webowie.com`

Native references remain available where useful:

- GitHub: `https://github.com/webOwie`
- ORCID: `https://orcid.org/0009-0002-0223-0929`
- ResearchID: `https://researchid.co/rid166406`

## 4. Research identity

Primary researcher:

**David Puchalla**

Roles represented on the research portal:

- System Architect
- Researcher
- OSINT / Cybersecurity

External identifiers:

- ORCID: `0009-0002-0223-0929`
- ResearchID: `rid166406`

The portal must clearly distinguish personal researcher identity from the webOwie organizational identity.

## 5. Research areas

The top-level research taxonomy is intentionally limited to six primary areas:

1. Local-first Artificial Intelligence
2. OSINT & Information Intelligence
3. Cybersecurity & Digital Resilience
4. Research Automation
5. Secure Infrastructure
6. Systems Architecture

Secondary subjects such as Proxmox, ZeroTier, DNS, certificates, private networking, SearXNG, agent architectures and security automation are grouped below these areas rather than promoted to top-level categories.

## 6. Information architecture

The repository/site will use the following logical structure:

```text
/
├── index.html
├── README.md
├── LICENSE
├── CITATION.cff
├── CNAME
├── _config.yml
├── people/
│   └── david-puchalla.md
├── projects/
│   ├── README.md
│   ├── infrastructure-client.md
│   ├── proxmox-management.md
│   ├── osint-research-stack.md
│   └── local-ai-infrastructure.md
├── publications/
│   └── README.md
├── software/
│   └── README.md
├── datasets/
│   └── README.md
├── methods/
│   └── README.md
├── research-notes/
│   └── README.md
├── assets/
│   └── css/
│       └── site.css
└── docs/
    └── superpowers/
        └── specs/
```

## 7. Home page design

The home page will be a static research portal with these sections:

### Hero

- `webOwie Research`
- `Open Research, Intelligence Infrastructure and Applied Systems Engineering`
- concise explanation of local-first, reproducible and operator-controlled research

### Research Identity

- David Puchalla
- ORCID
- ResearchID
- links to resolvers and native profiles

### Research Areas

Six concise cards or semantic sections for the research taxonomy.

### Current Research & Development

Initial project entries:

- webOwie Infrastructure Client
- Proxmox Infrastructure Management
- OSINT Research Stack
- Local AI Infrastructure
- Private Networking / ZeroTier integration as a related subject where appropriate

### Research Outputs

Links to:

- Publications
- Technical Reports
- Research Notes
- Software
- Datasets
- Methods
- Experiments and documentation when material exists

### Open Source & External Identity

Canonical links to GitHub, LinkedIn, ORCID and ResearchID.

### Citation

Expose repository citation metadata and provide a direct link to `CITATION.cff`.

## 8. Visual design

The site should follow the established webOwie visual identity without becoming a marketing microsite.

Principles:

- dark/black base
- restrained cyan accents
- high contrast
- typography optimized for technical reading
- responsive layout
- no heavy JavaScript framework
- no tracking scripts by default
- accessible semantic HTML
- minimal visual effects

The research portal should look credible as both a technical project index and an academic-facing reference page.

## 9. Technical architecture

### Hosting

GitHub Pages on the `main` branch.

### Custom domain

`research.webowie.com`

The repository will contain:

```text
CNAME
```

with exactly:

```text
research.webowie.com
```

DNS configuration itself remains outside the repository.

### Runtime

Static HTML/CSS with GitHub Pages compatibility. No build system is required for the initial version.

This avoids unnecessary dependencies and keeps the portal auditable and portable.

## 10. Metadata and discoverability

The site should include:

- descriptive HTML title and meta description
- canonical URL
- Open Graph metadata
- researcher and organization metadata where appropriate
- semantic headings
- meaningful page descriptions
- explicit links to persistent researcher identifiers

No unverifiable claims, fabricated publications, fabricated affiliations or invented credentials may be added.

## 11. Citation model

The repository will provide a root-level `CITATION.cff` with:

- project title
- repository URL
- research portal URL
- author name
- ORCID
- license identifier
- keywords

Individual publications may later use DOI/Zenodo metadata and their own citation records.

## 12. Licensing

The existing repository license is GNU Affero General Public License v3.0.

Code and repository software components remain under AGPL-3.0 unless explicitly stated otherwise.

Research publications, datasets or third-party materials may require separate licenses. Those licenses must be declared per output instead of assuming the software license automatically applies to all research material.

## 13. Content integrity rules

The portal must distinguish between:

- active projects
- planned projects
- publications
- research notes
- software releases
- datasets

Planned work must never be presented as completed research or released software.

External identifiers must use canonical values and be checked before publication.

## 14. Initial implementation scope

The first implementation will create:

1. production-ready README
2. `CITATION.cff`
3. `CNAME`
4. `_config.yml`
5. static `index.html`
6. shared CSS
7. researcher profile page
8. initial project index and project pages
9. publication/software/dataset/method/research-note indexes
10. links to webOwie, GitHub, LinkedIn, ORCID and ResearchID

No fabricated publication records or empty fake metrics will be added.

## 15. Success criteria

The initial version is successful when:

- the repository clearly represents webOwie Research
- the research identity is consistent across external identifiers
- the site can be served through GitHub Pages
- `research.webowie.com` is ready to be attached as the custom domain
- all navigation targets exist
- no broken internal links are introduced
- citation metadata is valid in structure
- the portal distinguishes current work from future research outputs
- the design remains usable on desktop and mobile

## 16. Future extensions

Out of scope for the first implementation but intentionally supported by the architecture:

- Zenodo / DOI publication indexing
- BibTeX and CSL exports
- JSON-LD / Schema.org research metadata
- automated publication feeds
- project release indexing
- datasets with provenance metadata
- multilingual research pages
- automated validation workflows

These should be introduced only when real source records exist.
