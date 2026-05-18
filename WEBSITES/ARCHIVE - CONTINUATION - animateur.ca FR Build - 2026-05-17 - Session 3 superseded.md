# CONTINUATION — animateur.ca FR Build — 2026-05-17
*Session compaction handoff. New Claude instance reads this FIRST before doing anything else.*

## HARD RULES — READ BEFORE ANY ACTION

1. NO em dashes anywhere. Commas or pipes.
2. NO "amont". Eklosion vocabulary.
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

Take corrections without re-arguing. Push back only when the logic is real.

---

## What's done

**Environment:** WordPress 6.9.4, Elementor 4.0.8, PHP 7.4.33 (EOL, deferred). Host: HostGator. UpdraftPlus backup at `/Volumes/main/BACKUP WEBSITE`.

**Plugins:**
- ✅ Easy MCP AI (OAuth-connected, Force Draft ENABLED, Yoast tools 3/3 enabled)
- ✅ Polylang 3.8.3 (directory-based, FR at /fr/)
- ✅ UpdraftPlus
- ✅ Yoast SEO
- ⚪ Connect Polylang for Elementor (inactive, stays inactive)
- ⚪ TranslatePress (inactive, never activate alongside Polylang)

**MCP:** `https://animateur.ca/wp-json/easy-mcp-ai/v1/mcp`. Force Draft ENABLED. Yoast tools accessible via wp_yoast_update_post_seo. Note: if Yoast tools don't load via tool_search, disconnect and reconnect the animateur.ca connector in Claude.ai Settings → Connectors.

**5 French draft pages — Yoast meta written and confirmed:**

| Page ID | Slug | Focus Keyword | SEO Title |
|---|---|---|---|
| 4535 | accueil-fr | animateur bilingue Québec | Animateur bilingue au Québec | Anthony Horng, MC |
| 4536 | animateur-corporatif | animateur corporatif Montréal | Animateur corporatif Montréal | Anthony Horng, bilingue |
| 4537 | animateur-gala | gala de reconnaissance | Animateur de gala de reconnaissance, Québec | Anthony Horng |
| 4538 | animateur-bilingue | animateur bilingue Montréal | Animateur bilingue à Montréal | Anthony Horng |
| 4539 | animateur-congres | maître de cérémonie congrès | Maître de cérémonie de congrès au Québec | Anthony Horng |

---

## What's locked (vocabulary, copy)

**Approved vocabulary:** crédibilité, co-création, intention, texte d'animation, enjeux, ressentir, "avant le jour J", "le partenaire de confiance", "les deux langues doivent compter".

**Locked homepage hero:**
> H1: L'animateur bilingue qui entre dans votre événement avant le jour J
> Subtitle: Le partenaire de confiance pour vos événements à enjeux.

**Locked process section (applied to all 5 pages):**
> H2: La co-création se fait en trois temps.
>
> Découvrir. Vous savez ce que votre événement doit accomplir, au-delà du programme. Pas ce qui doit être dit. Ce qui doit être compris. Anthony pose les questions sur votre intention réelle, le message qui doit traverser, ce que votre salle doit emporter avec elle.
>
> Concevoir. Vous savez ce qui va se passer sur scène avant le jour J. Le texte d'animation est construit avec vous. Chaque transition, chaque introduction, chaque moment de passage sert votre intention.
>
> Livrer. Vous savez que votre événement est entre bonnes mains, peu importe ce qui arrive. Les imprévus se gèrent sans que vos invités le ressentent. Votre équipe peut se concentrer sur le reste.

**Locked bilingual framing:**
> Quand les deux langues doivent compter dans la même salle, l'animateur bilingue n'est pas un atout. C'est une nécessité.

**Proof bank:** TELUS Santé, MTY / Sushi Shop, Skills Canada, MUDGIRL, TEDx, Boréa, Orchid Ball, Canada Day

**Eklosion posture:** discrete capture. Still working with Eklosion. Same Quebec market. No visible signals of competition. Strategy B (Mixed): compete where within reach, capture where Eklosion absent.

---

## Pending tasks (in order)

**Next primary deliverable: body content per page.**

The process section is locked and goes on all 5 pages. Each service page also needs:
- A page-specific intro section (above the process section) scoped to that service type
- Proof elements relevant to that service (from proof bank)
- A CTA / inquiry section

Homepage (accueil-fr) also needs: a proof/testimonial section and an inquiry placeholder.

Before writing any body copy: read the ICP file and Proof Bank. Links in REFERENCE file.

**Anthony's manual steps still pending:**
- Polylang: link each French page to its English equivalent. Do at publish time, not before.
- Reel embed: when reel drops, embed on accueil-fr draft.

**Deferred:**
- Blog strategy (topical authority + AI Overview citation play) — flagged, not scoped
- PHP 7.4 upgrade — contact HostGator
- Plugin cleanup (delete Connect Polylang for Elementor + TranslatePress once stable)
- Visual design layer (post-MUDGIRL)
- Zoho Forms embed on homepage inquiry placeholder

---

## Files in scope

- `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/11 - Marketing & Brand/WEBSITES/00 - START HERE.md`
- `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/11 - Marketing & Brand/WEBSITES/BUILD LOG - animateur.ca FR via MCP - 2026-05-17.md`
- `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/11 - Marketing & Brand/WEBSITES/SERP Analysis - Quebec Animateur Queries - 2026-05-12.md`
- `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/11 - Marketing & Brand/WEBSITES/SERP Analysis - Quebec Maître de Cérémonie Queries - 2026-05-12.md`
- `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/ZZ-Claude-Projects/ICP Coaching MC Work/PROOF BANK - MC Work - Anthony Horng - 2026-03-29.md`

---

## First moves for new instance

1. Load filesystem MCP: tool_search for "read file filesystem", "list directory search files vault", "filesystem write_file".
2. Read this file in full.
3. Read BUILD LOG in full.
4. Read ICP file and Proof Bank before writing any body copy.
5. Confirm understanding by quoting hard rules back before proceeding.
6. Ask Anthony: which page do you want to tackle first?
