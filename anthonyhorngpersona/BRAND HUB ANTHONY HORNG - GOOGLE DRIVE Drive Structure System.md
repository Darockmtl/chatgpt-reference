---
created: 2026-04-19
updated: 2026-04-19
status: permanent
tags:
  - note/reference
  - status/permanent
  - topic/organization
  - topic/brand
  - brand/anthonyhorng
---

# BRAND HUB — Drive Structure System

> **This is the master governance document for the Anthony Horng Brand Hub on Google Drive.** All file placement decisions, naming conventions, and organization rules defer to this document. If there is a conflict, this file wins.

---

## Purpose

The Brand Hub consolidates all brand assets, marketing materials, and content across the Anthony Horng business ecosystem in one centralized Drive structure. It serves as the single source for logos, photos, brand guidelines, deliverables, and publishing-ready content.

---

## Drive Folder Structure

### Root Folder
**"Anthony Horng — Brand Hub"** (ID: `11851y8Z8roU_hcxDU10IhoCyu_Q9MXtN`)

### Complete Folder Tree

```
00 SHARED
├── Headshots & Photos
├── Bios
└── Brand System
    └── Fonts

01 ANIMATEUR.CA
├── Logo
├── Speaker Sheets & Proposals
├── Event Photos
└── Testimonials

02 HOLDTHEROOM
(empty shell — future use)

03 SPEAKER ACADEMY
├── Logo & Wordmark
├── Marketing Assets
├── Canva Exports
└── Deliverables

04 ACADÉMIE PRENDS LA PAROLE
(empty shell — future use)

05 SOCIAL MEDIA (ID: 1SCFR3x3BLwwUysquxCY83I1SGjka028d)
├── 01 To Publish
├── 02 Published
└── 03 Swipe File

99 INBOX
```

---

## File Naming Convention

**Format:** `[prefix]-[what it is]-[language]-[date].ext`

### Prefixes by Brand

| Prefix | Brand/Entity | Use Case |
|---|---|---|
| `AH` | Anthony Horng (umbrella brand) | Personal brand assets, cross-brand materials, shared resources |
| `AN` | Animateur.ca | MC services, event materials, bilingual hosting content |
| `HTR` | Holdtheroom | English MC brand (future use) |
| `SA` | Speaker Academy | English course materials, coaching assets |
| `PLP` | Prends la parole | French course materials, Quebec market content |

### Language Codes
- `EN` = English
- `FR` = French (Quebec)
- `BI` = Bilingual (both languages in same file)
- Omit if not applicable (logos, photos, non-text assets)

### Date Format
- Use `YYYY-MM-DD` for dated materials
- Omit if not applicable (evergreen assets, logos)

### Examples
- `AH-Headshot-Professional-2026-04-15.jpg`
- `SA-Logo-Wordmark.png`
- `AN-Speaker-Sheet-BI-2026-04-19.pdf`
- `PLP-Course-Outline-FR-2026-05-01.docx`

---

## Three-Tier Storage Model

### Tier 1: Vault (Obsidian)
**Location:** `/Users/MC/MACMINIVAULT/MACMINI1` or `/Users/anthonyhorng/Vaults/AH/`

**What lives here:**
- Text drafts and works-in-progress
- Research and thinking documents
- Session notes and meeting captures
- Content that needs linking and cross-referencing

**Not here:**
- Final deliverables
- Brand assets
- Large media files
- Client-facing materials

### Tier 2: Google Drive Brand Hub
**Location:** Anthony Horng — Brand Hub

**What lives here:**
- Finished brand assets (logos, wordmarks, color guides)
- Finalized marketing materials
- Client deliverables and proposals
- Social media content ready to publish
- Photos and headshots
- Moderate-sized files that need sharing

**Not here:**
- Raw video footage
- Large source files
- Vault-style text documents

### Tier 3: External Drive
**Location:** Physical external drive

**What lives here:**
- Raw video footage
- Large source files and project archives
- High-resolution photo originals
- Files too large for cloud storage

---

## Routing Rules

### Decision Flow
1. **Small files, unsorted → 99 INBOX**
2. **Raw video → External drive**
3. **Finished reels → 05 Social Media / 01 To Publish**
4. **Other people's PDFs I'll read → Vault `99 ATTACHEMENTS`**
5. **Text drafts → Vault**
6. **Everything else → Figure out the correct brand storefront**

### Specific File Types

| File Type | Destination | Notes |
|---|---|---|
| Logos, wordmarks | `0X BRAND/Logo` folder | X = brand number |
| Headshots, professional photos | `00 SHARED/Headshots & Photos` | Cross-brand use |
| Brand guidelines, color specs | `00 SHARED/Brand System` | Reference materials |
| Social posts (finished) | `05 SOCIAL MEDIA/01 To Publish` | Ready for scheduling |
| Social posts (published) | `05 SOCIAL MEDIA/02 Published` | Archive with performance data |
| Event photos | `01 ANIMATEUR.CA/Event Photos` | MC work documentation |
| Course materials (final) | `03 SPEAKER ACADEMY/Deliverables` | Student-facing content |
| Research PDFs | Vault `99 ATTACHEMENTS` | Reading material, not assets |
| Video content (raw) | External drive | Too large for cloud |
| Uncertain placement | `99 INBOX` | Sort later when purpose is clear |

### Cross-Brand Materials
Files that serve multiple brands go in `00 SHARED`. Examples:
- Professional headshots usable across all brands
- Font files for brand system
- Bio text in multiple formats
- Anthony Horng personal brand guidelines

---

## Usage Notes

### Collaboration
- Share specific folders with collaborators, not the entire Brand Hub
- Use Google Drive sharing permissions to control access levels
- Comment directly in Google Docs for feedback rather than email

### Maintenance
- Monthly cleanup of `99 INBOX` — route files to proper locations
- Archive old versions when new ones are finalized
- Keep `01 To Publish` current — move published content to `02 Published`

### Integration with Content Creation
- Canva exports go to appropriate brand folder under `Canva Exports`
- Source files (Canva links) documented in vault, exports stored in Drive
- Social media workflow: Draft in vault → Design in Canva → Export to Drive → Schedule/publish

---

## Access and Permissions

### Internal Access
- Anthony Horng: Owner permissions on all folders
- Default: Private unless sharing is required

### External Sharing
- Client-specific materials: Share individual files or subfolders only
- Public materials: Use shareable links for logos, headshots when needed
- Maintain control: Avoid "Anyone with link can edit" permissions

---

## Future Considerations

### Brand Expansion
- `02 HOLDTHEROOM` and `04 ACADÉMIE PRENDS LA PAROLE` are shell folders ready for activation
- Additional prefix codes can be added as new brands launch
- Folder structure is scalable without reorganizing existing content

### Integration Opportunities
- Connect with social media scheduling tools (Blotato workflow)
- Automate export-to-Drive workflows from Canva
- Sync key brand assets to local machines for offline access

---

## Related Systems

This Drive structure integrates with:
- **Obsidian Vault:** Text content creation and research
- **Blotato:** Social media scheduling and publishing
- **Canva:** Visual content creation and brand kit management
- **Client Communication:** Shared folders for project collaboration

---

## Decision Log

| Date | Decision | Reason |
|---|---|---|
| 2026-04-19 | Brand Hub structure finalized | Consolidates scattered brand assets into single source of truth. Three-tier model separates working files (vault) from brand assets (Drive) from large media (external). |
| 2026-04-19 | File naming convention established | Prefix system enables quick identification of brand ownership while maintaining consistent format across all materials. |