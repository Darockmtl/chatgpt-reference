---
created: 2026-05-11
updated: 2026-05-11
tags:
  - note/reference
  - status/developing
  - topic/marketing
  - brand/speakeracademy
---

# MAP — Brand System Speaker Academy

One entry point for all Speaker Academy brand assets. Visual identity, voice, and positioning live here. Files auto-populate via Dataview. Add `#brand/speakeracademy` to any new file to include it.

---

## Visual Identity

Master document — all other files defer to this:
- [[BRAND SYSTEM - Speaker Academy Visual Identity - 2026-03-21]]

Supporting (deprecated, values accurate):
- [[SPEAKER ACADEMY - Brand Colors]]
- [[SPEAKER ACADEMY - Blotato Brand Kit Input]]

---

## Voice & Copy Rules

- [[SOCIAL MEDIA POST FORMATTING RULES]]
- [[PRINCIPLE - Speaker Academy Copy Leads with the Near-Term Result - 2026-04-16]]

---

## Positioning (Active)

- [[REFERENCE - Speaker Academy Brand Positioning Foundation - 2026-03-07]] — v1.7, locked April 2026. Upstream reference for all downstream work.
- [[SPEAKER ACADEMY POSITIONING 2026]]
- [[REFERENCE - Speaker Academy Positioning WIP Status - 2026-03-24]]
- [[REFERENCE - speaker_academy_positioning_continuity_handoff_and_anti_drift_guide]] — covers both SA and Prends la parole
- [[REFERENCE - speaker_academy_positioning_process_analysis_wins_and_failures]]
- [[speaker_academy_positioning_work_in_progress_status]] — covers both SA and Prends la parole

---

## Origin Story

- [[ORIGIN STORY - Speaker Academy - 2026-03-27]]

---

## Archives

Positioning foundation version history — use active file above, not these:

```dataview
TABLE file.folder AS Location
FROM #brand/speakeracademy
WHERE contains(file.path, "_Archive") OR contains(file.path, "ARCHIVE")
SORT file.name ASC
```

---

## All Brand Files — Auto-List

```dataview
TABLE file.folder AS Location, status
FROM #brand/speakeracademy
WHERE !contains(file.path, "_Archive") AND !contains(file.name, "ARCHIVE") AND file.name != "MAP - Brand System Speaker Academy"
SORT file.name ASC
```
