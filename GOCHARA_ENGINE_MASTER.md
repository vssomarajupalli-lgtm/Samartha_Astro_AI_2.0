<<<<<<< HEAD
TITLE
SAMARTHA ASTRO-AI SYSTEM 2.0
GOCHARA ENGINE MASTER
AUTHORITATIVE MICRO AND MACRO TRANSIT SPECIFICATION

1. PURPOSE

This document is the sole authoritative specification for all Samartha Gochara computations.
All gochara-related logic including Moon-centric micro transit indexing, Elinati Shani lifecycle detection, present planetary gochara reporting, and Dasha-linked transit print outputs shall be governed by this file.

This file supersedes all previous embedded whole-rashi gochara logic formerly placed inside broader calculation engine documents.

2. GLOBAL GOCHARA PRINCIPLE

Legacy whole-sign transit narration is deprecated for Samartha True Micro Gochara.
The system shall not assign transit outcomes merely because a planet has entered a sign.
All meaningful micro-gochara computations shall be based on exact nakshatra-pada positioning.

The native Moon’s exact natal nakshatra-pada shall be the primary anchor for Elinati Shani and Moon-centric micro transit calculations.

3. ZODIAC DIVISION MODEL

The zodiac shall be treated as:
- 12 Rashis
- 27 Nakshatras
- 108 Nakshatra Padas

Each Rashi = 9 Padas
Each Nakshatra = 4 Padas

All circular transit indexing shall operate on the 108-pada belt.

4. EPHEMERIS SOURCE POLICY

Swiss Ephemeris is not mandatory for this deployment path.

Primary free astronomical source:
Skyfield with JPL ephemeris data

Fallback free astronomical source:
Moshier ephemeris

The engine must be built through a decoupled ephemeris provider interface so that astronomical back-end sources can be changed without rewriting the Gochara calculation logic.

5. MOON-CENTRIC 27-PADA ELINATI SHANI BELT

5.1 Central Anchor

The natal Moon exact pada shall be identified from the birth chart and fixed as the center reference point.

5.2 Belt Span

A Moon-centric Elinati Shani active belt shall be defined as:
- 13 padas backward from natal Moon
- natal Moon center position
- 13 padas forward from natal Moon

Thus:
Total Active Belt = 27 Padas

5.3 Internal Position Indexing

For internal calculation:
- Position 1 to 13 = backward side
- Position 14 = natal Moon center
- Position 15 to 27 = forward side

5.4 Zone Division

The 27-pada active belt shall always be divided into 3 equal fixed 9-pada zones:

Zone 1:
Positions 1 to 9
Interpretation: 12th House Zone

Zone 2:
Positions 10 to 18
Interpretation: 1st House Zone / Lagna Zone

Zone 3:
Positions 19 to 27
Interpretation: 2nd House Zone

Thus Position 14, the natal Moon center, belongs to the middle band and therefore falls under the 1st House Zone.

5.5 Equal Eligibility Rule

No pada inside the 27-pada belt shall receive any unequal weighting.
No apex weighting, center weighting, or distance decay shall be used.
All padas inside the active belt are equally valid for zone membership.

6. SATURN TRANSIT MATCHING RULE

At runtime, the engine shall compute Saturn’s exact current nakshatra-pada.
The engine shall calculate Saturn’s relative position against the Moon-centric 27-pada belt.

If Saturn falls outside the 27-pada belt:
- Elinati Shani micro zone status = inactive

If Saturn falls inside the 27-pada belt:
- the engine shall identify the exact active zone:
  - 12th House Zone
  - 1st House Zone
  - 2nd House Zone

7. ELINATI SHANI LIFESPAN CYCLE DETECTION

The engine shall scan Saturn transit movement across the native’s practical life span and detect all complete Elinati Shani cycles based on the Moon-centric 27-pada rule.

A full cycle begins when Saturn first enters the 27-pada belt.
A full cycle ends when Saturn exits the 27-pada belt after crossing the full active zone range.

The engine shall identify:
- past completed cycles
- currently active cycle
- future upcoming cycles

A native may typically experience approximately 2 to 3 major Elinati Shani cycles across life, but the engine shall calculate actual occurrences dynamically rather than assuming a fixed count.

8. ELINATI SHANI CYCLE DATES

For each detected cycle, the engine shall compute and store:

- Cycle Number
- Full Cycle Start Date
- 12th Zone Entry Date
- 1st Zone Entry Date
- 2nd Zone Entry Date
- Full Cycle Exit Date
- Total Cycle Duration
- Status Tag: Past / Present / Future

All dates must be rendered in DD.MM.YYYY format.

9. ZONE SCORE FORMULAS

Once active zone is identified, the zone result shall be calculated using an equal three-part average.

9.1 12th House Zone
Final Score =
(Saturn Strength + Moon Strength + 12th Bhava Strength) / 3

9.2 1st House Zone
Final Score =
(Saturn Strength + Moon Strength + 1st Bhava Strength) / 3

9.3 2nd House Zone
Final Score =
(Saturn Strength + Moon Strength + 2nd Bhava Strength) / 3

All component strengths must already be normalized into 0 to 100 scale before averaging.

10. DASHA LINKAGE INTEGRATION

Every Elinati Shani cycle and every zone transition date must be cross-mapped with the Dasha engine.

For each important cycle date, the print system must identify:
- active Mahadasha
- active Antardasha
- active Pratyantardasha

This mapping is mandatory for:
- full cycle start
- 12th zone start
- 1st zone start
- 2nd zone start
- full cycle exit

11. PRESENT FULL GOCHARA ENGINE

The Gochara module shall also generate a present-time full planetary transit sheet for all principal planets.

Mandatory present-gochara planet list:
- Sun
- Moon
- Mars
- Mercury
- Jupiter
- Venus
- Saturn
- Rahu
- Ketu

For each planet, the engine shall produce:
- current longitude
- current rashi
- current nakshatra
- current pada
- runtime timestamp
- optional Moon-relative status where applicable

12. CURRENT STATUS OUTPUT

For Saturn specifically, the engine must output:
- current transit rashi
- current nakshatra
- current pada
- whether Saturn is inside or outside the Moon-centric 27-pada belt
- active zone label if inside
- corresponding zone percentage
- related bhava label
- current cycle status: not active / active / upcoming / completed

13. CIRCULAR INDEXING RULE

The zodiac shall be treated as a continuous circular 108-pada field.

If backward counting crosses below pada 1, the index shall wrap to 108.
If forward counting crosses above pada 108, the index shall wrap to 1.

This circular continuity is mandatory for all transit calculations.

14. OUTPUT OBJECTS

The engine must compute and expose clean JSON-ready output objects for both PDF and PWA.

Mandatory Elinati Shani object fields:
- Natal Moon Pada
- Saturn Transit Pada
- Relative Position in 27-Pada Belt
- Active Zone
- Related House
- Saturn Strength
- Moon Strength
- Related Bhava Strength
- Final Zone Percentage
- Grade Label
- Full Cycle Start
- 12th Zone Entry
- 1st Zone Entry
- 2nd Zone Entry
- Full Cycle Exit
- Past/Present/Future Status
- Active MD
- Active AD
- Active PD
- Runtime Timestamp

Mandatory Present Gochara object fields:
- Planet Name
- Longitude
- Rashi
- Nakshatra
- Pada
- Runtime Timestamp

15. PRINT PRODUCTION STRUCTURE

The print engine shall support a clean production-ready gochara report.

Recommended fixed page structure:

Page 1:
Elinati Shani Lifecycle Summary
- all detected cycles
- start/end dates
- past/present/future tags

Page 2:
Current Saturn Micro Status
- natal Moon anchor
- current Saturn pada
- active zone
- formula components
- final percentage

Page 3:
Present Full Planetary Gochara
- all principal planets
- rashi, nakshatra, pada

Page 4:
Dasha Overlap Sheet
- MD / AD / PD active at each Saturn cycle transition date

16. PWA STRUCTURE

For the hosted PWA, the Gochara module shall expose at least the following tabs or views:

- Elinati Shani Summary
- Current Saturn Status
- Present Full Gochara
- Dasha Overlap

17. LANGUAGE AND PRESENTATION RULE

All final user-facing output intended for print or PWA display must comply with the Pure Telugu output rules defined in the core system rules.

Internal code variable names may remain in English for maintainability.
Rendered labels, headings, and narrative output must be in Telugu.

18. GOVERNANCE

This file is the final authority for Gochara computation.
=======
TITLE
SAMARTHA ASTRO-AI SYSTEM 2.0
GOCHARA ENGINE MASTER
AUTHORITATIVE MICRO AND MACRO TRANSIT SPECIFICATION

1. PURPOSE

This document is the sole authoritative specification for all Samartha Gochara computations.
All gochara-related logic including Moon-centric micro transit indexing, Elinati Shani lifecycle detection, present planetary gochara reporting, and Dasha-linked transit print outputs shall be governed by this file.

This file supersedes all previous embedded whole-rashi gochara logic formerly placed inside broader calculation engine documents.

2. GLOBAL GOCHARA PRINCIPLE

Legacy whole-sign transit narration is deprecated for Samartha True Micro Gochara.
The system shall not assign transit outcomes merely because a planet has entered a sign.
All meaningful micro-gochara computations shall be based on exact nakshatra-pada positioning.

The native Moon’s exact natal nakshatra-pada shall be the primary anchor for Elinati Shani and Moon-centric micro transit calculations.

3. ZODIAC DIVISION MODEL

The zodiac shall be treated as:
- 12 Rashis
- 27 Nakshatras
- 108 Nakshatra Padas

Each Rashi = 9 Padas
Each Nakshatra = 4 Padas

All circular transit indexing shall operate on the 108-pada belt.

4. EPHEMERIS SOURCE POLICY

Swiss Ephemeris is not mandatory for this deployment path.

Primary free astronomical source:
Skyfield with JPL ephemeris data

Fallback free astronomical source:
Moshier ephemeris

The engine must be built through a decoupled ephemeris provider interface so that astronomical back-end sources can be changed without rewriting the Gochara calculation logic.

5. MOON-CENTRIC 27-PADA ELINATI SHANI BELT

5.1 Central Anchor

The natal Moon exact pada shall be identified from the birth chart and fixed as the center reference point.

5.2 Belt Span

A Moon-centric Elinati Shani active belt shall be defined as:
- 13 padas backward from natal Moon
- natal Moon center position
- 13 padas forward from natal Moon

Thus:
Total Active Belt = 27 Padas

5.3 Internal Position Indexing

For internal calculation:
- Position 1 to 13 = backward side
- Position 14 = natal Moon center
- Position 15 to 27 = forward side

5.4 Zone Division

The 27-pada active belt shall always be divided into 3 equal fixed 9-pada zones:

Zone 1:
Positions 1 to 9
Interpretation: 12th House Zone

Zone 2:
Positions 10 to 18
Interpretation: 1st House Zone / Lagna Zone

Zone 3:
Positions 19 to 27
Interpretation: 2nd House Zone

Thus Position 14, the natal Moon center, belongs to the middle band and therefore falls under the 1st House Zone.

5.5 Equal Eligibility Rule

No pada inside the 27-pada belt shall receive any unequal weighting.
No apex weighting, center weighting, or distance decay shall be used.
All padas inside the active belt are equally valid for zone membership.

6. SATURN TRANSIT MATCHING RULE

At runtime, the engine shall compute Saturn’s exact current nakshatra-pada.
The engine shall calculate Saturn’s relative position against the Moon-centric 27-pada belt.

If Saturn falls outside the 27-pada belt:
- Elinati Shani micro zone status = inactive

If Saturn falls inside the 27-pada belt:
- the engine shall identify the exact active zone:
  - 12th House Zone
  - 1st House Zone
  - 2nd House Zone

7. ELINATI SHANI LIFESPAN CYCLE DETECTION

The engine shall scan Saturn transit movement across the native’s practical life span and detect all complete Elinati Shani cycles based on the Moon-centric 27-pada rule.

A full cycle begins when Saturn first enters the 27-pada belt.
A full cycle ends when Saturn exits the 27-pada belt after crossing the full active zone range.

The engine shall identify:
- past completed cycles
- currently active cycle
- future upcoming cycles

A native may typically experience approximately 2 to 3 major Elinati Shani cycles across life, but the engine shall calculate actual occurrences dynamically rather than assuming a fixed count.

8. ELINATI SHANI CYCLE DATES

For each detected cycle, the engine shall compute and store:

- Cycle Number
- Full Cycle Start Date
- 12th Zone Entry Date
- 1st Zone Entry Date
- 2nd Zone Entry Date
- Full Cycle Exit Date
- Total Cycle Duration
- Status Tag: Past / Present / Future

All dates must be rendered in DD.MM.YYYY format.

9. ZONE SCORE FORMULAS

Once active zone is identified, the zone result shall be calculated using an equal three-part average.

9.1 12th House Zone
Final Score =
(Saturn Strength + Moon Strength + 12th Bhava Strength) / 3

9.2 1st House Zone
Final Score =
(Saturn Strength + Moon Strength + 1st Bhava Strength) / 3

9.3 2nd House Zone
Final Score =
(Saturn Strength + Moon Strength + 2nd Bhava Strength) / 3

All component strengths must already be normalized into 0 to 100 scale before averaging.

10. DASHA LINKAGE INTEGRATION

Every Elinati Shani cycle and every zone transition date must be cross-mapped with the Dasha engine.

For each important cycle date, the print system must identify:
- active Mahadasha
- active Antardasha
- active Pratyantardasha

This mapping is mandatory for:
- full cycle start
- 12th zone start
- 1st zone start
- 2nd zone start
- full cycle exit

11. PRESENT FULL GOCHARA ENGINE

The Gochara module shall also generate a present-time full planetary transit sheet for all principal planets.

Mandatory present-gochara planet list:
- Sun
- Moon
- Mars
- Mercury
- Jupiter
- Venus
- Saturn
- Rahu
- Ketu

For each planet, the engine shall produce:
- current longitude
- current rashi
- current nakshatra
- current pada
- runtime timestamp
- optional Moon-relative status where applicable

12. CURRENT STATUS OUTPUT

For Saturn specifically, the engine must output:
- current transit rashi
- current nakshatra
- current pada
- whether Saturn is inside or outside the Moon-centric 27-pada belt
- active zone label if inside
- corresponding zone percentage
- related bhava label
- current cycle status: not active / active / upcoming / completed

13. CIRCULAR INDEXING RULE

The zodiac shall be treated as a continuous circular 108-pada field.

If backward counting crosses below pada 1, the index shall wrap to 108.
If forward counting crosses above pada 108, the index shall wrap to 1.

This circular continuity is mandatory for all transit calculations.

14. OUTPUT OBJECTS

The engine must compute and expose clean JSON-ready output objects for both PDF and PWA.

Mandatory Elinati Shani object fields:
- Natal Moon Pada
- Saturn Transit Pada
- Relative Position in 27-Pada Belt
- Active Zone
- Related House
- Saturn Strength
- Moon Strength
- Related Bhava Strength
- Final Zone Percentage
- Grade Label
- Full Cycle Start
- 12th Zone Entry
- 1st Zone Entry
- 2nd Zone Entry
- Full Cycle Exit
- Past/Present/Future Status
- Active MD
- Active AD
- Active PD
- Runtime Timestamp

Mandatory Present Gochara object fields:
- Planet Name
- Longitude
- Rashi
- Nakshatra
- Pada
- Runtime Timestamp

15. PRINT PRODUCTION STRUCTURE

The print engine shall support a clean production-ready gochara report.

Recommended fixed page structure:

Page 1:
Elinati Shani Lifecycle Summary
- all detected cycles
- start/end dates
- past/present/future tags

Page 2:
Current Saturn Micro Status
- natal Moon anchor
- current Saturn pada
- active zone
- formula components
- final percentage

Page 3:
Present Full Planetary Gochara
- all principal planets
- rashi, nakshatra, pada

Page 4:
Dasha Overlap Sheet
- MD / AD / PD active at each Saturn cycle transition date

16. PWA STRUCTURE

For the hosted PWA, the Gochara module shall expose at least the following tabs or views:

- Elinati Shani Summary
- Current Saturn Status
- Present Full Gochara
- Dasha Overlap

17. LANGUAGE AND PRESENTATION RULE

All final user-facing output intended for print or PWA display must comply with the Pure Telugu output rules defined in the core system rules.

Internal code variable names may remain in English for maintainability.
Rendered labels, headings, and narrative output must be in Telugu.

18. GOVERNANCE

This file is the final authority for Gochara computation.
>>>>>>> 0b0fa04 (initial commit)
If any older master file, embedded prompt, or calculation block contradicts this file on transit logic, this file shall override that older content.