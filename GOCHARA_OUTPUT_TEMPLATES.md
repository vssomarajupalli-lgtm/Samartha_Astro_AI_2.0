TITLE
SAMARTHA ASTRO-AI SYSTEM 2.0
GOCHARA OUTPUT TEMPLATES
PRINT AND PWA RENDER SPECIFICATION

1. PURPOSE

This file defines the standard output templates for rendering Samartha Gochara results in PDF and PWA formats.

It governs:
- Elinati Shani Summary layout
- Current Saturn Status layout
- Present Full Gochara layout
- Dasha Overlap layout
- JSON object to UI mapping

2. GLOBAL RULES

All rendered output must follow the core system rules:
- DD.MM.YYYY date format
- Pure Telugu display output
- Runtime timestamp visibility where required
- Print-safe structured sections
- JSON-ready data compatibility

3. PDF OUTPUT STRUCTURE

Recommended fixed PDF page order:

Page 1:
Birth Details Page

Page 2:
Elinati Shani Life-Cycle Summary

Page 3:
Current Saturn Micro Gochara Status

Page 4:
Present Full Planetary Gochara

Page 5:
Dasha Overlap for Saturn Cycle Dates

4. ELINATI SHANI SUMMARY TEMPLATE

Required fields:
- Cycle Number
- Full Start Date
- 12th Zone Start Date
- 1st Zone Start Date
- 2nd Zone Start Date
- Full Exit Date
- Total Duration
- Current Status Tag

Suggested table columns:
- Cycle
- Start
- 12th Zone
- 1st Zone
- 2nd Zone
- Exit
- Duration
- Status

5. CURRENT SATURN STATUS TEMPLATE

Required fields:
- Natal Moon Rashi
- Natal Moon Nakshatra
- Natal Moon Pada
- Current Saturn Rashi
- Current Saturn Nakshatra
- Current Saturn Pada
- Relative Belt Position
- Belt Status
- Active Zone
- Saturn Strength
- Moon Strength
- Related Bhava Strength
- Final Zone Percentage
- Grade Label

Suggested section order:
- Natal Moon Anchor
- Current Saturn Transit
- Moon-Centric Belt Mapping
- Strength Components
- Final Result

6. PRESENT FULL GOCHARA TEMPLATE

Required planet list:
- Sun
- Moon
- Mars
- Mercury
- Jupiter
- Venus
- Saturn
- Rahu
- Ketu

Suggested table columns:
- Planet
- Longitude
- Rashi
- Nakshatra
- Pada
- Runtime Time

7. DASHA OVERLAP TEMPLATE

Required fields:
- Event Type
- Event Date
- Mahadasha
- Antardasha
- Pratyantardasha

Mandatory event rows:
- Full Cycle Start
- 12th Zone Entry
- 1st Zone Entry
- 2nd Zone Entry
- Full Cycle Exit

8. PWA TAB TEMPLATE

Minimum required gochara tabs:

- Elinati Shani Summary
- Current Saturn Status
- Present Full Gochara
- Dasha Overlap

9. JSON OUTPUT TEMPLATE

Mandatory JSON root keys:

- birth_profile
- natal_moon_reference
- saturn_micro_status
- elinati_shani_cycles
- present_full_gochara
- dasha_overlap
- runtime_metadata

10. SAMPLE JSON SHAPE

{
  "birth_profile": {},
  "natal_moon_reference": {},
  "saturn_micro_status": {},
  "elinati_shani_cycles": [],
  "present_full_gochara": [],
  "dasha_overlap": [],
  "runtime_metadata": {}
}

11. UI LABELING RULE

Internal code may remain in English.
All displayed headings, labels, tables, and narrative output must be rendered in Telugu.

12. PRINT SAFETY RULE

All tables must be print-safe.
Rows must avoid page-break splitting.
Headers must repeat across pages where needed.

13. GOVERNANCE

Any future gochara UI, PDF, or report output must conform to this output template file unless an updated authoritative template replaces it.