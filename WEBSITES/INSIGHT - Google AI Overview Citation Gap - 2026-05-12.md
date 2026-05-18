---
created: 2026-05-12
status: developing
tags:
  - note/insight
  - status/developing
  - topic/marketing
  - topic/seo
  - topic/websites
  - topic/discoverability
  - brand/anthonyhorng
related:
  - "[[00 - START HERE]]"
  - "[[SESSION CAPTURE - 2026-05-12 - Cleanup and SEO Discovery]]"
  - "[[MASTER PLAN - Marketing System - Anthony Horng - v2 - 2026-04-18]]"
  - "[[SERP Analysis - Quebec Animateur Queries - 2026-05-12]]"
  - "[[SERP Analysis - Quebec Maître de Cérémonie Queries - 2026-05-12]]"
  - "[[SCREEN SHOTS]]"
---

# INSIGHT — Google AI Overview Citation Gap
*2026-05-12 — Discovered when Anthony ran a local Google search for "animateur bilingue" from Sainte-Catherine-de-la-Jacques-Cartier, Quebec, during SERP analysis work.*

---

## THE DISCOVERY IN ONE PARAGRAPH

Google AI Overview is the new top-of-page on Google searches. For "animateur bilingue" run from Anthony's Quebec location on 2026-05-12, the AI Overview names specific entities as recognized bilingual MCs: **Mike Tobin, Katerine Rollet, Anika Lirette**, and agencies **Eklosion** and **Scarlett Entertainment**. Anthony Horng is not in the citation set. This is a separate problem from organic ranking — even when animateur.ca ranks well (#4 on "animateur bilingue Québec"), the AI Overview that appears above the organic results doesn't cite him. The strategic implication: classical SEO (organic rankings) and generative SEO (AI Overview citation) are now two distinct pillars. The post-MUDGIRL rebuild of animateur.ca must address both.

---

## THE EVIDENCE

**Screenshot 1** (in [[SCREEN SHOTS]]): Google AI Overview for "animateur bilingue" cites:
- Mike Tobin — Maître de cérémonie, animateur dynamique (français/anglais)
- Katerine Rollet — Animatrice de congrès, colloques, et galas à Montréal/Québec
- Anika Lirette — Animation bilingue pour des événements culturels et institutionnels
- Agences spécialisées: Eklosion, Scarlett Entertainment

**Screenshot 2** (in [[SCREEN SHOTS]]): Organic top 4 for same query (Anthony's local IP):
1. Eklosion — service page
2. Master D Productions — animation bilingue En-Fr
3. Agence Speak — blog post "L'animatrice bilingue: un must!" (note: BLOG post, not service page)
4. Katerine-Lune Rollet — dedicated service page

Anthony is absent from both the AI Overview and the visible organic top 4 on this query without geographic qualifier. He returns to #4 organic when "Québec" is added to the query (per [[SERP Analysis - Quebec Animateur Queries - 2026-05-12]]).

---

## THE MECHANISM — Why competitors are cited and Anthony is not

The entities cited in the AI Overview share specific signals that Google AI uses to recognize them as legitimate, structured, authoritative answers to the query:

**Mike Tobin** — runs a **multi-domain strategy**: animateurbilingue.ca (the literal keyword as domain), bilingualmc.ca (English keyword as domain), iamgmmc.com (brand/persona domain). Three sites targeting three keyword clusters. Each domain is a clear topical signal to Google.

**Katerine-Lune Rollet** — has **blog content with topical authority**. Articles like "Une animatrice bilingue? Oui! - Montréal" feed Google AI as a citation source. The blog is the mechanism — she's not just listing services, she's producing content that answers the query.

**Anika Lirette** — has a **dedicated keyword-targeted page** with structured author identity (`/animation-bilingual-host` slug).

**Eklosion** — uses **BreadcrumbList + Person schema markup** to feed structured data to Google. Per [[SERP Analysis - Quebec Animateur Queries - 2026-05-12]] Part C, their service pages have schema; animateur.ca does not.

**Anthony Horng** has none of these:
- One domain (animateur.ca) — generic, no keyword targeting
- No blog content feeding topical authority
- Homepage `<title>` still says "motivational speaker" (deprecated language per [[MASTER PLAN - Marketing System - Anthony Horng - v2 - 2026-04-18]])
- No schema markup detected
- 5+ year old content with no recency signals

The site ranks #4 on the main keyword **on domain authority alone**. The structural and content signals that drive AI Overview citation are absent.

---

## THE STRATEGIC SHIFT — Two pillars, not one

Until this discovery, the assumption was that "winning on Google" meant winning organic rankings. The data shows that's no longer sufficient. The post-MUDGIRL rebuild of animateur.ca (and the parallel build of [[holdtheroom.com]] / discoverability work on [[anthonyhorng.com]]) must address both pillars:

### Pillar 1 — Classical SEO (organic ranking)

- Service-page architecture (dedicated pages per keyword cluster)
- URL slug matching (`/animateur-bilingue/`, `/maitre-de-ceremonie/`, etc.)
- Title + H1 + meta keyword targeting
- BreadcrumbList + Person + LocalBusiness schema markup
- Content depth (match Eklosion's medium-depth pages or exceed)
- Internal linking
- Geographic qualifiers in copy and structure

### Pillar 2 — Generative SEO (AI Overview citation)

- **Named-entity authority** — consistent NAP (name, address, phone) across sites; structured Person schema with credentials, services, locations
- **Topical authority blog** — the Katerine-Lune Rollet and Agence Speak play. Blog content that answers MC-related queries directly, written from a clear author identity. This is content marketing as SEO infrastructure, not as engagement play.
- **External citations** — getting Anthony's name mentioned on news sites, agency rosters, association pages, conference speaker bios, etc. Google AI cites entities that are referenced elsewhere as authorities.
- **Q&A-style content** — pages structured around questions the AI might be asked to answer ("Comment choisir un animateur bilingue?", "Quelle est la différence entre un animateur et un maître de cérémonie?")
- **Multi-domain consideration** — is the Mike Tobin pattern (animateurbilingue.ca + bilingualmc.ca + animateur.ca) worth replicating? Or does it dilute authority? Open question.

The two pillars work differently but reinforce each other. Strong organic rankings increase the chance of AI citation. Strong AI citation drives traffic that improves organic ranking signals. They're not independent — they're a flywheel.

---

## IMPLICATIONS FOR THE REBUILD

The discoverability spec — the next deliverable per [[00 - START HERE]] — must address both pillars explicitly.

What this changes about the rebuild scope:

1. **A blog is no longer optional.** Previous design study work treated content as nice-to-have. The AI Overview data shows it's structural. The rebuild must include a blog plan — topics, cadence, author identity, distribution.

2. **Schema markup is mandatory.** Not a polish item. A core requirement. Without it, animateur.ca cannot compete with Eklosion structurally regardless of how good the design is.

3. **External citations need a strategy.** Getting Anthony's name on third-party authoritative sites is part of the spec. This isn't traditional "link building" — it's entity recognition building. Different work.

4. **The "personal brand hub" framing of anthonyhorng.com gains importance.** Per [[INSIGHT - anthonyhorng.com Is a Practitioner's Personal Site - 2026-04-19]], anthonyhorng.com is structured as a practitioner's home. That structure also serves entity recognition — a consistent author identity across both sites strengthens the named-entity signal Google AI uses.

5. **Multi-domain question needs a decision.** Mike Tobin's three-domain play is sophisticated. Do we replicate it (registering keyword-matching domains and redirecting/duplicating)? Or does Anthony's two-site architecture (animateur.ca FR + anthonyhorng.com EN) handle it? Decision deferred to the spec.

---

## WHAT'S NOT YET KNOWN

This discovery opens questions the spec will need to answer:

- **AI Overview behavior is still evolving.** Google is iterating fast. What works in May 2026 may not work in September. Spec needs to identify principles, not just tactics.
- **Search volume data** for the queries in [[SERP Analysis - Quebec Animateur Queries - 2026-05-12]] and [[SERP Analysis - Quebec Maître de Cérémonie Queries - 2026-05-12]] is not yet collected. Manus could not access keyword volume tools. Without volume, prioritization is partial.
- **The multi-domain decision** requires research into how Google AI treats domain consolidation vs distribution.
- **The blog cadence question** — Katerine-Lune Rollet's blog appears infrequent but topical. Agence Speak's blog appears more regular. Which model fits Anthony's capacity?
- **The external citation strategy** — what specifically: press mentions, agency rosters, association memberships, conference bios, podcast appearances. Needs a concrete list.

---

## RELATED FILES

- [[00 - START HERE]] — folder orientation, governing files, next-action pickup
- [[SESSION CAPTURE - 2026-05-12 - Cleanup and SEO Discovery]] — full record of the session this insight emerged in
- [[SERP Analysis - Quebec Animateur Queries - 2026-05-12]] — Round 1 (animateur queries)
- [[SERP Analysis - Quebec Maître de Cérémonie Queries - 2026-05-12]] — Round 2 (MC queries)
- [[SCREEN SHOTS]] — AI Overview + organic SERP screenshots
- [[MASTER PLAN - Marketing System - Anthony Horng - v2 - 2026-04-18]] — needs update to add 8th component (discoverability) or fold into Component 1
- [[REBUILD BRIEF - Strategic Experience Design Pitch for MC Services]] — vocabulary standard applies to all spec output
- [[DESIGN STUDY - anthonyhorng.com and holdtheroom.com Site Architecture Exploration - 2026-04-19]] — Prototype 4 is the closest structural model; needs discoverability layer added

---

## USAGE LOG

- 2026-05-12 — Insight generated during SERP analysis session. The local-search screenshot Anthony took surfaced the AI Overview gap that desk-research had missed.
