# EMERGENCY CAPTURE — animateur.ca 500 Recovery — 2026-05-18

## RESOLVED — SITE IS BACK UP (as of 2026-05-18 ~02:16 AM)

The site recovered. Both front-end (`animateur.ca`) and WordPress admin (`animateur.ca/wordpress/wp-admin/`) are working again.

**Root cause:** Corrupted iThemes Security block inside `/public_html/wordpress/.htaccess` — the block was truncated mid-line at `RewriteCond %{HTTP_USE` and was missing its `# END iThemes Security` closing marker. Apache hit the syntax error on every request to anything under `/wordpress/` and returned 500. The outer `/public_html/.htaccess` was fine, which is why `animateur.ca` alone partially loaded while `animateur.ca/wordpress/*` died.

**Fix applied:** Deleted lines 10 through 161 of `/public_html/wordpress/.htaccess` — the entire corrupted iThemes Security block from `# BEGIN iThemes Security` down through `RewriteCond %{HTTP_USE`. iThemes Security isn't active anyway. The block was orphaned dead weight.

**This was NOT caused by anything in this chat session.** The corruption was pre-existing in the .htaccess file, likely from a prior partial UpdraftPlus restore or a previous incomplete .htaccess write. Apache's tolerance for the malformed block apparently changed when PHP was upgraded to 8.1 (or independently when the server reloaded its config), exposing the latent bug.

**The breakthrough diagnostic** was cPanel → Errors (server-level Apache error log). That log showed the exact line and file with the syntax error. Should have gone there much earlier in the troubleshooting — would have saved hours.

## CURRENT NON-DEFAULT STATE — STILL NEEDS REVERTING

These are changes that are still in place and should be reverted at the next session start (with a fresh head, not at 2 AM):

### 1. PHP version: 7.4 → 8.1 — KEEP

This change is **good and should not be reverted.** PHP 7.4 was EOL since November 2022. Site is now on PHP 8.1 (`ea-php81`). One-way change in cPanel — cannot revert through UI anyway.

Update the BUILD LOG to reflect that PHP is now 8.1, not 7.4.

### 2. Seven plugins renamed to `-disabled` — RE-ENABLE ONE AT A TIME

These plugin folders still have `-disabled` appended and need to be renamed back to their original names. **Do this one at a time, refreshing the site between each, to confirm none of them break PHP 8.1.** If any of them did break, that's a separate fix per plugin.

Path: `/public_html/wordpress/wp-content/plugins/`

- `easy-mcp-ai-disabled` → `easy-mcp-ai`
- `nextgen-gallery-disabled` → `nextgen-gallery`
- `give-disabled` → `give`
- `ewww-image-optimizer-disabled` → `ewww-image-optimizer`
- `contact-form-7-disabled` → `contact-form-7`
- `all-in-one-seo-pack-disabled` → `all-in-one-seo-pack`
- `polylang-disabled` → `polylang`

**Polylang is the most important to verify** — without it, the `/fr/` URL routing breaks and the FR drafts can't be properly linked.

### 3. wp-config.php: WP_DEBUG enabled — TURN BACK OFF

Path: `/public_html/wordpress/wp-config.php`, lines 84-86.

Currently:
```
define('WP_DEBUG', true);
define('WP_DEBUG_LOG', true);
define('WP_DEBUG_DISPLAY', false);
```

Should be (once recovery is complete and we don't need diagnostics anymore):
```
define('WP_DEBUG', false);
```

Local backup of original wp-config.php is in Anthony's Downloads folder if needed.

### 4. Cloudflare paused — RE-ENABLE

Cloudflare → animateur.ca → Overview → "Enable Cloudflare on Site"

The pause was 3-hour window starting ~01:40 AM. It may auto-reactivate at ~04:40 AM. Verify it's active before next work session.

### 5. .htaccess inside /wordpress/ — backup exists locally

The corrupted .htaccess that had iThemes Security crap removed was downloaded as backup before edit. The CURRENT version on the server is the clean fixed version. Don't restore from the local backup unless something goes badly wrong — the local backup has the bug.

### 6. plugins-off folder renamed back to plugins — DONE

This was the rename that fixed the first half of the issue (mid-session). The folder at `/wp-content/plugins/` is the correct active folder now. The pre-existing `plugins-old/`, `updraft/plugins-old/`, and the `-old` cleanup mess is still there but is not blocking anything.

## STILL NEEDS DOING (post-recovery)

### Immediate next session priorities

1. **Verify the 6 FR draft pages still exist and are intact** in WordPress admin:
   - 4535 (homepage / accueil-fr)
   - 4536 (corporatif)
   - 4537 (gala)
   - 4538 (bilingue)
   - 4539 (congrès)
   - 4567 (demande / form)
2. Re-enable the 7 plugins one at a time (above)
3. Turn off WP_DEBUG
4. Re-enable Cloudflare
5. Update BUILD LOG with the full recovery story and current state

### Then resume the original Session 5 work

Original purpose of Session 5: continue the FR build by replacing 12 logos on all 5 FR pages with newly resized versions. Per the Session 5 continuation file, Anthony was preparing the 12 resized logos in Canva (300×300 / 400×300 / 600×300 canvases with logos centered). That work was NEVER done — the 500 hit before he started.

Order of resume:
1. Anthony resizes 12 logos in Canva (color logos on white canvas)
2. Anthony uploads to WP Media Library
3. New chat reads media IDs via `wp_list_media`
4. New chat updates all 5 FR pages via `wp_update_page` with new media IDs
5. Add greyscale CSS filter to the existing Customizer CSS (the one-line `filter: grayscale(100%);` addition)
6. Anthony previews homepage
7. Polylang FR↔EN linking
8. Final publish

### Carried open items (lower priority)

- File Emma Blomdahl testimonial to vault
- Plugin cleanup (Connect Polylang for Elementor, TranslatePress) — both currently inactive, can delete post-launch
- Clean up the `wp-content/-old` folder mess and `updraft/plugins-old/` etc. — pre-existing junk, archive to local then delete from server
- Cloudflare paused timer monitoring

## LESSONS FROM TONIGHT

1. **cPanel → Errors tool is the first diagnostic for any 500.** Server-level Apache errors are NOT in WordPress's debug.log. If debug.log is empty despite WP_DEBUG being on, the failure is upstream of WordPress and only the server error log will catch it.
2. **A 500 with no PHP error usually means .htaccess or Apache config.** This pattern needs to be recognized fast next time.
3. **Multiple `.htaccess` files exist** — `/public_html/.htaccess` AND `/public_html/wordpress/.htaccess` were different files with different content. Always check which one the error is about.
4. **Claude's hypothesis chain (PHP handler, Cloudflare, plugins, etc.) was slow.** Should have gone to the error log FIRST. Hours were burned narrowing the wrong problems.
5. **Anthony's push to look at the error log directly** was correct earlier than I responded to it. When Anthony asks "are you just grasping at straws," that's the cue to stop hypothesizing and go look at actual data.

## VAULT PATH (Mac Mini)

`/Users/MC/MACMINIVAULT/MACMINI1/`

## TIMELINE OF SESSION 5 — BEFORE THE 500

Session 5 started normally to continue the animateur.ca FR build. The plan per the Session 5 continuation file was:
- Anthony to resize 12 logos to consistent canvas, re-upload to WP Media Library
- Claude to update all 5 FR pages with new image IDs
- Continue toward publish

In this session:
1. Tools loaded successfully
2. Discussed logo canvas dimensions (300×300 / 400×300 / 600×300)
3. Generated 3 blank PNG canvas templates for Anthony to use as a base
4. Anthony then said "Sorry, that didn't work. Please try again or come back later. 500 Error" — site went down out of nowhere
5. The rest of the session was recovery troubleshooting

Notable: At no point did Claude make any write calls to the live site before the 500 appeared. The 500 was not triggered by anything done in this chat session.

## ORIGINAL SYMPTOMS (when the 500 first appeared)

- `https://animateur.ca/wordpress/wp-admin/` → 500
- `https://animateur.ca` → loaded but completely unformatted
- HostGator dashboard initially showed 4 sites, then dropped to 3 (animateur.ca/wordpress disappeared from Websites list)
- error_log at WP root had only two old entries from yesterday — both Really Simple SSL cron noise, unrelated

## CHANGES MADE THIS SESSION DURING RECOVERY ATTEMPTS

See "Current Non-Default State" section above for the running list.

Full timeline:
1. Renamed 7 plugins to `-disabled` (still need reverting — see above)
2. Edited wp-config.php to enable WP_DEBUG (still need reverting)
3. Changed PHP 7.4 → 8.1 (keep this)
4. Paused Cloudflare (re-enable)
5. Renamed `plugins-off` back to `plugins` (this was good — that folder was renamed by an unknown process at 01:02 AM)
6. **THE FIX:** Removed corrupted iThemes Security block from `/public_html/wordpress/.htaccess` (lines 10-161)

## DISCOVERED STATE — STILL TRUE, FOR NEXT SESSION TO BE AWARE

The wp-content folder has historical mess that is pre-existing and unrelated to tonight:
- `plugins-old/` (at top level of wp-content)
- `themes-old/`
- `uploads-old/`
- `languages-old/`
- `gallery-old/`
- `ewww-old/`
- A full `updraft/` tree with `plugins-old/`, `themes-old/`, `uploads-old/` inside

These are leftover from previous restore attempts and should be cleaned up at a stable point. Not blocking. Not urgent. Archive to local first, then delete from server.

The `plugins-off` folder no longer exists (renamed back to `plugins`).

## FILES TO READ IN ORDER FOR NEW CHAT

1. This file (you're reading it)
2. `CONTINUATION - animateur.ca FR Build - Session 5 - 2026-05-17.md` (original Session 5 starting point — pre-emergency)
3. `BUILD LOG - animateur.ca FR via MCP - 2026-05-17.md` (full project history)
4. `REFERENCE - Anthony Horng Project Context.md` at `/Users/MC/MACMINIVAULT/MACMINI1/01.ANTHONY HORNG PERSONAE/`
5. `CLAUDE.md` at same path

## DO NOT FORGET — SEQUENCE FOR NEXT SESSION

Once site stability is confirmed:

1. **Re-enable plugins one at a time** (rename `-disabled` back). Watch each for 30 seconds. Polylang FIRST — it's critical for the FR URL routing.
2. **Turn off WP_DEBUG** in wp-config.php (revert lines 84-86 back to a single `define('WP_DEBUG', false);`).
3. **Re-enable Cloudflare** in the Cloudflare dashboard.
4. **Verify FR draft pages still exist** in WP admin (Pages → Drafts → look for IDs 4535-4539, 4567).
5. **Update BUILD LOG** with full recovery story + PHP 8.1 status.
6. **Resume logo work** per the original Session 5 plan.
