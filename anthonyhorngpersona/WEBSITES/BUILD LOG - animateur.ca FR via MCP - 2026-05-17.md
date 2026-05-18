---
created: 2026-05-17
type: build-log
status: active
tags:
  - note/reference
  - status/active
  - topic/websites
  - topic/animateur-ca
  - brand/anthonyhorng
---

# BUILD LOG — animateur.ca French Version via MCP
*Live log of the French version build on animateur.ca using Claude MCP connection. Add to this file as work progresses.*

---

## PROJECT GOAL

Build a French version of animateur.ca at `animateur.ca/fr` while leaving the live English site untouched.

**The French version is not a translation.** It's a completely new layout in Quebec French — and it doubles as the prototype for the eventual full site rebuild post-MUDGIRL season.

Stays as drafts until ready to publish. Live English site continues running on Elementor v3 architecture, untouched.

---

## ARCHITECTURE DECISION (locked 2026-05-17)

**The split:**
- **English pages:** Elementor (existing, unchanged)
- **French pages:** Gutenberg (standard WordPress blocks), no Elementor
- **Polylang:** handles `/fr` URL routing only — not used to "translate" Elementor pages
- **Connect Polylang for Elementor:** STAYS INACTIVE (not needed in this architecture)

**Why this split:** The bridge plugin Connect Polylang for Elementor has documented current issues with Elementor 4.x (forum reports within last month — "Critical error", "conflicts with the latest version of Elementor Pro"). Building French pages outside Elementor sidesteps the entire Polylang-Elementor compatibility problem. Polylang's only job here is URL structure and language switching.

**Long-term implication:** When the post-MUDGIRL rebuild happens, the English site can also move to Gutenberg — dropping Elementor entirely. Fewer dependencies, faster pages, less to break.

---

## SERVER + PLUGIN STATE (as of 2026-05-18)

| Item | Value | Status |
|---|---|---|
| WordPress | 6.9.4 | ✓ Current |
| Elementor | 4.0.8 | ✓ Current (V4 Atomic Editor — released March 2026) |
| PHP | 8.1 (ea-php81) — upgraded 2026-05-18 during 500 recovery | ✓ |
| UpdraftPlus | Installed + backup taken + downloaded locally 2026-05-17 | ✓ |
| Easy MCP AI | Installed + activated 2026-05-17. Yoast SEO tools 3/3 enabled. | ✓ |
| Polylang | 3.8.3 — installed and active, directory-based, FR at /fr/ | ✓ |
| Connect Polylang for Elementor | Installed but inactive | Stays inactive |
| TranslatePress | Installed but inactive | Stays inactive — never activate alongside Polylang |
| Languages menu in admin | French added as secondary language | ✓ |

---

## FLAGS — Things to handle, not now

**PHP upgraded to 8.1 — 2026-05-18.** Upgraded during 500 recovery. All 7 active plugins confirmed stable on 8.1. Flag closed.

**Multiple unused multilingual plugins installed.**
- Connect Polylang for Elementor + TranslatePress both sit inactive
- Suggests previous multilingual attempts that were rolled back partially
- Recommendation: delete both once project stable — but only after we know everything works without them

---

## MCP CONNECTION DETAILS

- **MCP URL:** `https://animateur.ca/wp-json/easy-mcp-ai/v1/mcp`
- **Authentication:** OAuth via WordPress login (no API token needed for claude.ai web)
- **Force Draft on Create:** ENABLED
- **Connected from:** claude.ai web (Settings → Connectors → Add custom connector)
- **Note:** After enabling new plugin tools in Easy MCP AI, the connector must be disconnected and reconnected in Claude.ai to reload the tool registry. Confirmed working for Yoast tools 2026-05-17.

**What Claude can do via MCP:**
- Read all posts, pages, media, settings
- Create new posts/pages (forced to draft)
- Update content
- Manage taxonomies and menus
- Read and write Yoast SEO meta (seo_title, meta_description, focus_keyword, OG, Twitter) via wp_yoast_update_post_seo
- Read rendered SEO head for any URL via wp_yoast_get_head

**What Claude cannot touch:**
- Existing Elementor pages (different storage format, not edited via MCP)
- Existing English content unless explicitly authorized in chat

---

## YOAST SEO META — 5-PAGE BUILD (completed 2026-05-17)

**Strategy:** B (Mixed). Compete with Eklosion where within reach. Capture open SERPs where Eklosion is absent or weak. Discrete posture — no visible signals of competition while still working with Eklosion in the same Quebec market.

**Keyword mapping and meta — all written via MCP, confirmed:**

| Page ID | Slug | Focus Keyword | SEO Title | Meta Description |
|---|---|---|---|---|
| 4535 | accueil-fr | animateur bilingue Québec | Animateur bilingue au Québec | Anthony Horng, MC | Animateur bilingue au Québec depuis 20 ans. Anthony Horng entre dans votre événement avant le jour J. Le partenaire de confiance pour vos enjeux. |
| 4536 | animateur-corporatif | animateur corporatif Montréal | Animateur corporatif Montréal | Anthony Horng, bilingue | Animateur corporatif à Montréal, bilingue français-anglais. Anthony Horng entre dans votre événement avant le jour J. 20 ans d'expérience corporative. |
| 4537 | animateur-gala | gala de reconnaissance | Animateur de gala de reconnaissance, Québec | Anthony Horng | Animateur de gala de reconnaissance au Québec, bilingue. Anthony Horng conçoit avec vous le texte d'animation de votre soirée de remise de prix avant le jour J. |
| 4538 | animateur-bilingue | animateur bilingue Montréal | Animateur bilingue à Montréal | Anthony Horng | Animateur bilingue à Montréal, 20 ans d'expérience. Anthony Horng entre dans votre événement avant le jour J pour que les deux langues comptent dans la salle. |
| 4539 | animateur-congres | maître de cérémonie congrès | Maître de cérémonie de congrès au Québec | Anthony Horng | Maître de cérémonie de congrès et sommets professionnels au Québec. Anthony Horng entre dans votre événement avant le jour J, bilingue français-anglais. |

**Polylang language assignment:** all 5 pages set to Français via bulk edit 2026-05-17.

---

## BODY CONTENT — 5-PAGE BUILD (completed 2026-05-17, Session 3)

**Locked vocabulary applied across all 5 pages:**
- Hero: "L'animateur bilingue qui entre dans votre événement avant le jour J" / "Le partenaire de confiance pour vos événements à enjeux."
- Process section: Découvrir / Concevoir / Livrer (locked, identical on all 5 pages)
- Bilingual framing: "Quand les deux langues doivent compter dans la même salle..."
- No em dashes. No "script" (texte d'animation). No "amont". No Eklosion vocabulary.

**MUDGIRL credential (homepage only, 4535):**
> Animateur attitré des événements MUDGIRL à travers le Canada. Plus de 60 000 participantes chaque année.

**Trust list — applied to all 5 pages (text placeholder, logos pending upload):**
Radio-Canada · Patrimoine canadien · TELUS Santé · Sushi Shop · Compétences Canada · Spartan Race Canada · Tandem Communication · MUDGIRL · RCCAQ · SP Canada · Borea Construction · Moisson Laurentides

**Organization research completed 2026-05-17:**
- All 12 org names verified against official sources
- Borea: accent dropped (official brand is "Borea Construction", not "Boréa")
- Skills Canada: displayed as "Compétences Canada" for Quebec FR audience
- SP Canada: rebranded from "Société canadienne de la sclérose en plaques"
- Sport-ERA confirmed = MUDGIRL event company — removed from list to avoid redundancy

**Testimonials — 3 per page, all sources verified for public-use permission:**

| Page | Source 1 | Source 2 | Source 3 |
|---|---|---|---|
| 4535 accueil-fr | Peter Trang, PDG, Les Aliments Crystal (LinkedIn rec, EN→FR) | Natacha Laflamme, Gestionnaire marketing et numérique, MTY Food Group — Sushi Shop (Getformly, FR) | Mélodie Lespérance, Réseau d'agriculture urbaine de Québec (LinkedIn rec, FR) |
| 4536 corporatif | Chanelle Turgeon Gervais, Borea Construction (case study, approved, FR) | Natacha Laflamme, MTY Food Group — Sushi Shop (Getformly, FR) | Pierre Michaud, Directeur général (LinkedIn rec, FR) |
| 4537 gala | Jennifer Nadro, Coordonnatrice, communications et marketing philanthropique, Moisson Laurentides (LinkedIn rec, FR) | Nima Jalalvandi, PDG, Ready Plan Go (LinkedIn rec, EN→FR) | David Lepage (LinkedIn rec, FR) |
| 4538 bilingue | Chloé Larocque, Borea Construction (case study, approved, FR) | Roxanne (Getformly, FR — prénom seulement per permission) | Barb Stegemann, CBC Dragons' Den (LinkedIn rec, EN→FR) |
| 4539 congrès | Roel Frissen, Cofondateur, Event Design Collective (LinkedIn rec, EN→FR) | Nadine Menard, propriétaire, SUITE22 (LinkedIn public post, FR — industry endorsement, not client) | Richard Rampersad (LinkedIn rec, EN→FR) |

**Permission rules applied:**
- LinkedIn recs tagged "Public. Approved." → full name + title + org
- Getformly Natacha Laflamme → full name + title + org (explicit permission)
- Getformly Roxanne Bacha → prénom seulement ("Roxanne") per her instruction
- Getformly Emma Blomdahl (BDC) → permission granted, not used on pages (quote too generic)
- Internal sources (Fireflies, Gmail) → not used publicly without separate permission
- TELUS Santé → in trust list only; testimonial proof point still pending post-event approval
- Nadine Menard / SUITE22 → industry endorsement (not a client); org not in trust list

**4539 intro fix applied:** "pas un passeur de micro" → "le partenaire de confiance qui donne de la cohérence à l'ensemble"

---

## TESTIMONIAL FILES FILED (vault: 01.ANTHONY HORNG PERSONAE/13 - Testimonials & Results/)

| File | Source | Permission |
|---|---|---|
| TESTIMONIAL - Natacha Laflamme - MTY Group - Sushi Shop - 2026-04-10.md | Getformly client form | Nom complet + titre |
| TESTIMONIAL - Roxanne - Niché - 2026-03-24.md | Getformly producteur form | Prénom seulement |

Emma Blomdahl (BDC, Getformly attendee form, 2026-03-18) — permission granted, not yet filed to vault. Still in chat uploads only.

---

## LOGO GRID — FINAL LINEUP (Sessions 4–5)

### Row 1 — square / tall anchors
| Org | Media ID | File |
|---|---|---|
| Radio-Canada | 4584 | gem-red-rouge.png |
| MUDGIRL | 4581 | mudgirl.jpg |
| The Idea Hunter | 4598 | the-idea-hunter-logo-1.png |
| Compétences Canada | 4587 | SCC_logo_black-210x101-1.png |

### Row 2 — medium rectangle with icon
| Org | Media ID | File |
|---|---|---|
| Patrimoine canadien | 4591 | patrimoine-canada-logo-png_seeklogo-463872.png |
| RCCAQ | 4583 | RCCAQ.png |
| Moisson Laurentides | 4579 | Moisson_Laurentides_idKKmW06fq_1.png |
| Cancers du sang | 4600 | llsc-logo-fr.svg |

### Row 3 — horizontal wordmark
| Org | Media ID | File |
|---|---|---|
| TELUS Santé | 4589 | TELUS_Sante_id1geKKXck_1.svg |
| Sushi Shop | 4588 | Sushi_Shop_idXxZWffNp_1.svg |
| Tandem Communication | 4585 | TANDEM_logos.png |
| SP Canada (FR) | 4599 | sp-canada-logo-black-fr.svg |

### Dropped from grid (still in media library, do not use)
- **4586** — Spartan-Race-Logo-Vector.svg (signals sports/entertainment MC, not strategic partner; MUDGIRL covers large-scale sporting proof)
- **4580** — borea-fbshare-removebg-preview.png (not recognizable to senior comms/events ICP; Borea testimonials remain on pages 4536 and 4538)
- **4582** — MS-SP-CANDA-logo-black.svg (English version of SP Canada, replaced by FR version 4599)
- **4590** — TELUS_Sante_id1geKKXck_0.png (duplicate PNG; SVG 4589 is canonical)

### Current CSS (published in WP Customizer → Additional CSS)

```css
.wp-block-columns .wp-block-image img {
  max-height: 60px !important;
  width: auto !important;
  object-fit: contain !important;
  margin: 0 auto !important;
  display: block !important;
}

.wp-block-columns .wp-block-image {
  display: flex !important;
  align-items: center !important;
  justify-content: center !important;
}
```

**Why this CSS is safe for the main English site:** The English site uses Elementor with `elementor-*` / `eael-*` class structure. Gutenberg's `.wp-block-columns .wp-block-image` selector does not match Elementor markup. Anthony verified this in Customizer preview before publishing — main site rendered unchanged.

**Why CSS only partially solves the problem:** Source images have wildly different native dimensions. CSS can cap height and align center but cannot make a square logo and a horizontal logo carry equal visual weight. Real fix: normalize all logos onto a consistent canvas before upload. Next step: Anthony resizes all 12 to 300×150px white background, logo centered with ~20px padding, export PNG.

---

## DECISION LOG

| Date | Decision | Reason |
|---|---|---|
| 2026-05-17 | Use Polylang + Gutenberg, not WPML, not TranslatePress | Free, lightweight, no AI translation needed (Claude writes French directly) |
| 2026-05-17 | French at `/fr`, not `fr.animateur.ca` subdomain | Same WP install, URL structure Anthony wanted |
| 2026-05-17 | Build live, not on staging | UpdraftPlus + Gutenberg-only French = bounded risk |
| 2026-05-17 | Easy MCP AI as MCP server plugin | Most complete free option, OAuth support, audit log, Force Draft setting |
| 2026-05-17 | Yoast SEO strategy B (Mixed) | Compete with Eklosion where within reach, capture open SERPs where absent |
| 2026-05-17 | 5-page focus keyword mapping locked | See YOAST SEO META section above |
| 2026-05-17 | Eklosion competition: discrete capture, not visible contest | Still working with Eklosion, same Quebec market, no public signals of competition |
| 2026-05-17 | Testimonials: LinkedIn recs + filed Getformly only for public pages | Internal Fireflies/Gmail sources not used publicly without separate permission |
| 2026-05-17 | Trust list: text placeholder on all 5 pages | Logo images not yet uploaded to WP Media Library — convert to image grid when ready |
| 2026-05-17 | MUDGIRL credential on homepage only | Scale signal; irrelevant to service-specific pages |
| 2026-05-17 | "Borea Construction" (no accent) | Verified against official brand; "Boréa" was incorrect |
| 2026-05-17 | Attribution rule: use role held at time of engagement, not current LinkedIn title | Avoids inflation, protects testimonial integrity (e.g. Jennifer Nadro stays at Moisson Laurentides though she has since moved to Cora) |
| 2026-05-17 | Spartan Race dropped from logo wall | Signals sports/entertainment MC, not strategic partner. MUDGIRL already covers large-scale sporting proof. |
| 2026-05-17 | Borea Construction dropped from logo wall | Not visually recognizable to senior comms/events ICP. Borea testimonials remain on pages 4536 and 4538. |
| 2026-05-17 | The Idea Hunter + Cancers du sang added to logo wall | Better ICP fit; Cancers du sang = FR brand version of LLSC |
| 2026-05-17 | SP Canada swapped to FR version (ID 4599) | English logo (ID 4582) on a French page was a mismatch. FR version uploaded and confirmed. |
| 2026-05-17 | Logo rows ordered by shape | Row 1: square/tall anchors. Row 2: medium with icons. Row 3: horizontal wordmarks. CSS alone could not normalize visual weight across aspect ratios. |
| 2026-05-17 | Source logo resizing accepted as next step | CSS normalization partial fix only. Real fix is consistent canvas (300×150, white background, logo centered) before upload. |

---

## NEXT STEPS

1. ~~Body content build per page~~ — DONE (Session 3)
2. **Logo grid** — grid built and CSS live (Session 4). Source logo resizing still needed before publish. Anthony resizes 12 logos to 300×150 white canvas → re-uploads → Claude reads new IDs → updates all 5 pages via wp_update_page.
3. Add greyscale CSS filter to Customizer CSS: `filter: grayscale(100%);` on logo images
4. Polylang: link each French page to its English equivalent — do at publish time, not before
5. Reel embed — when reel drops, embed on homepage French draft (page 4535)
6. Blog strategy — topical authority + AI Overview citation play — flagged, not yet scoped
7. ~~PHP 7.4 upgrade~~ — DONE (8.1 active as of 2026-05-18)
8. Delete Connect Polylang for Elementor + TranslatePress — once build stable post-launch
9. File Emma Blomdahl (BDC) testimonial to vault — pending
10. Getformly → Zoho CRM webhook — flagged for post-launch evaluation only. Do not touch until base launch is published.

---

## ROLLBACK PROTOCOL

If anything breaks the live site:

1. Deactivate the most recently installed/changed plugin
2. If still broken: deactivate Polylang and Easy MCP AI
3. If still broken: restore from UpdraftPlus backup (Settings → UpdraftPlus Backups → Existing Backups → Restore)
4. **Backup file location on local: `/Volumes/main/BACKUP WEBSITE`** (UpdraftPlus full backup taken 2026-05-17)

---

## USAGE LOG

- 2026-05-17 — File created at start of MCP setup session. Easy MCP AI installed and activated. UpdraftPlus full backup taken and downloaded locally to `/Volumes/main/BACKUP WEBSITE`. Awaiting OAuth connector setup and Polylang install.
- 2026-05-17 — Session 2. Polylang 3.8.3 installed and configured. 5 French draft pages created (IDs 4535-4539). Polylang language set to Français on all 5 via bulk edit. Yoast SEO tools enabled in Easy MCP AI (3/3). Connector reconnected to reload tool registry. Yoast meta (seo_title, meta_description, focus_keyword) written to all 5 pages via wp_yoast_update_post_seo. Strategy B (Mixed) locked. Keyword mapping finalized. Eklosion discrete-capture posture confirmed.
- 2026-05-17 — Session 3. Full body copy written to all 5 pages via MCP. Testimonials section added (3 quotes per page, all sources permission-verified). Trust list updated to 12 orgs (text placeholder). MUDGIRL attitré credential added to homepage. Borea accent dropped across all pages. 4539 intro fixed ("partenaire de confiance" frame). All 12 org names researched and verified. Roxanne testimonial filed to vault (13 - Testimonials & Results). Emma Blomdahl (BDC) testimonial noted, not yet filed. Moisson Laurentides added to trust list after being missed in initial pass. Jennifer Nadro attribution corrected on 4537 to full title at time of Grand Bedon ("Coordonnatrice, communications et marketing philanthropique, Moisson Laurentides") — she has since moved to Cora; attribution stays at the role she held during the engagement.
- 2026-05-17 — Session 4. Logo grid built on all 5 FR pages via Gutenberg Columns blocks. Initial 12 logos uploaded to WP Media Library (IDs 4579–4600). CSS height normalization published to WP Customizer → Additional CSS. Logo lineup revised: Spartan Race and Borea dropped from logo wall (ICP fit). Idea Hunter (4598) and Cancers du sang (4600) added. SP Canada swapped to FR version (4599). Rows reordered by shape (row 1 square/tall, row 2 medium with icons, row 3 horizontal wordmarks). Decision: source logo resizing required before publish — CSS alone cannot solve aspect ratio inconsistency. 300×150 white canvas target. Session ended with logo resize deferred to next session.
- 2026-05-18 — Session 5 (emergency). Site went 500 at session start — both front-end and WP admin down. Root cause: corrupted iThemes Security block in `/public_html/wordpress/.htaccess`, truncated mid-line at `RewriteCond %{HTTP_USE`, missing closing marker. Apache rejected all requests to `/wordpress/`. Fix: deleted lines 10–161 of that file. Site recovered ~02:16 AM. During recovery: PHP upgraded 7.4 → 8.1 (ea-php81, permanent), 7 plugins renamed to `-disabled` for diagnostics, WP_DEBUG enabled, Cloudflare paused. No FR page content was changed. Diagnostic lesson: cPanel → Errors is first call for any 500 — server Apache error log catches failures upstream of WordPress that WP debug.log never sees.
- 2026-05-18 — Session 5 morning cleanup. All 7 plugins re-enabled one at a time via cPanel File Manager, all confirmed stable on PHP 8.1 (Polylang first). WP_DEBUG confirmed already off. Cloudflare confirmed active. cPanel error log clean. Recovery complete. BUILD LOG updated. Resuming logo resize work.
