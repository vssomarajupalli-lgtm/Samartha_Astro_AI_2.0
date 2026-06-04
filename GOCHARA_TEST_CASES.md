TITLE
SAMARTHA ASTRO-AI SYSTEM 2.0
GOCHARA TEST CASES
VALIDATION AND VERIFICATION SUITE

1. PURPOSE

This file defines the mandatory test-case structure for validating the Samartha Gochara Engine.
It must be used to verify Moon-centric 27-pada indexing, Elinati Shani life-cycle detection, present full planetary gochara generation, and Dasha-linked print integration.

2. TEST CASE FORMAT

Each test case must contain the following blocks:

- Test Case ID
- Native Birth Details
- Natal Moon Reference
- Saturn Transit Reference
- Moon-Centric 27-Pada Belt Mapping
- Zone Identification Result
- Zone Score Result
- Elinati Shani Cycle Dates
- MD / AD / PD Overlap
- Present Full Gochara Validation
- Expected Print Output
- Expected JSON Output

3. MANDATORY INPUT BLOCK

Each test case must include:

- Native Name
- Date of Birth
- Time of Birth
- Place of Birth
- Latitude
- Longitude

All dates must be rendered in DD.MM.YYYY format.

4. NATAL MOON VALIDATION BLOCK

Each test case must verify:

- Natal Moon Rashi
- Natal Moon Nakshatra
- Natal Moon Pada
- Natal Moon 108-Pada Absolute Index
- Natal Moon mapped as Position 14 in the 27-Pada Belt

5. SATURN MICRO GOCHARA VALIDATION BLOCK

For each selected runtime date, validate:

- Saturn Current Longitude
- Saturn Current Rashi
- Saturn Current Nakshatra
- Saturn Current Pada
- Saturn 108-Pada Absolute Index
- Relative Position inside Moon-Centric 27-Pada Belt
- Whether Saturn is inside or outside active belt
- If inside, exact active zone:
  - 12th House Zone
  - 1st House Zone
  - 2nd House Zone

6. ZONE SCORE VALIDATION BLOCK

For every active-zone result, verify:

12th House Zone Score =
(Saturn Strength + Moon Strength + 12th Bhava Strength) / 3

1st House Zone Score =
(Saturn Strength + Moon Strength + 1st Bhava Strength) / 3

2nd House Zone Score =
(Saturn Strength + Moon Strength + 2nd Bhava Strength) / 3

All inputs must be normalized to 0-100 before averaging.

7. ELINATI SHANI LIFE-CYCLE TESTS

Each test suite must verify:

- Full Cycle Start Date
- 12th Zone Entry Date
- 1st Zone Entry Date
- 2nd Zone Entry Date
- Full Cycle Exit Date
- Total Duration
- Status Tag:
  - Past
  - Present
  - Future

The engine must identify all valid cycles across the tested life span.

8. DASHA OVERLAP VALIDATION

For each cycle boundary and zone transition date, validate:

- Active Mahadasha
- Active Antardasha
- Active Pratyantardasha

This validation is mandatory for:
- Full Cycle Start
- 12th Zone Entry
- 1st Zone Entry
- 2nd Zone Entry
- Full Cycle Exit

9. PRESENT FULL GOCHARA VALIDATION

For the runtime date, verify output for:

- Sun
- Moon
- Mars
- Mercury
- Jupiter
- Venus
- Saturn
- Rahu
- Ketu

Each must return:
- Longitude
- Rashi
- Nakshatra
- Pada
- Runtime Timestamp

10. EXPECTED PRINT VALIDATION

Each test case must define expected print blocks:

- Elinati Shani Summary Page
- Current Saturn Status Page
- Present Full Gochara Page
- Dasha Overlap Page

11. EXPECTED JSON OBJECT VALIDATION

Each test case must verify that JSON-ready output contains required fields for:

- Elinati Shani object
- Current Saturn status object
- Present full gochara object
- Dasha overlap object

12. SAMPLE TEST CASE TEMPLATE

Test Case ID:
Native Name:
Date of Birth:
Time of Birth:
Place of Birth:
Latitude:
Longitude:

Natal Moon:
- Rashi:
- Nakshatra:
- Pada:
- Absolute 108-Pada Index:

Runtime Date:
Saturn Transit:
- Longitude:
- Rashi:
- Nakshatra:
- Pada:
- Absolute 108-Pada Index:

27-Pada Belt Result:
- Relative Position:
- Belt Status:
- Active Zone:

Strength Inputs:
- Saturn Strength:
- Moon Strength:
- Related Bhava Strength:

Zone Score:
- Final Percentage:
- Grade Label:

Elinati Shani Cycle:
- Cycle Number:
- Full Start:
- 12th Zone Start:
- 1st Zone Start:
- 2nd Zone Start:
- Full Exit:
- Status:

Dasha Mapping:
- MD:
- AD:
- PD:

Present Gochara Table:
- Sun:
- Moon:
- Mars:
- Mercury:
- Jupiter:
- Venus:
- Saturn:
- Rahu:
- Ketu:

Expected Print Pages:
- Page 1:
- Page 2:
- Page 3:
- Page 4:

Expected JSON Validation:
- Pass / Fail
- Notes

13. GOVERNANCE

No gochara engine implementation shall be treated as production-ready unless it passes the validation format defined in this file.