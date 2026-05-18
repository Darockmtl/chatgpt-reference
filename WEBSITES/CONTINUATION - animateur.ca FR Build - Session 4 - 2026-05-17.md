# CONTINUATION — animateur.ca FR Build — Session 4 — 2026-05-17
*Handoff for next Claude instance. Read this file in full BEFORE doing anything else.*

---

## YOUR FIRST MOVES (in this order, do not skip)

1. **Load filesystem tools** — they are deferred. Run three `tool_search` calls:
   - `tool_search` for "read file filesystem"
   - `tool_search` for "list directory search files vault"
   - `tool_search` for "filesystem write_file"

2. **Read this file in full.** You're doing this now.

3. **Read the BUILD LOG in full.**
   Path: `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/11 - Marketing & Brand/WEBSITES/BUILD LOG - animateur.ca FR via MCP - 2026-05-17.md`

4. **Read the project context files at vault root:**
   - `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/REFERENCE - Anthony Horng Project Context.md`
   - `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/CLAUDE.md`

5. **Quote the hard rules back to Anthony** before proceeding. Confirm understanding.

6. **Ask Anthony which task he wants to tackle first** from the "Pending tasks" list below.

---

## HARD RULES (NON-NEGOTIABLE — VIOLATING ANY OF THESE BREAKS TRUST)

### Vocabulary rules
1. NO em dashes anywhere. Commas or pipes.
2. NO "amont". Eklosion vocabulary — never use.
3. NO "ce soir-là". Use "avant le jour J".
4. NO "moitié francophone, moitié anglophone". Use "les deux langues doivent compter".
5. NO "pas un exécutant de programme". Use "le partenaire de confiance".
6. NO "pas livré la veille". Cut.
7. NO "ne pensent pas à poser". Cut.
8. NO "préparer le programme". Anthony prepares the texte d'animation. Client owns the program.
9. NO "script" in French. Use "texte d'animation".
10. NO copy from anthonyhorng.com or Eklosion.
11. NO Yoast meta from guess. Read SERP files first.
12. NO inventing competitor failure patterns.
13. NO lines beyond what was approved. Write the approved thing, nothing adjacent.
14. When in doubt: cut.

### Attribution rules (Session 3 additions)
15. **Use the role held at time of engagement, NOT current LinkedIn title.** Example: Jennifer Nadro stays attributed to "Coordonnatrice, communications et marketing philanthropique, Moisson Laurentides" even though she has since moved to Cora.
16. **Borea Construction has NO accent.** Verified against their actual brand. The proof bank wrote "Boréa" but that is wrong.
17. **Permission must be explicit and verifiable BEFORE using any testimonial publicly.**
   - LinkedIn recommendations are public/approved.
   - Filed Getformly responses with explicit permission are approved.
   - Internal sources (Fireflies transcripts, Gmail, Formly internal feedback) are NOT permission — data only.
   - Respect permission granularity. Roxanne (Niché) granted "prénom seulement" — never write "Roxanne Bacha" or "Niché" publicly.

### Working rules
18. **Take corrections without re-arguing.**
19. **When Anthony pushes back, re-examine using the right tools — don't just restate the claim.** Search the vault, read the actual pages, verify. Hold the line only if verification confirms you were right.
20. **Don't be lazy. If asked to research, research ALL items in the list — not just the ones flagged.** Sloppy partial work is worse than no work.
21. **Show before writing. Wait for explicit confirmation. Write using `filesystem:write_file` with full content. Read back to verify.**

---

## CURRENT STATE — WHAT IS DONE

### WordPress draft pages (all 5 in `draft` status, NOT published)
| Page ID | Slug | URL preview | Status |
|---|---|---|---|
| 4535 | accueil-fr | animateur.ca/fr/?page_id=4535 | Body copy DONE |
| 4536 | animateur-corporatif | animateur.ca/fr/?page_id=4536 | Body copy DONE |
| 4537 | animateur-gala | animateur.ca/fr/?page_id=4537 | Body copy DONE |
| 4538 | animateur-bilingue | animateur.ca/fr/?page_id=4538 | Body copy DONE |
| 4539 | animateur-congres | animateur.ca/fr/?page_id=4539 | Body copy DONE |

### What's on every page
- H1 + intro
- Service-specific section (varies by page)
- Locked 3-step process section (Découvrir / Concevoir / Livrer) — IDENTICAL on all 5
- Testimonials section ("Ce qu'ils en disent") — 3 quotes per page, all permission-verified
- Trust list ("Ils lui ont fait confiance" / "Des organisations qui lui font confiance") — text placeholder, 12 orgs
- CTA section with inquiry button → links to `#formulaire` anchor

### Homepage 4535 only
- MUDGIRL credential between process section and testimonials: "Animateur attitré des événements MUDGIRL à travers le Canada. Plus de 60 000 participantes chaque année."
- Form placeholder at bottom (anchor `#formulaire`): "[Formulaire de demande à intégrer]"

### Yoast SEO meta on all 5 pages
Written and confirmed. See BUILD LOG for full mapping. Focus keywords: animateur bilingue Québec / animateur corporatif Montréal / gala de reconnaissance / animateur bilingue Montréal / maître de cérémonie congrès.

### Testimonials filed to vault
- `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/13 - Testimonials & Results/TESTIMONIAL - Natacha Laflamme - MTY Group - Sushi Shop - 2026-04-10.md`
- `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/13 - Testimonials & Results/TESTIMONIAL - Roxanne - Niché - 2026-03-24.md`

### Trust list (12 orgs, used as text placeholder on all 5 pages)
Radio-Canada · Patrimoine canadien · TELUS Santé · Sushi Shop · Compétences Canada · Spartan Race Canada · Tandem Communication · MUDGIRL · RCCAQ · SP Canada · Borea Construction · Moisson Laurentides

**Verified display names:**
- Radio-Canada (not "Société Radio-Canada")
- Patrimoine canadien (federal department; alternative "Fête du Canada" is the event name)
- TELUS Santé (NOT "TELUS Health" in French)
- Sushi Shop (NOT "Groupe MTY" — engagement was Sushi Shop franchisees, brand recognition is stronger)
- Compétences Canada (the Quebec FR form of Skills/Compétences Canada)
- Spartan Race Canada
- Tandem Communication (full corporate name: Tandem communication événementielle)
- MUDGIRL (= Sport-ERA — same company, do not list both)
- RCCAQ (acronym is their brand; full: Regroupement des cabinets de courtage d'assurance du Québec)
- SP Canada (rebranded from Société canadienne de la sclérose en plaques)
- Borea Construction (NO accent — verified)
- Moisson Laurentides

---

## PENDING TASKS (in priority order)

### Task 1 — Logo grid implementation (highest priority, blocks site publish)

**Current state:** trust list is a TEXT paragraph on all 5 pages. The 12 orgs are listed text-only with " · " separator.

**Goal:** Convert to a clean image grid (3×4 or 4×3) showing actual logos.

**Steps:**
1. Anthony uploads 12 logo image files to WP Media Library. The existing live English animateur.ca has many of these already — they may already be in the library. Check first.
2. Get each logo's attachment ID and URL from the Media Library.
3. Replace the text paragraph on all 5 pages with a Gutenberg gallery or columns block displaying the logos.
4. Use consistent sizing. Greyscale or color is Anthony's call.

**Where the logos exist on the live English site (URLs for reference):**
- MUDGIRL: `https://animateur.ca/wordpress/wp-content/uploads/2020/06/mudgirl-copy.jpg`
- Patrimoine canadien: `https://animateur.ca/wordpress/wp-content/uploads/2020/06/patrimoine.jpg`
- RCCAQ: `https://animateur.ca/wordpress/wp-content/uploads/2020/06/rccaqjpg12.jpg`
- SP: `https://animateur.ca/wordpress/wp-content/uploads/2020/06/sp-logo-Modifier-1jpg13.jpg`
- Spartan Race: `https://animateur.ca/wordpress/wp-content/uploads/2020/06/spartan-race-logo-Modifierjpg14.jpg`
- Tandem: `https://animateur.ca/wordpress/wp-content/uploads/2020/06/logo_tandem-communication-evenementielle-Modifierjpg07.jpg`
- Radio-Canada: `https://animateur.ca/wordpress/wp-content/uploads/2020/06/radio-canadajpg11.jpg`

**Need to source new logos for:**
- TELUS Santé
- Sushi Shop (or Groupe MTY)
- Compétences Canada
- Borea Construction
- Moisson Laurentides

**Note:** Existing live site logos are 6 years old, possibly low-res for retina screens. Anthony's call whether to use existing or upload fresh.

---

### Task 2 — Zoho Forms embed on homepage

**Current state:** Page 4535 has placeholder: `<em>[Formulaire de demande à intégrer]</em>` inside the section with anchor `#formulaire`.

**Goal:** Replace placeholder with Zoho Forms iframe embed.

**Blocker:** Anthony needs to provide the Zoho Forms URL or embed code.

**Buttons on pages 4536-4539** all link to `/fr/#formulaire` (homepage anchor). Once the form is embedded on the homepage, this routing works automatically.

---

### Task 3 — Reel embed on homepage

**Current state:** No video on the homepage yet.

**Goal:** When Anthony's bilingual reel drops, embed it on the homepage between the hero section and the service columns, or wherever Anthony specifies.

**Blocker:** Reel not yet delivered. Was targeted around May 8 — confirm current status with Anthony.

---

### Task 4 — Polylang language linking

**Current state:** All 5 FR pages are tagged "Français" in Polylang, but NOT yet linked to their English equivalents.

**Goal:** At publish time (not before), link each FR page to its corresponding EN Elementor page on the live site.

**Anthony does this manually in WP admin via Polylang's language metabox on each page. Do not do this before publish.**

---

### Task 5 — File Emma Blomdahl testimonial to vault

**Status:** Emma's Getformly response (BDC, 2026-03-18) is in chat uploads only. She granted full public-use permission. Quote was deemed too generic to use on the new pages but may be useful for social media or future use.

**Action:** Save to `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/13 - Testimonials & Results/TESTIMONIAL - Emma Blomdahl - BDC - 2026-03-18.md` following the same format as Natacha and Roxanne's files.

**Source data is in this session's HTML upload — Anthony may need to re-upload OR the next instance asks for it.** The content was:
- Name: Emma Blomdahl
- Title: BDC (district manager)
- Email: em.blomdahl@gmail.com
- Quote: "He is passionate and engaging"
- Rating: 5/5
- Permission: "Yes" for site, social, proposals
- Marketing opt-in: "Yes"

---

### Task 6 — Plugin cleanup (low priority, do after publish + stability)

- Delete `Connect Polylang for Elementor` (inactive, not needed in current architecture)
- Delete `TranslatePress` (inactive, conflicts with Polylang if activated)

---

### Task 7 — PHP 7.4 upgrade (security flag, separate from website work)

- Server is HostGator. PHP 7.4 reached EOL November 2022.
- Anthony to contact HostGator to upgrade to PHP 8.1+.
- Not blocking current work but should happen within weeks.

---

### Task 8 — Blog strategy (deferred, not yet scoped)

- Topical authority + Google AI Overview citation play. See `INSIGHT - Google AI Overview Citation Gap - 2026-05-12.md` in the WEBSITES folder for context.
- Not in scope until post-launch.

---

## LOCKED COPY (DO NOT MODIFY WITHOUT EXPLICIT INSTRUCTION)

### Homepage hero (page 4535)
> H1: L'animateur bilingue qui entre dans votre événement avant le jour J
> Subtitle: Le partenaire de confiance pour vos événements à enjeux.

### Process section (on all 5 pages, identical)
> H2: La co-création se fait en trois temps.
>
> **Découvrir.** Vous savez ce que votre événement doit accomplir, au-delà du programme. Pas ce qui doit être dit. Ce qui doit être compris. Anthony pose les questions sur votre intention réelle, le message qui doit traverser, ce que votre salle doit emporter avec elle.
>
> **Concevoir.** Vous savez ce qui va se passer sur scène avant le jour J. Le texte d'animation est construit avec vous. Chaque transition, chaque introduction, chaque moment de passage sert votre intention.
>
> **Livrer.** Vous savez que votre événement est entre bonnes mains, peu importe ce qui arrive. Les imprévus se gèrent sans que vos invités le ressentent. Votre équipe peut se concentrer sur le reste.

### Bilingual framing (homepage and page 4538)
> Quand les deux langues doivent compter dans la même salle, l'animateur bilingue n'est pas un atout. C'est une nécessité.

### MUDGIRL credential (homepage only, page 4535)
> Animateur attitré des événements MUDGIRL à travers le Canada. Plus de 60 000 participantes chaque année.

### Approved vocabulary
crédibilité · co-création · intention · texte d'animation · enjeux · ressentir · "avant le jour J" · "le partenaire de confiance" · "les deux langues doivent compter"

---

## TESTIMONIAL SOURCES — WHAT IS ON WHICH PAGE

| Page | Quote 1 | Quote 2 | Quote 3 |
|---|---|---|---|
| 4535 home | Peter Trang, PDG, Les Aliments Crystal | Natacha Laflamme, Gestionnaire marketing et numérique, MTY Food Group — Sushi Shop | Mélodie Lespérance, Réseau d'agriculture urbaine de Québec |
| 4536 corporatif | Chanelle Turgeon Gervais, Borea Construction | Natacha Laflamme, MTY Food Group — Sushi Shop | Pierre Michaud, Directeur général |
| 4537 gala | Jennifer Nadro, Coordonnatrice, communications et marketing philanthropique, Moisson Laurentides | Nima Jalalvandi, PDG, Ready Plan Go | David Lepage |
| 4538 bilingue | Chloé Larocque, Borea Construction | Roxanne (prénom seulement) | Barb Stegemann, CBC Dragons' Den |
| 4539 congrès | Roel Frissen, Cofondateur, Event Design Collective | Nadine Menard, propriétaire, SUITE22 | Richard Rampersad |

---

## MCP CONNECTION

- **URL:** `https://animateur.ca/wp-json/easy-mcp-ai/v1/mcp`
- **Auth:** OAuth via WordPress login, already connected on claude.ai web
- **Force Draft on Create:** ENABLED
- **Tool available to update pages:** `wp_update_page` — takes `page_id` + `content` (full content replacement, no patching)
- **Tool to read pages:** `wp_get_page` — takes `page_id`
- **Yoast meta:** `wp_yoast_update_post_seo` and `wp_yoast_get_head`

**If Yoast or other tools don't load:** disconnect and reconnect the animateur.ca connector in Claude.ai Settings → Connectors to reload tool registry.

---

## ROLLBACK PROTOCOL

If the site breaks:
1. Deactivate most recently changed plugin
2. If still broken: deactivate Polylang and Easy MCP AI
3. If still broken: restore from UpdraftPlus (Settings → UpdraftPlus Backups → Restore)
4. Backup location locally: `/Volumes/main/BACKUP WEBSITE` (taken 2026-05-17)

---

## FILES THE NEXT INSTANCE WILL NEED

| File | Why |
|---|---|
| This file (the continuation) | First read |
| `BUILD LOG - animateur.ca FR via MCP - 2026-05-17.md` | Full history of decisions and state |
| `REFERENCE - Anthony Horng Project Context.md` | Anthony's standing operating context |
| `CLAUDE.md` at the vault root + the personae folder | Standing rules |
| `00 - START HERE.md` in this WEBSITES folder | Project orientation for websites work |
| `PROOF BANK - MC Work - Anthony Horng - 2026-03-29.md` at `/Users/MC/MACMINIVAULT/MACMINI1/ZZ-Claude-Projects/ICP Coaching MC Work/` | Source of truth for all testimonial proof points and permission status |
| `13 - Testimonials & Results/` folder | Filed Getformly responses (Natacha, Roxanne) |
| `SERP Analysis - Quebec Animateur Queries - 2026-05-12.md` and `SERP Analysis - Quebec Maître de Cérémonie Queries - 2026-05-12.md` in this folder | SEO reference, do not re-run |

---

## DO NOT

- Do not publish any of the 5 pages without explicit instruction from Anthony.
- Do not delete the live English site or any existing Elementor content.
- Do not touch the proof bank file (read-only reference).
- Do not modify locked vocabulary or hero/process/bilingual sections without explicit request.
- Do not assume permission for testimonial sources — verify each one against the proof bank's approval tags or filed Getformly responses.
- Do not pull from internal Fireflies/Gmail/Formly internal feedback for public copy.
- Do not get defensive when Anthony pushes back. Re-examine using the right tools.
- Do not write long files. Anthony reads carefully and catches sloppy work fast.
