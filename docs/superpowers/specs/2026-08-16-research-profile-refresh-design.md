# webOwie Research Profile Refresh Design

Date: 2026-08-16
Branch: research-profile-refresh
Status: Approved direction, awaiting spec review before implementation

## Goal

Refresh `research.webowie.com` so that David Puchalla's current research identity, verifiable affiliation with webOwie Research, current research outputs, persistent identifiers, selected qualifications, and active research themes are represented clearly and consistently.

The refresh must improve both public research credibility and reviewer verifiability for third-party research-access workflows such as Meta/CASD without overstating institutional status, qualifications, publications, or affiliations.

## Success criteria

A reviewer visiting `https://research.webowie.com/#identity` should be able to determine within roughly 30 seconds:

1. who David Puchalla is;
2. his current role as an independent researcher and system architect;
3. that his declared research affiliation is webOwie Research;
4. which research areas he works on;
5. which persistent research identifiers belong to him;
6. which current public research output is associated with him;
7. how to verify that output and his identifiers independently.

The site must remain a research portal, not become a general personal CV or marketing landing page.

## Identity model

The site will keep personal researcher identity and organizational identity separate but explicitly linked.

### Researcher

- Name: David Puchalla
- Role: Independent Researcher · System Architect
- Research affiliation: webOwie Research
- Research identity URL: `https://research.webowie.com/#identity`
- Detailed profile: `https://research.webowie.com/people/david-puchalla/`
- ORCID: `0009-0002-0223-0929`
- ResearchID: `rid166406`

### Organization

- Name: webOwie Research
- Positioning: researcher-led independent research initiative
- Canonical URL: `https://research.webowie.com/`
- Scope: Open Research, Intelligence Infrastructure and Applied Systems Engineering

The wording intentionally does not claim university, public-sector, intelligence-service, or other institutional affiliation that cannot be independently verified.

## Homepage changes

### `#identity`

Replace the current short researcher summary with a stronger affiliation-verification block.

Required content:

- David Puchalla
- Independent Researcher · System Architect
- webOwie Research
- concise affiliation statement:
  - `David Puchalla conducts independent research within webOwie Research, a researcher-led independent research initiative focused on intelligence systems, AI-assisted research and digital information analysis.`
- persistent identifiers
- link to detailed researcher profile
- link to current research output and DOI

### Research focus

The homepage should represent the current research focus with a concise set of terms rather than an exhaustive keyword cloud:

- Open Source Intelligence (OSINT)
- Social Media Intelligence (SOCMINT)
- Marketing Intelligence
- AI-assisted Research
- Intelligence Orchestration
- Human-AI Teaming
- Digital Risk & Information Integrity
- Cybersecurity & Digital Resilience
- Local-first AI
- Research Automation
- Secure Infrastructure
- Systems Architecture

### Current output card

Add a visible research-output card for the current preprint:

**Title**
`Von OSINT zu Marketing Intelligence: Entwurf und Forschungsagenda einer agentischen All-Source-Architektur für adaptive digitale Marktkommunikation am Beispiel webOwie/DIBA`

**Author**
David Puchalla

**Type**
Preprint

**Version**
1.0

**Date**
2026-08-16

**DOI**
`10.5281/zenodo.21967847`

**License**
CC BY 4.0

If the Zenodo record is still in preview/draft state at implementation time, the website must not label it as fully published. In that case use `Preprint record prepared` or `DOI reserved` until the public record resolves without preview mode.

## Detailed researcher profile

Update `/people/david-puchalla/` and the corresponding source profile so they do not drift apart.

### Header

- David Puchalla
- Independent Researcher · System Architect
- webOwie Research

### Research identity

Include:

- ORCID
- ResearchID
- webOwie resolver URLs
- canonical research portal URL
- research profile URL
- current publication DOI

### Research areas

Use the same canonical research-area list as the homepage.

### Research concepts and systems

Document these as project concepts, not universal scientific terms:

- DIBA
- webOwie
- Silent Hunter
- Intelligence-to-Content
- The Orchestra

Descriptions must be neutral and research-oriented. `Silent Hunter` must be described as an intelligence-first decision concept, not as covert influence or surveillance.

### Selected qualifications and continuing education

Add a section for selected, research-relevant qualifications. Credentials must be represented as credentials or continuing education, not as academic degrees.

Initial verified/current entries:

- AI Search Operating System, Semrush Academy, August 2026
  - verification URL: `https://static.semrush.com/academy/certificates/d9bd3fcaf2/david-puchalla_2.pdf`
- AI Visibility, Semrush Academy, August 2026
  - verification URL: `https://static.semrush.com/academy/certificates/2bd0cd75e1/david-puchalla_37.pdf`
- Generative AI in Marketing, Semrush Academy, August 2026
  - verification URL already documented in project records
- SEO Grundlagen, Semrush Academy, August 2026
  - verification URL already documented in project records
- IP-Führerschein – Markenrecht, PROvendis GmbH, August 2026
- IP-Führerschein – Geschäftsgeheimnisgesetz (GeschGehG), PROvendis GmbH, August 2026
- Digitaler Ersthelfer, BSI-related training record, only if a verifiable supporting record is available in the repository or can be linked from the site

Any credential without a verifiable public source may be listed only as `documented qualification` without a `Verify credential` link, or omitted until a source is added.

## Publications section

Update `/publications/` and its repository index.

The current placeholder `No publication record is indexed here yet` must be removed once a real public record exists.

The first publication record must include:

- full title
- author
- type
- version
- date
- DOI
- ORCID attribution
- license
- abstract or concise summary
- canonical Zenodo URL
- recommended citation
- related research concepts: OSINT, SOCMINT, Marketing Intelligence, DIBA, webOwie, Intelligence-to-Content

The historical LinkedIn article `OSINT ist die neue BWL` may be referenced as a conceptual/historical research artifact, but not represented as a peer-reviewed publication.

## Repository README

Update the repository README to reflect:

- Independent Researcher · System Architect
- affiliation with webOwie Research
- expanded research areas
- publication index now containing a verifiable research output
- DOI link
- ORCID and ResearchID

Keep the existing principle that unfinished work is not promoted into completed research.

## CITATION.cff

The repository-level CFF continues to describe the `webOwie Research` software/research repository, not the individual preprint.

Update keywords to include current research themes where appropriate:

- OSINT
- SOCMINT
- marketing intelligence
- intelligence orchestration
- AI-assisted research
- local AI
- cybersecurity
- research automation
- systems engineering

Do not replace the repository citation with the Zenodo paper citation.

## Machine-readable metadata

Where practical in the existing static site, add lightweight JSON-LD to improve machine-readable identity and affiliation discovery.

### Organization object

- `@type: Organization`
- `name: webOwie Research`
- `url: https://research.webowie.com/`

### Person object

- `@type: Person`
- `name: David Puchalla`
- `jobTitle: Independent Researcher · System Architect`
- `affiliation: webOwie Research`
- `sameAs`: ORCID, ResearchID, canonical research profile

The structured data must mirror visible page content and must not make stronger institutional claims than the page itself.

## Integrity and governance wording

Replace the current integrity note that broadly says the profile does not claim institutional affiliations.

New principle:

`This profile documents only affiliations, identifiers, research outputs and qualifications that can be represented by a source record or a webOwie-controlled organizational record. It does not claim academic, governmental or other institutional affiliations not independently supported by evidence.`

This preserves the earlier anti-overclaiming principle while allowing the actual webOwie Research affiliation to be stated explicitly.

## Files expected to change

Primary implementation scope:

- `index.html`
- `people/david-puchalla/index.md`
- `people/david-puchalla.md`
- `publications/index.md`
- `publications/README.md`
- `README.md`
- `CITATION.cff`

Review and update only if needed:

- `sitemap.xml`
- `_config.yml`
- CSS in `assets/css/site.css`

No unrelated refactoring.

## UX constraints

- Preserve the current dark webOwie Research design language.
- Keep homepage identity concise.
- Put detailed qualifications and concepts on the researcher profile.
- Avoid badge overload.
- Ensure all verification links are plain, accessible links.
- Keep the page readable on mobile.
- No unsupported metrics, rankings, citation counts, employment claims or academic titles.

## Data flow / source hierarchy

For visible claims, use this priority order:

1. public persistent identifiers and records (ORCID, DOI/Zenodo);
2. public credential verification URLs;
3. webOwie-controlled research records;
4. internally documented but non-public qualifications, clearly labeled as such.

A weaker source must not be used to imply a stronger claim than it supports.

## Error handling

- If the Zenodo DOI does not yet resolve publicly, show a non-published status rather than a dead `Published` claim.
- If a credential verification link is missing or broken, omit the verification action rather than inventing one.
- If duplicated identity information differs between homepage and profile, the detailed profile is canonical and the homepage must be updated to match it.

## Testing

Before merge:

1. verify all modified pages render through GitHub Pages/Jekyll;
2. check internal links and anchors, especially `#identity`;
3. verify ORCID, ResearchID and DOI links;
4. verify the profile page works as the Meta/CASD organizational-affiliation evidence URL;
5. inspect mobile layout for the expanded identity block;
6. ensure the publication status matches the actual Zenodo state;
7. confirm no unsupported institutional affiliation is introduced;
8. check CFF syntax remains valid YAML/CFF.

## Out of scope

- redesigning the entire webOwie Research visual identity;
- adding unrelated personal biography or full employment history;
- claiming BND, university, government or other institutional affiliation without independent evidence;
- adding unverifiable certifications or performance metrics;
- changing the underlying hosting architecture.
