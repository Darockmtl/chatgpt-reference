# REFERENCE — Logo Wall SOP — animateur.ca FR Pages — 2026-05-18

## PURPOSE

This file is the single source of truth for the logo wall on all 5 FR service pages (not the form page).
If a logo needs to be replaced, a new client added, or the grid rebuilt from scratch — start here.
Do not reconstruct decisions from chat history. Everything is captured below.

---

## THE 12-LOGO LINEUP

Finalized in Sessions 3-4. Locked unless Anthony explicitly changes it.
Grouped into 3 rows by visual shape/aspect ratio. Row assignment matters for the canvas sizing below.

### Row 1 — Square / Tall anchors (4 logos)
- Radio-Canada (gem mark — square, icon-only)
- MUDGIRL (square badge)
- The Idea Hunter (square mark)
- Competences Canada (logo mark — slightly tall)

### Row 2 — Medium rectangle with icon (4 logos)
- Patrimoine canadien (medium rectangle with icon + text)
- RCCAQ (medium rectangle with icon + text)
- Moisson Laurentides (medium rectangle with icon + text)
- Cancers du sang (medium rectangle with icon + text, SVG)

### Row 3 — Horizontal wordmark (4 logos)
- TELUS Sante (wide horizontal wordmark, SVG)
- Sushi Shop (wide horizontal wordmark, SVG)
- Tandem Communication (wide horizontal wordmark, PNG)
- SP Canada FR (wide horizontal wordmark — French version only, SVG)

### Dropped from grid — do NOT use on logo wall

These are still in the WP Media Library. Do not put them on the logo wall.

- Spartan Race: signals sports/entertainment MC, not strategic partner. MUDGIRL covers large-scale sporting proof.
- Borea Construction: not recognizable to senior comms/events ICP. Borea testimonials remain on pages 4536 and 4538 — just not on the logo wall.
- SP Canada EN (English logo): English version — wrong for FR pages. FR version is correct.
- TELUS Sante PNG duplicate: SVG version is canonical. PNG duplicate not needed.

---

## LOGO PREPARATION — CANVAS SPEC

This decision was made to normalize visual weight across logos with different native aspect ratios.
Do not skip this step. CSS alone cannot fix the weight imbalance between a square icon and a horizontal wordmark.

### Canvas dimensions (2x retina — use these)

Row 1 — square/tall: 300 x 300 px
Logos: Radio-Canada, MUDGIRL, Idea Hunter, Competences Canada

Row 2 — medium rectangle: 400 x 300 px
Logos: Patrimoine, RCCAQ, Moisson, Cancers du sang

Row 3 — horizontal wordmark: 600 x 300 px
Logos: TELUS Sante, Sushi Shop, Tandem, SP Canada FR

Why 2x: CSS caps display height at 60px. At 1x (150px height), logos render unsharp on retina/HiDPI screens. At 2x (300px height), they render crisp.

### Background

Transparent PNG. Not white.

Why: transparent avoids a visible white-box ring if the source logo has any off-white areas. The page background is white, so transparent renders identically — but it is future-proof.

### Logo placement on canvas

- Logo centered horizontally and vertically
- Padding: ~30-40px on all sides
- Do NOT stretch or distort the logo to fill the canvas
- Let the canvas create the breathing room — logo keeps its native aspect ratio

### Color treatment — source files

Keep logos in their original colors. Do NOT convert to greyscale at the file level.

Why: CSS applies greyscale at render time (see CSS section below). If you bake greyscale into the PNG, it locks the treatment permanently. Keeping source color files means the CSS decision can be changed later without re-processing 12 images.

### File naming convention

logo-[org-slug]-[canvas-width].png

Examples:
logo-radiocanada-300.png
logo-mudgirl-300.png
logo-ideahunter-300.png
logo-competencescanada-300.png
logo-patrimoinecanadien-400.png
logo-rccaq-400.png
logo-moissonlaurentides-400.png
logo-cancersdusang-400.png
logo-telussante-600.png
logo-sushishop-600.png
logo-tandem-600.png
logo-spcanada-600.png

Consistent naming lets Claude match files to orgs after upload via wp_list_media without guessing.

---

## CURRENT MEDIA IDs (as of Session 4 — pre-resized versions)

These are the IDs currently live on the FR pages. They will be replaced once the resized versions are uploaded. Update this table after re-upload.

Radio-Canada: 4584 (gem-red-rouge.png)
MUDGIRL: 4581 (mudgirl.jpg)
The Idea Hunter: 4598 (the-idea-hunter-logo-1.png)
Competences Canada: 4587 (SCC_logo_black-210x101-1.png)
Patrimoine canadien: 4591 (patrimoine-canada-logo-png_seeklogo-463872.png)
RCCAQ: 4583 (RCCAQ.png)
Moisson Laurentides: 4579 (Moisson_Laurentides_idKKmW06fq_1.png)
Cancers du sang: 4600 (llsc-logo-fr.svg)
TELUS Sante: 4589 (TELUS_Sante_id1geKKXck_1.svg)
Sushi Shop: 4588 (Sushi_Shop_idXxZWffNp_1.svg)
Tandem Communication: 4585 (TANDEM_logos.png)
SP Canada FR: 4599 (sp-canada-logo-black-fr.svg)

---

## CSS — CURRENT STATE (published in WP Customizer Additional CSS)

### Normalization CSS (published Session 3/4, currently live)

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

### Greyscale CSS — DECIDED IN SESSION 4, NOT YET ADDED

The decision to greyscale the logo wall was made in Sessions 3/4. Greyscale is applied via CSS at render time — NOT baked into the source files.

This line still needs to be added to WP Customizer Additional CSS:

.wp-block-columns .wp-block-image img {
  filter: grayscale(100%);
}

This can be added as a separate rule or merged into the existing .wp-block-columns .wp-block-image img block above.

Why CSS greyscale, not file-level greyscale: one line of CSS changes the treatment for all 12 logos instantly. To reverse it, delete one line. Re-processing 12 image files would be a full job.

### Why this CSS is safe for the main EN site

The English site uses Elementor with elementor-* / eael-* class structure. Gutenberg's .wp-block-columns .wp-block-image selector does not match Elementor markup. The CSS only affects Gutenberg Columns blocks, which only the FR pages use for the logo grid.

---

## HOW TO REPLACE A SINGLE LOGO

If one logo needs updating (org rebranded, better file found, etc.):

1. Prepare the new logo file on the correct canvas for its row (300x300, 400x300, or 600x300)
2. Upload to WP Media Library (Anthony uploads via WP admin drag-and-drop)
3. Note the new media ID (Claude reads via wp_list_media, or check Media Library — click the file, ID is in the URL)
4. Run wp_update_page for each of the 5 FR service pages (4535, 4536, 4537, 4538, 4539) replacing only the old ID with the new ID in the figure block for that logo
5. Update the media ID table in this file with the new ID

Do NOT rebuild the full grid unless the row structure or lineup changes. Surgical replacement only.

---

## HOW TO REBUILD THE FULL GRID FROM SCRATCH

If the grid needs to be rebuilt on all pages (after a full site restore, or after a WordPress update breaks the block structure):

1. Read the current FR page content via wp_get_page for each page to confirm current state
2. The grid lives inside a Gutenberg Columns block structure — 3 separate wp:columns blocks (one per row), each with 4 wp:column child blocks each containing a wp:image block
3. Use the media IDs from the table above (updating to latest after any logo replacements)
4. Run wp_update_page for each page with the rebuilt content
5. Verify normalization CSS is still published in Customizer
6. Verify greyscale filter is still in Customizer

---

## THE 5 FR SERVICE PAGES (logo wall lives on all of these)

4535 — Anthony Horng | Animateur bilingue | Maitre de ceremonie au Quebec (slug: accueil-fr)
4536 — Animateur corporatif bilingue au Quebec | Anthony Horng
4537 — Animateur de gala et soirees de remise de prix au Quebec
4538 — Animateur bilingue francais-anglais au Canada | Anthony Horng
4539 — Animateur de congres et sommets professionnels au Quebec

Page 4567 (Parlons de votre evenement / form page) does NOT have a logo wall.

---

## DECISIONS LOG — LOGO WALL

1. 12 logos, not more — enough proof without becoming a gallery
2. Shape-grouped rows — visual normalization strategy (Row 1 square, Row 2 medium, Row 3 horizontal)
3. 2x retina canvas — 300x300 / 400x300 / 600x300 (decided Session 5 to fix sharpness on HiDPI)
4. Transparent PNG — future-proof, avoids white-box artifacts
5. Source files stay in color — CSS handles greyscale at render time
6. Greyscale at render via CSS filter: grayscale(100%) — premium look, unifies color chaos, one-line CSS toggle
7. Spartan Race and Borea dropped — ICP fit, not display quality
8. SP Canada: FR version only — bilingual market reality, logo verifies French capability
9. MUDGIRL stays — 60K+ women season total across multiple events; largest single event approximately 3,000. Do not inflate this number in any copy near the logo.
10. Gutenberg Columns not Gallery block — more control, compatible with the CSS selector strategy
