# NGI Zero – søknadsutkast (arbeidsdokument)

> **Status:** Under utvikling – sesjon 55 (2026-05-24)
> **Prosjektnavn:** CommDocs / commdocs.org (registrert 2026-05-24)
> **Frist:** 1. juni 2026 kl. 12:00 CEST
> **Avsender:** Erik Hagen / Interop AS (privatperson/AS), med referanse til SAMT-BU som tidlig pilot
> **Gjenstår:** Team-seksjon (tas 2026-05-25), avklaringer i «What is new», verifisere COM/2021/118-ref

---

## Hva jeg spør om (til prosjekteier/Digdir)

Jeg vurderer å søke NGI Zero-midler (inntil €50 000) for å bygge en generisk,
åpen kildekode-plattform for markedsdialog og samskaping i offentlig sektor –
basert på metoden vi har utviklet og testet i SAMT-BU.

Jeg ber om avklaring på tre punkter:

1. **Proof of Method-referanse:** Kan jeg i søknaden referere til SAMT-BU-piloten
   som tidlig evidens for at metodikken er relevant? Jeg vil referere til
   *metoden og lærdommene*, ikke til kode eller infrastruktur som tilhører Digdir/SAMT-BU.

2. **Digdir som samarbeidspartner:** Vil Digdir/SAMT-BU vurdere å stille som
   samarbeidspartner eller skrive en kort støtteerklæring til søknaden? NLnet ser
   positivt på at prosjekter er forankret i reelle brukerbehov. En slik erklæring
   binder ikke Digdir til noe kommersielt.

3. **Klarhet om opphavsrett og sideprosjekt:** Kan vi avklare at en eventuelt
   NGI-finansiert, generisk videreutvikling gjøres i privat regi (Interop AS), og
   at dette ikke er i konflikt med min stilling eller SAMT-BU-prosjektet?

**Mulig tillegg:** DFØ (Direktoratet for forvaltning og økonomi) – e-post sendes
tirsdag 2026-05-27 for å be om støtteerklæring. Se utkast til e-post og brev
nedenfor (seksjon «Støtteerklæring DFØ»).

---

## Søknadsutkast (engelsk – NLnet-format)

*NLnet aksepterer søknader på engelsk via skjema på nlnet.nl. Teksten under
følger strukturen i NLnet-skjemaet og kan justeres før innsending.*

---

### Project name

**CommDocs**

*Tagline: Open collaborative documentation for public-interest initiatives*

*Domain: commdocs.org (registered 2026-05-24)*

---

### Abstract (max 500 chars)

Cross-sector public initiatives need open, traceable documentation where domain
experts, legal staff and translators contribute on equal terms with developers.
No current tooling enables this. CommDocs extends the git collaboration model —
proven across open source communities — to non-technical contributors through a
simple web interface. An early pilot at the Norwegian Digitalisation Agency
provides initial evidence. Research: git as compliance mechanism; persistent
identifiers for open annotation.

*(~494 tegn)*

---

### Problem

Public procurement law across the EU (Directive 2014/24/EU) and EEA requires
that pre-procurement market dialogue be conducted with equal treatment and
transparency. In practice, this is nearly impossible to guarantee:

- Market dialogues happen in meetings, emails, and closed portals where
  information reaches participants unevenly.
- Documenting equal treatment is an administrative burden that falls entirely
  on the contracting authority.
- Small and non-traditional actors (startups, research groups, civil society)
  lack the resources to track and participate in scattered dialogue processes.
- Existing procurement tools (Mercell, TendSign, Visma) treat compliance as an
  audit problem: logs and locked rooms. This is compliance *after the fact*.

The challenge extends beyond procurement: any cross-sector, cross-border
initiative — co-creating policy, jointly developing standards, building shared
knowledge bases — faces the same structural exclusion of non-technical
contributors from version-controlled workflows.

The result: collaborative documentation processes are legally risky,
administratively burdensome, and systematically exclude the domain experts,
lawyers and translators whose participation is essential.

---

### Solution

A platform where the dialogue medium *is* the compliance mechanism.

When all contributions are made directly in open, version-controlled documents —
visible to all participants simultaneously, with immutable timestamps and author
attribution — the equal treatment requirement is structurally satisfied without
any additional administrative overhead.

The core insight: **compliance by design, not by audit**.

CommDocs builds on:
- A static site generator (Hugo) for structured, navigable content
- Git as the provider-agnostic version control and audit layer — any git host
  supporting OAuth, merge requests, and repository-level access control
  (GitLab CE, GitHub, Forgejo, or any self-hosted instance) can serve as
  CommDocs backend
- Repository-scoped access control: content modules reside in independently
  governed repositories that may be hosted on different git providers
  simultaneously — organisations adopt gradually without requiring
  provider migration
- A user-friendly contribution interface: "Suggest change", "Suggest new
  section", "Leave comment" — no command-line knowledge required
- A lightweight authentication gateway (reference implementation: Cloudflare
  Workers; replaceable with any OAuth relay service, including self-hosted
  open source alternatives)
- Stable, resolvable content identifiers (UUID-based) enabling permanent
  references and open annotation

The result: any organisation can open a collaborative documentation space,
publish it openly, and receive fully documented, equal-access contributions
from any participant — whether for procurement market dialogue, cross-agency
co-creation, or joint programme documentation.

---

### Proof of method

The methodology builds on the proven git collaboration model used across
thousands of open source communities — where transparent, attributed,
version-controlled contributions are the norm. CommDocs applies this model
to public sector documentation workflows.

An early-stage pilot at the Norwegian Digitalisation Agency (Digdir), as part
of the SAMT-BU project — a cross-agency initiative for integrated digital
services for children and youth — provides initial evidence:

- Open, version-controlled documentation was used for collaborative knowledge
  building across public agencies and contributing parties.
- The contribution interface (suggest change / suggest new section) was tested
  with non-technical users, confirming that the git mechanism can be fully
  abstracted away.
- The open, timestamped, auditable contribution structure was found to align
  with the equal treatment requirements of the Norwegian procurement act.

The pilot implementation is bespoke, tightly coupled to a single agency's
infrastructure, and not designed for reuse. This application seeks funding
to build a standalone, reusable platform that makes this methodology
available to any organisation in Europe.

---

### What is new / why now

**The components are not new. The combination is.**

Version-controlled documentation, non-technical web interfaces, and open
annotation are established concepts. What does not exist is their integration
into a coherent platform where the git audit trail is the compliance mechanism,
non-technical participants are first-class contributors, and content elements
carry stable, resolvable identifiers.

---

**Competitive landscape**

Existing tools fail at different points in the requirement triangle
(open + traceable + non-technical):

*General collaboration tools — Confluence, Notion, SharePoint, Google Docs* —
enable non-technical co-authorship but provide no open, verifiable audit trail.
Contributions are locked in proprietary systems; equal treatment in a legal
sense cannot be demonstrated.

*Git-native documentation — GitHub/GitLab wikis, Hugo, Docusaurus, MkDocs* —
provide full traceability and openness but require technical literacy that
structurally excludes most public sector contributors.

*Procurement tools — Mercell, TendSign, Visma* — treat compliance as a
closed-room problem: access control, audit logs, locked portals. Transparency
to all market participants simultaneously is not a design goal.

*Web annotation — Hypothesis.is* — provides inline commenting on web content
but is centralised, requires account registration, and is disconnected from
any version-controlled document repository.

No existing tool treats git history as a structural compliance mechanism. No
open tool provides stable, resolvable content identifiers for collaborative
markdown documents.

---

**What is specifically new:**

1. **Non-technical contribution as the primary design constraint.** CommDocs is
   designed from the ground up for contributors who will never open a terminal.
   Git and merge requests are implementation details, not user-facing concepts.

2. **Structural compliance — not documented compliance.** No existing procurement
   tool treats open version control as the equal treatment mechanism itself.
   CommDocs makes compliance a property of the process, eliminating a category
   of legal risk that currently deters contracting authorities from meaningful
   market dialogue.

3. **Granular persistent content identifiers — applying data catalog principles
   to collaborative documents.** DCAT and the linked data ecosystem have solved
   persistent identification for datasets: a stable URI resolves via a catalog
   to the current physical access point, regardless of where the data is hosted.
   CommDocs applies this same pattern to documents — treating each page (and
   eventually each heading) as a dataset with a persistent identifier, a set of
   distributions (rendered HTML, raw markdown), and a catalog entry
   (`uuid-map.json`). A document is a dataset; its frontmatter is its metadata
   record; its UUID is its catalog identifier. Within a single deployment,
   Hugo's built-in `relref` mechanism provides build-time link validation —
   links to non-existent pages fail the build. This guarantee breaks down across
   repository boundaries and across CommDocs instances; UUID-based resolution
   extends it regardless of which repository hosts the target, which git provider
   serves that repository, or how the content has been restructured. Block-reference
   systems exist in proprietary tools (Notion, Roam, Logseq), and Akoma Ntoso
   addresses clause-level identification in legal XML. No open specification
   extends this model to sub-document granularity in git-native collaborative
   content. CommDocs will deliver both the specification and the resolver
   infrastructure — making documents first-class participants in the European
   data space alongside structured datasets.

4. **W3C Web Annotation on git-native markdown.** The W3C Web Annotation
   standard (2017) defines a data model for inline commenting on any web
   resource, including external sources (legislation, standards, prior
   publications). No open implementation exists for git-backed collaborative
   documentation. CommDocs will make Word-like inline commenting available on
   version-controlled documents — with full attribution and traceability.

---

**Why now:**

*Regulatory moment.* The EU's guidance on innovation procurement (COM/2021/118)
explicitly calls for more structured pre-procurement engagement. Member states
are actively seeking practical tools; none currently exist as open infrastructure.
*(NB: referansen COM/2021/118 bør verifiseres)*

*Open source in government.* The EU Open Source Strategy 2020–2023 and member
state mandates create sustained political momentum for public sector tools built
entirely on open infrastructure. CommDocs is implemented on GitLab CE —
open source all the way down.

*Ecosystem readiness.* Docs-as-code is a mature discipline; GitLab CI, Hugo and
the W3C annotation stack are stable, well-maintained foundations. The missing
piece — a non-technical contribution layer with compliance-grade audit properties
— is the specific gap CommDocs addresses, and the moment to build it is now.

---

### Technical approach and deliverables

CommDocs builds on a validated pilot implementation at the Norwegian
Digitalisation Agency (docs.samt-bu.no) and advances it along two distinct
research axes.

---

**Platform foundation**

The shared substrate for both research tracks:

- Standalone, self-hostable deployment (Docker-based)
- Contribution interface for non-technical users: *Suggest change*,
  *Suggest new section*, *Leave comment* — backed by git merge requests,
  no git knowledge required
- Provider-agnostic architecture: content modules may reside on different git
  hosts simultaneously (GitLab CE, GitHub, Forgejo, Gitea); organisations
  can mix providers within a single site and adopt gradually without
  requiring a big-bang migration
- Reference implementations on GitLab CE and GitHub; Forgejo recommended as
  the fully sovereign self-hosted option for organisations requiring no
  dependency on commercial platforms
- Multi-language framework (Norwegian and English as initial implementation
  languages)
- Operator documentation: deploy and configure a new dialogue instance in
  under one day

---

**RQ1 — Git as structural compliance mechanism**

*How can an open git history satisfy the equal treatment requirements of public
procurement law — structurally, not as an audit afterthought?*

The hypothesis: if all contributions to a market consultation are made through
an open, timestamped, author-attributed git history — visible simultaneously
to all participants — the equal treatment requirement (EU Directive 2014/24/EU
Art. 40; Norwegian LOA § 4) is satisfied by the process itself, without
additional administrative documentation.

The pilot confirmed the principle in practice. What remains unresolved: the
precise mapping between git contribution events and the legal evidence
requirements across EU member state implementations — and the tooling to make
this mapping exportable and reusable.

*Deliverables:*
- **Contribution log generator** — automated structured export (PDF + JSON)
  of a complete dialogue record referencing git commits, suitable as
  procurement documentation for KOFA (Norway) and OJEU (EU)
- **Phase-gate management** — configurable dialogue phases (open / input
  period / summary / closed) with auditable state transitions and clear
  participant-facing status signalling
- **Compliance specification** — a published document mapping git audit trail
  to EU procurement law requirements, reusable by any implementing authority
- **Pilot deployment** — migration of docs.samt-bu.no to standalone CommDocs
  platform; letter of intent from at least one additional public sector
  organisation (Novari / KF / DFØ — pending)

---

**RQ2 — Granular, persistent content identifiers and open annotation**

*How can individual content elements in a git-native collaborative documentation
system be assigned stable, resolvable identifiers — enabling permanent references,
cross-document transclusion, and Word-like inline commenting on arbitrary content
spans, including references to external resources?*

The pilot has already implemented UUID-based persistent identifiers at document
(file) level — the same pattern used in DCAT data catalogs, where a stable URI
resolves via a catalog to the current physical access point regardless of where
the data is hosted. This project formalises and extends that foundation in two
directions: a resolver service for stable permalinks, and an open annotation
layer using the W3C Web Annotation standard as data model.

The W3C Web Annotation model separates annotations from documents: a comment
references a target resource (identified by UUID or URL) and a selector (a text
span, heading, or position within that resource). This makes annotations:
- independent of document structure
- applicable to both CommDocs content and external resources (laws, standards,
  prior publications)
- portable across implementations

No open, self-hostable implementation of this model exists for git-native
markdown documentation.

Related prior art: Akoma Ntoso (legal XML, EU/UN legislation), W3C Web
Annotations (2017 Recommendation), Hypothesis.is (web annotation, centralised),
block-reference systems in Notion/Roam/Logseq (all proprietary).

*Core deliverables:*
- **UUID resolution service** — lightweight, self-hostable service resolving
  `/{uuid}` to current canonical URL, maintaining redirect history across
  restructuring; generated from Hugo build as `uuid-map.json`
- **CommDocs Content Identity Specification** — open specification for
  file-level and heading-level persistent identifiers in markdown-based git
  repositories
- **Heading-UUID tooling** — automated assignment and maintenance of UUID
  anchors on headings within files

*Phase 2 — Annotation layer:*
- **W3C Web Annotation implementation** — JavaScript annotation layer rendering
  inline comments on CommDocs pages; text-selection triggers comment creation;
  annotations stored as structured JSON in a git-backed annotation repository
- **External resource annotation** — annotations targeting external URLs
  (legislation, standards, prior publications) displayed in context within
  CommDocs documents
- **Annotation resolution across versions** — TextQuoteSelector as primary
  anchor, TextPositionSelector as fallback; comments marked «anchored to
  version X» when source text has changed

*Future work (beyond this grant):*
- Sub-file granularity below heading level (paragraph/sentence)
- Diff-based automatic comment migration across document versions
- Federation of annotation stores across CommDocs instances

---

**Timeline**

| Months | Focus |
|--------|-------|
| 1–3    | Platform foundation, contribution interface, GitLab migration, multi-language |
| 2–5    | RQ1: contribution log generator, phase-gate management |
| 3–6    | RQ2 core: UUID resolver, Content Identity Specification, heading-UUID tooling |
| 5–8    | Compliance specification, pilot deployment, security review |
| 6–9    | RQ2 annotation layer: W3C Web Annotations implementation |
| 8–10   | External resource annotation, version-tracking for comments |
| 10–12  | Documentation, community bootstrap, final report |

---

**Open source licence:** EUPL-1.2 (European Union Public Licence) — OSI-approved,
compatible with EU institutional requirements.

---

### Why NGI Commons

This project directly addresses four NGI Commons priorities:

- **Digital commons for public infrastructure:** CommDocs gives every public
  sector organisation in Europe access to a compliance-grade collaborative
  documentation platform without vendor dependency or licensing costs.

- **European digital sovereignty:** Built on GitLab CE — open source
  infrastructure with no dependency on proprietary US platforms. Self-hostable
  by any organisation with basic technical capacity.

- **Trust and transparency by design:** Git version control as an accountability
  mechanism is a direct implementation of the transparency-by-design principle
  applied to public governance.

- **Open standards and interoperability:** CommDocs implements the W3C Web
  Annotation standard and EUPL-1.2, contributing to the open annotation
  ecosystem rather than creating a new silo.

---

### Team

*[TAS 2026-05-25 – se notater nedenfor]*

**Notater til Team-seksjonen:**

- **Erik Hagen** – prosjektleder / plattformarkitektur / UX (Interop AS, privat
  kapasitet – ikke på vegne av Digdir)
- **[Sønnens navn]** – SW-utvikling (Interop AS); MSc informatikk NTNU,
  leverer masteroppgave [måned] 2026
- **[Datterens navn]** – brukerdesign og interessentengasjement (Interop AS);
  bakgrunn i sosialfag; dekker ikke-tekniske bidragsytere, tilgjengelighet,
  brukertest
- **Mulig: Espen / NeoSystems.ai** – subcontractor for avgrenset komponent
  (avklares)
- **Pilot-partnere (LoI):** Novari (non-profit, fylkeskommuner) og/eller KF
  (Kommuneforlaget) – kontaktes denne uka
- **Støtteerklæring:** DFØ (e-post sendes tirsdag), Digdir/SAMT-BU (avklares)

---

### Budget breakdown

| Item | EUR |
|------|-----|
| Core platform development — Erik Hagen (architecture, GitLab migration, integration) | 20 000 |
| Software development — [sønn] (UUID resolver, annotation layer, CI/CD) | 12 000 |
| User research and accessibility — [datter] (testing, WCAG 2.1 AA, docs) | 5 000 |
| Independent security review | 6 000 |
| Legal and governance (EUPL-1.2, CLA, governance structure) | 4 000 |
| Pilot deployments and onboarding support | 1 000 |
| Documentation and community bootstrap | 2 000 |
| **Total** | **50 000** |

*NB: Budsjett justeres når Team-seksjon er ferdigstilt.*

---

### Prior work and references

- CommDocs project site: [commdocs.org](https://commdocs.org) *(under utvikling)*
- SAMT-BU early pilot: [docs.samt-bu.no](https://docs.samt-bu.no)
- Market dialogue methodology:
  [docs.samt-bu.no/ekstern-markedsdialog](https://docs.samt-bu.no/ekstern-markedsdialog/)
- NLnet NGI Zero Commons Fund: [nlnet.nl/commonsfund](https://nlnet.nl/commonsfund/)
- EU Procurement Directive 2014/24/EU, Article 40
- EU guidance on innovation procurement: COM/2021/118 *(verifiseres)*
- W3C Web Annotation standard: [w3.org/TR/annotation-model](https://www.w3.org/TR/annotation-model/)
- Akoma Ntoso (legal document XML): [akomantoso.org](http://www.akomantoso.org/)
- Norwegian Public Procurement Act (LOA) § 4, Anskaffelsesforskriften § 8-2
- GitLab CE: [gitlab.com/gitlab-org/gitlab](https://gitlab.com/gitlab-org/gitlab)
- Forgejo (self-hosted git): [forgejo.org](https://forgejo.org/)
- W3C DCAT (Data Catalog Vocabulary): [w3.org/TR/vocab-dcat](https://www.w3.org/TR/vocab-dcat/)
- W3C Cool URIs for the Semantic Web: [w3.org/TR/cooluris](https://www.w3.org/TR/cooluris/)
- Handle System (persistent identifiers): [handle.net](https://www.handle.net/)

---

## Støtteerklæring DFØ – utkast til e-post og brev

### E-post til DFØ-kontakt (sendes tirsdag 2026-05-27)

```
Emne: Støtteerklæring til NGI-søknad – åpen plattform for markedsdialog

Hei [navn],

Jeg arbeider med en søknad til NGI Zero Commons Fund (EU/NLnet) med frist 1. juni.
Søknaden gjelder CommDocs – en åpen, versjonskontrollert plattform for markedsdialog
og samskaping i offentlige anskaffelsesprosesser.

Kort fortalt: plattformen gjør at likebehandling og sporbarhet er bygget inn i
selve dialogprosessen – compliance by design, ikke compliance by audit. Tidlig
utprøvd i SAMT-BU-prosjektet hos Digdir.

Jeg tenker at dette kan være relevant for neste generasjon anskaffelsesveiledere
hos DFØ – særlig for store, tverrnasjonale samarbeidsprosjekter der åpen, sporbar
markedsdialog er krevende å gjennomføre i dag.

Ville du vurdere å skrive en kort støtteerklæring til søknaden? Ikke en forpliktelse,
bare en bekreftelse på at dere kjenner til konseptet og ser potensial for samarbeid.
Jeg legger ved et utkast du kan tilpasse.

Gjerne ta en kort prat i løpet av uka hvis det er enklere.

Beste hilsen
Erik
```

### Utkast til støtteerklæring (DFØ tilpasser)

```
To: NLnet Foundation
Re: Letter of support – CommDocs (NGI Zero Commons Fund application)

The Norwegian Agency for Public and Financial Management (DFØ) is responsible
for guidance on public procurement in Norway, including market engagement and
innovative procurement procedures.

We have reviewed the CommDocs concept presented by Erik Hagen. The platform
addresses a recognised challenge in pre-procurement market dialogue: ensuring
equal treatment and traceability of contributions across all market actors,
in a way that is accessible to non-technical participants.

DFØ is currently developing next-generation guidance for innovative procurement,
including cross-agency and cross-border collaborative processes. We believe
CommDocs could provide relevant infrastructure for this work, and we are open
to exploring collaboration and piloting during the project period.

[Name], [Title]
Direktoratet for forvaltning og økonomi (DFØ)
```

---

*Søknadsutkast – ikke for offentlig distribusjon. Sist oppdatert: 2026-05-24.*
