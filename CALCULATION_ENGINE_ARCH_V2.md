<<<<<<< HEAD
# 📊 SAMARTHA ASTRO-AI SYSTEM 2.0 - MASTER CALCULATION ENGINE SPECIFICATION
## UNIVERSAL MATHEMATICAL EQUATIONS, SHADBALA LOGIC, AND DYNAMIC TRANSIT LIFECYCLE

ఈ సాంకేతిక పత్రం సమర్థ ఆస్ట్రో-AI ఇంజన్ యొక్క కోర్ గణిత సమీకరణాలు, షడ్బల అల్గారిథమ్స్, రాశి/భావ బలాల లెక్కలు, మరియు డైనమిక్ లైఫ్‌లాంగ్ టైమ్‌లైన్ లూప్‌లను వందకు వంద శాతం లాక్ చేస్తుంది. ఏ జాతక ప్రొఫైల్ ఇన్పుట్ ఇచ్చినా, సిస్టమ్ ఇక్కడ నిర్దేశించిన ఫార్ములాల ప్రకారమే రన్‌టైమ్ లో కాలిక్యులేషన్స్ ఎగ్జిక్యూట్ చేయాలి.

---

### 1. DYNAMIC PLANETARY STRENGTH ENGINE (గ్రహబల గణిత విధానము)

సిస్టమ్ ఎక్కడా కూడా గ్రహాల స్థిర శాతాలను (Static Percentages) వాడకూడదు. జాతకుడి జనన కాల గ్రహ రేఖాంశాల (Planetary Longitudes) ఆధారంగా క్లాసికల్ షడ్బల (Shadbala) పద్ధతిలో లైవ్ గా లెక్కించాలి.

#### 1.1. షడ్బల లెక్కింపు సమీకరణం (Core Shadbala Equation)
ప్రతి గ్రహం యొక్క పూర్తి బలాన్ని ($S_{\text{planet}}$) లెక్కించడానికి ఈ క్రింది 6 సాంప్రదాయ బలాల వెక్టార్లను ఇంగెషన్ లూప్ ద్వారా రన్ చేయాలి:
$$\text{Total Shadbala Points (Virupas)} = \text{Sthana Bala} + \text{Dig Bala} + \text{Kala Bala} + \text{Cheshta Bala} + \text{Naisargika Bala} + \text{Drik Bala}$$

* **నార్మలైజేషన్ ఫార్ములా (Normalization)**: లభించిన మొత్తం వీరుపాలను (Virupas) శాస్త్రీయ ప్రమాణాల ఆధారంగా $0\%$ నుండి $100\%$ పరిధిలోకి మార్చాలి.
* **వేరియబుల్ మ్యాపింగ్**: `S_planet[1..9]` = రవి, చంద్ర, కుజ, బుధ, గురు, శుక్ర, శని, రాహు, కేతువుల డైనమిక్ షడ్బల శాతం.

#### 1.2. గ్రహబల గ్రేడింగ్ మరియు ప్యూర్ తెలుగు అవుట్‌పుట్
* $S_{\text{planet}} \ge 75\%$: గ్రేడింగ్ = **`ఉత్తమ బలం`**
* $60\% \le S_{\text{planet}} < 75\%$: గ్రేడింగ్ = **`సాధారణ బలం`**
* $S_{\text{planet}} < 60\%$: గ్రేడింగ్ = **`బలహీనం`**
* **గమనిక**: అవుట్‌పుట్ టేబుల్స్ లో ఎక్కడా ఇంగ్లీష్ పదాలు లేదా బ్రాకెట్లు రాకూడదు.

---

### 2. DYNAMIC 12-BHAVA & RASI STRENGTH ENGINE (భావ - రాశి బలాల విధానము)

#### 2.1. భావబల గణిత సమీకరణం (Bhava Bala Formula)
ప్రతి జాతక ప్రొఫైల్ యొక్క కచ్చితమైన లగ్న స్ఫుటాన్ని బట్టి 12 భావాల బలాలను ఈ క్రింది సూత్రం ద్వారా డైనమిక్‌గా లెక్కించాలి:
$$\text{Final Bhava Strength } (Bhava\_Bala) = S_{\text{lord}} \text{ (భావాధిపతి షడ్బల బలం)} + \text{Bhava Drishti Bala} + \text{Kendra Dig-Bala Modifier}$$

#### 2.2. అష్టకవర్గ (SAV) మరియు రాశిఫల లాజిక్ అనుసంధానం
* `sav_score[1..12]` = గ్రహాల బిందువుల ఆధారంగా 12 రాశి చక్ర గృహాలకు లభించే సముదాయ అష్టకవర్గ స్కోర్ (0 నుండి 56 వరకు).
* **రాశిఫల కాలిక్యులేషన్**: సదరు భావంలో ఉన్న గ్రహాలు + భావాధిపతి షడ్బల బలం (`S_planet[Lord]`) + ఆ రాశి యొక్క `sav_score` మూడింటినీ ఇంటరెక్ట్ చేసి ఫలిత తీవ్రతను లెక్కించాలి.
* **వేరియబుల్స్**: `bhava_strength[1..12]` మరియు `bhava_lord[1..12]`.

---

### 3. PHASE 2 TIMELINE ENGINE: LIFELONG TRI-PLANETARY LIFECYCLE LOOP (MD-AD-PD విధానము)

#### 3.1. నిరంతర జీవిత కాల లూప్ నియమం (Continuous Ingestion Scope)
జాతకుడి జనన సమయం నుండి ప్రారంభించి, 120 సంవత్సరాల పూర్తి జీవిత కాల వింశోత్తరి దశా క్రమాన్ని (కుజ, రాహు, గురు, శని, బుధ, కేతు, శుక్ర) ఎలాంటి కటింగ్స్ లేకుండా నిరంతరాయంగా లూప్ చేయాలి. ప్రతి మహాదశ లోని 9 అంతర్దశలను, మరియు ప్రతి అంతర్దశ లోని 9 ప్రత్యంతర్దశల (MD -> AD -> PD) టైమ్‌లైన్ రోస్ అన్నింటినీ విడివిడిగా జనరేట్ చేయాలి.

#### 3.2. త్రి-ग्रह సగటు సమీకరణం మరియు సీలింగ్ రౌండింగ్ (Tri-Planetary Average & Ceiling Rounding)
ప్రతి ప్రత్యంతర్దశ (PD) రో లోనూ, ఆయా కాలాలకు అధిపతులైన మూడు గ్రహాల షడ్బల బలాలను కలిపి, డివైడెడ్ బై మూడు చేస్తూ రన్‌టైమ్ లో పర్సంటేజీని లెక్కించాలి:
$$\text{PD Final Output Value (\%)} = \left\lceil \frac{S_{\text{planet}}[\text{MD\_Lord}] + S_{\text{planet}}[\text{AD\_Lord}] + S_{\text{planet}}[\text{PD\_Lord}]}{3} \right\rceil$$

* **సీలింగ్ రౌండింగ్ రూల్**: భాగహారం చేసినప్పుడు వచ్చే దశాంశ విలువలను (Floating values) కచ్చితంగా `math.ceil` ఉపయోగించి తదుపరి పూర్ణ సంఖ్యకు (Next Highest Integer) రౌండ్ అప్ చేయాలి.

#### 3.3. కాలిక్యులేషన్ ఉదాహరణ మరియు అవుట్‌పుట్ వెరిఫికేషన్ (Calculation Example & Output Standard)
* **Sample Input Data**: శని షడ్బల బలం = 75% | గురు షడ్బల బలం = 76% | బుధ షడ్బల బలం = 78%.
* **Target Node Path**: శని మహాదశ (MD) -> గురు అంతర్దశ (AD) -> బుధ ప్రత్యంతర్దశ (PD).
* **Execution Mathematical Step**: 
  $$\text{Value} = \frac{75 + 76 + 78}{3} = \frac{229}{3} = 76.333\%$$
* **Expected Output Standard**: సిస్టమ్ దీనిని పక్కాగా **`77%`** గా రౌండ్ అప్ చేసి, టైమ్‌లైన్ టేబుల్‌లో సదరు `DD.MM.YYYY` తేదీల పక్కన డిస్ప్లే చేస్తుంది.

---
### 4. SAMARTHA MICRO-PADA GOCHARA ENGINE (గోచార క్యాలిక్యులేషన్ విధానము)
All Samartha True Micro Gochara logic, lifecycle Saturn period computation, present planetary transit logic, and Dasha-linked transit printing rules are defined in GOCHARA_ENGINE_MASTER.md
This calculation architecture file shall treat GOCHARA_ENGINE_MASTER.md as the authoritative transit engine specification.
*
* ### 5. 5-అంచెల ప్రశ్నల మ్యాచింగ్ విధానం (Proprietary 5-Tier Questionnaire)
ప్రామాణిక ప్రశ్నలకు ప్రిడిక్టివ్ ప్రాబబిలిటీ స్కోర్‌ను లెక్కించడానికి ఈ క్రింది నిర్దేశిత భిన్న విభజన సమీకరణాన్ని ( UI లో `40:30:15:10:5` Metric Engine) వాడాలి:
$$\text{Final Question Score} = (0.40 \times S_{\text{lord}}) + (0.30 \times S_{\text{karaka}}) + (0.15 \times S_{\text{D9}}) + (0.10 \times S_{\text{varga}}) + (0.05 \times 20) + \text{Bonus}$$
* **వర్గోత్తమ బోనస్ & 100% పరిమితి రూల్**: భావాధిపతి వర్గోత్తమ స్థితిలో ఉంటే `+5%` బోనస్ కలపాలి. కానీ మొత్తం స్కోరు 100% దాటిపోకుండా ఒక హార్డ్ క్యాప్ పెట్టాలి (`if final_question_score > 100: final_question_score = 100`).

---

### 6. SOURCE REPORT CLEANUP & SUPPRESSION DIRECTIVE (తీసివేయాల్సిన అంశాలు)

85 పేజీల బేస్‌లైన్ డేటా నుండి లేఅవుట్ కన్ఫ్యూజన్‌ను తొలగించడానికి ఈ క్రింది విభాగాలను కంపైల్ టైమ్ లో **పూర్తిగా suppressed మరియు డిస్కార్డ్** చేయాలి:
* **అవకహడ చక్రం** (Avakahada Chakra)
* **ఘాత చక్రం** (Ghata Chakra)
* **పంచధా మైత్రి చక్రము** (Panchadha Maitri Chakra)
* **జైమిని కారకాలు** (Jaimini Karakas)
* **జైమిని ఆరుఢములు** (Jaimini Arudhas)

---

### 7. MULTI-MODE AUTOMATED PRINTING & DOWNLOADING PROCEDURE

#### 7.1. ఆటోమేటిక్ డెస్క్‌టాప్ జనరేషన్ (Instant Execution)
సిస్టమ్ లోకల్ ఎన్విరాన్‌మెంట్‌లో రన్ అవ్వగానే, ఎలాంటి మాన్యువల్ వెయిటింగ్ లేకుండా బ్యాక్‌గ్రౌండ్ లో పిడిఎఫ్ ఫైల్స్ జనరేట్ అయి డీఫాల్ట్ పాత్ లో సేవ్ అయిపోవాలి.

#### 7.2. డ్యూయల్ డౌన్‌లోడ్ ఆప్షన్స్ టాగుల్ (Dual Mode Selection)
వెబ్‌సైట్ మరియు పిడిఎఫ్ కంపైలర్ లో యూజర్ సెలెక్షన్ కోసం ఈ క్రింది డౌన్‌లోడింగ్ ఆప్షన్స్ ఉండాలి:
1. **Four Isolated Segment PDF Files**: నాలుగు విడివిడి పిడిఎఫ్ రిపోర్టులు.
2. **Single Unified Master Document PDF**: అన్ని మోడ్యూల్స్ కలిపిన ఒకే ఒక్క మాస్టర్ పిడిఎఫ్ డాక్యుమెంట్.

---

### 8. MANDATORY EVERY SECTION COVER PAGE SPECIFICATION (కవర్ పేజీ ప్రొసీజర్)

రిపోర్ట్ ఒకే ఫైల్ గా వచ్చినా లేదా నాలుగు విడివిడి సెగ్మెంట్లుగా వచ్చినా, **ప్రతి విభాగం ప్రారంభంలోనూ ఒక స్టాండర్డ్ పేజీ 1 (కవర్ పేజీ)** విధిగా ప్రింట్ అవ్వాలి.

#### 8.1. కవర్ పేజీ లేఅవుట్ పారామితులు (Cover Page Render Parameters)
ప్రతి కవర్ పేజీ పైన ఈ క్రింది డేటా ఫీల్డ్స్ మాత్రమే ప్యూర్ తెలుగు ప్రెజెంటేషన్ ఫిల్టర్ తో డిస్ప్లే అవ్వాలి:
* **శీర్షిక బ్రాండింగ్**: సమర్థవాస్తు (Footprint < 5MB Logo Slot)
* **విభాగం పేరు (Section Title)**: (ఉదాహరణకు: `12 భావాల బలాల సమగ్ర నివేదిక`)
* **జనన కాల వివరాలు (Birth Details Box)**:
  * జాతకుడి పేరు (Native Name)
  * జనన తేదీ (Date of Birth - formatted as `DD.MM.YYYY`)
  * జనన సమయం (Time of Birth)
  * జనన స్థలం (Place of Birth)
  * అక్షాంశం / రేఖాంశం (Latitude / Longitude)
=======
# 📊 SAMARTHA ASTRO-AI SYSTEM 2.0 - MASTER CALCULATION ENGINE SPECIFICATION
## UNIVERSAL MATHEMATICAL EQUATIONS, SHADBALA LOGIC, AND DYNAMIC TRANSIT LIFECYCLE

ఈ సాంకేతిక పత్రం సమర్థ ఆస్ట్రో-AI ఇంజన్ యొక్క కోర్ గణిత సమీకరణాలు, షడ్బల అల్గారిథమ్స్, రాశి/భావ బలాల లెక్కలు, మరియు డైనమిక్ లైఫ్‌లాంగ్ టైమ్‌లైన్ లూప్‌లను వందకు వంద శాతం లాక్ చేస్తుంది. ఏ జాతక ప్రొఫైల్ ఇన్పుట్ ఇచ్చినా, సిస్టమ్ ఇక్కడ నిర్దేశించిన ఫార్ములాల ప్రకారమే రన్‌టైమ్ లో కాలిక్యులేషన్స్ ఎగ్జిక్యూట్ చేయాలి.

---

### 1. DYNAMIC PLANETARY STRENGTH ENGINE (గ్రహబల గణిత విధానము)

సిస్టమ్ ఎక్కడా కూడా గ్రహాల స్థిర శాతాలను (Static Percentages) వాడకూడదు. జాతకుడి జనన కాల గ్రహ రేఖాంశాల (Planetary Longitudes) ఆధారంగా క్లాసికల్ షడ్బల (Shadbala) పద్ధతిలో లైవ్ గా లెక్కించాలి.

#### 1.1. షడ్బల లెక్కింపు సమీకరణం (Core Shadbala Equation)
ప్రతి గ్రహం యొక్క పూర్తి బలాన్ని ($S_{\text{planet}}$) లెక్కించడానికి ఈ క్రింది 6 సాంప్రదాయ బలాల వెక్టార్లను ఇంగెషన్ లూప్ ద్వారా రన్ చేయాలి:
$$\text{Total Shadbala Points (Virupas)} = \text{Sthana Bala} + \text{Dig Bala} + \text{Kala Bala} + \text{Cheshta Bala} + \text{Naisargika Bala} + \text{Drik Bala}$$

* **నార్మలైజేషన్ ఫార్ములా (Normalization)**: లభించిన మొత్తం వీరుపాలను (Virupas) శాస్త్రీయ ప్రమాణాల ఆధారంగా $0\%$ నుండి $100\%$ పరిధిలోకి మార్చాలి.
* **వేరియబుల్ మ్యాపింగ్**: `S_planet[1..9]` = రవి, చంద్ర, కుజ, బుధ, గురు, శుక్ర, శని, రాహు, కేతువుల డైనమిక్ షడ్బల శాతం.

#### 1.2. గ్రహబల గ్రేడింగ్ మరియు ప్యూర్ తెలుగు అవుట్‌పుట్
* $S_{\text{planet}} \ge 75\%$: గ్రేడింగ్ = **`ఉత్తమ బలం`**
* $60\% \le S_{\text{planet}} < 75\%$: గ్రేడింగ్ = **`సాధారణ బలం`**
* $S_{\text{planet}} < 60\%$: గ్రేడింగ్ = **`బలహీనం`**
* **గమనిక**: అవుట్‌పుట్ టేబుల్స్ లో ఎక్కడా ఇంగ్లీష్ పదాలు లేదా బ్రాకెట్లు రాకూడదు.

---

### 2. DYNAMIC 12-BHAVA & RASI STRENGTH ENGINE (భావ - రాశి బలాల విధానము)

#### 2.1. భావబల గణిత సమీకరణం (Bhava Bala Formula)
ప్రతి జాతక ప్రొఫైల్ యొక్క కచ్చితమైన లగ్న స్ఫుటాన్ని బట్టి 12 భావాల బలాలను ఈ క్రింది సూత్రం ద్వారా డైనమిక్‌గా లెక్కించాలి:
$$\text{Final Bhava Strength } (Bhava\_Bala) = S_{\text{lord}} \text{ (భావాధిపతి షడ్బల బలం)} + \text{Bhava Drishti Bala} + \text{Kendra Dig-Bala Modifier}$$

#### 2.2. అష్టకవర్గ (SAV) మరియు రాశిఫల లాజిక్ అనుసంధానం
* `sav_score[1..12]` = గ్రహాల బిందువుల ఆధారంగా 12 రాశి చక్ర గృహాలకు లభించే సముదాయ అష్టకవర్గ స్కోర్ (0 నుండి 56 వరకు).
* **రాశిఫల కాలిక్యులేషన్**: సదరు భావంలో ఉన్న గ్రహాలు + భావాధిపతి షడ్బల బలం (`S_planet[Lord]`) + ఆ రాశి యొక్క `sav_score` మూడింటినీ ఇంటరెక్ట్ చేసి ఫలిత తీవ్రతను లెక్కించాలి.
* **వేరియబుల్స్**: `bhava_strength[1..12]` మరియు `bhava_lord[1..12]`.

---

### 3. PHASE 2 TIMELINE ENGINE: LIFELONG TRI-PLANETARY LIFECYCLE LOOP (MD-AD-PD విధానము)

#### 3.1. నిరంతర జీవిత కాల లూప్ నియమం (Continuous Ingestion Scope)
జాతకుడి జనన సమయం నుండి ప్రారంభించి, 120 సంవత్సరాల పూర్తి జీవిత కాల వింశోత్తరి దశా క్రమాన్ని (కుజ, రాహు, గురు, శని, బుధ, కేతు, శుక్ర) ఎలాంటి కటింగ్స్ లేకుండా నిరంతరాయంగా లూప్ చేయాలి. ప్రతి మహాదశ లోని 9 అంతర్దశలను, మరియు ప్రతి అంతర్దశ లోని 9 ప్రత్యంతర్దశల (MD -> AD -> PD) టైమ్‌లైన్ రోస్ అన్నింటినీ విడివిడిగా జనరేట్ చేయాలి.

#### 3.2. త్రి-ग्रह సగటు సమీకరణం మరియు సీలింగ్ రౌండింగ్ (Tri-Planetary Average & Ceiling Rounding)
ప్రతి ప్రత్యంతర్దశ (PD) రో లోనూ, ఆయా కాలాలకు అధిపతులైన మూడు గ్రహాల షడ్బల బలాలను కలిపి, డివైడెడ్ బై మూడు చేస్తూ రన్‌టైమ్ లో పర్సంటేజీని లెక్కించాలి:
$$\text{PD Final Output Value (\%)} = \left\lceil \frac{S_{\text{planet}}[\text{MD\_Lord}] + S_{\text{planet}}[\text{AD\_Lord}] + S_{\text{planet}}[\text{PD\_Lord}]}{3} \right\rceil$$

* **సీలింగ్ రౌండింగ్ రూల్**: భాగహారం చేసినప్పుడు వచ్చే దశాంశ విలువలను (Floating values) కచ్చితంగా `math.ceil` ఉపయోగించి తదుపరి పూర్ణ సంఖ్యకు (Next Highest Integer) రౌండ్ అప్ చేయాలి.

#### 3.3. కాలిక్యులేషన్ ఉదాహరణ మరియు అవుట్‌పుట్ వెరిఫికేషన్ (Calculation Example & Output Standard)
* **Sample Input Data**: శని షడ్బల బలం = 75% | గురు షడ్బల బలం = 76% | బుధ షడ్బల బలం = 78%.
* **Target Node Path**: శని మహాదశ (MD) -> గురు అంతర్దశ (AD) -> బుధ ప్రత్యంతర్దశ (PD).
* **Execution Mathematical Step**: 
  $$\text{Value} = \frac{75 + 76 + 78}{3} = \frac{229}{3} = 76.333\%$$
* **Expected Output Standard**: సిస్టమ్ దీనిని పక్కాగా **`77%`** గా రౌండ్ అప్ చేసి, టైమ్‌లైన్ టేబుల్‌లో సదరు `DD.MM.YYYY` తేదీల పక్కన డిస్ప్లే చేస్తుంది.

---
### 4. SAMARTHA MICRO-PADA GOCHARA ENGINE (గోచార క్యాలిక్యులేషన్ విధానము)
All Samartha True Micro Gochara logic, lifecycle Saturn period computation, present planetary transit logic, and Dasha-linked transit printing rules are defined in GOCHARA_ENGINE_MASTER.md
This calculation architecture file shall treat GOCHARA_ENGINE_MASTER.md as the authoritative transit engine specification.
*
* ### 5. 5-అంచెల ప్రశ్నల మ్యాచింగ్ విధానం (Proprietary 5-Tier Questionnaire)
ప్రామాణిక ప్రశ్నలకు ప్రిడిక్టివ్ ప్రాబబిలిటీ స్కోర్‌ను లెక్కించడానికి ఈ క్రింది నిర్దేశిత భిన్న విభజన సమీకరణాన్ని ( UI లో `40:30:15:10:5` Metric Engine) వాడాలి:
$$\text{Final Question Score} = (0.40 \times S_{\text{lord}}) + (0.30 \times S_{\text{karaka}}) + (0.15 \times S_{\text{D9}}) + (0.10 \times S_{\text{varga}}) + (0.05 \times 20) + \text{Bonus}$$
* **వర్గోత్తమ బోనస్ & 100% పరిమితి రూల్**: భావాధిపతి వర్గోత్తమ స్థితిలో ఉంటే `+5%` బోనస్ కలపాలి. కానీ మొత్తం స్కోరు 100% దాటిపోకుండా ఒక హార్డ్ క్యాప్ పెట్టాలి (`if final_question_score > 100: final_question_score = 100`).

---

### 6. SOURCE REPORT CLEANUP & SUPPRESSION DIRECTIVE (తీసివేయాల్సిన అంశాలు)

85 పేజీల బేస్‌లైన్ డేటా నుండి లేఅవుట్ కన్ఫ్యూజన్‌ను తొలగించడానికి ఈ క్రింది విభాగాలను కంపైల్ టైమ్ లో **పూర్తిగా suppressed మరియు డిస్కార్డ్** చేయాలి:
* **అవకహడ చక్రం** (Avakahada Chakra)
* **ఘాత చక్రం** (Ghata Chakra)
* **పంచధా మైత్రి చక్రము** (Panchadha Maitri Chakra)
* **జైమిని కారకాలు** (Jaimini Karakas)
* **జైమిని ఆరుఢములు** (Jaimini Arudhas)

---

### 7. MULTI-MODE AUTOMATED PRINTING & DOWNLOADING PROCEDURE

#### 7.1. ఆటోమేటిక్ డెస్క్‌టాప్ జనరేషన్ (Instant Execution)
సిస్టమ్ లోకల్ ఎన్విరాన్‌మెంట్‌లో రన్ అవ్వగానే, ఎలాంటి మాన్యువల్ వెయిటింగ్ లేకుండా బ్యాక్‌గ్రౌండ్ లో పిడిఎఫ్ ఫైల్స్ జనరేట్ అయి డీఫాల్ట్ పాత్ లో సేవ్ అయిపోవాలి.

#### 7.2. డ్యూయల్ డౌన్‌లోడ్ ఆప్షన్స్ టాగుల్ (Dual Mode Selection)
వెబ్‌సైట్ మరియు పిడిఎఫ్ కంపైలర్ లో యూజర్ సెలెక్షన్ కోసం ఈ క్రింది డౌన్‌లోడింగ్ ఆప్షన్స్ ఉండాలి:
1. **Four Isolated Segment PDF Files**: నాలుగు విడివిడి పిడిఎఫ్ రిపోర్టులు.
2. **Single Unified Master Document PDF**: అన్ని మోడ్యూల్స్ కలిపిన ఒకే ఒక్క మాస్టర్ పిడిఎఫ్ డాక్యుమెంట్.

---

### 8. MANDATORY EVERY SECTION COVER PAGE SPECIFICATION (కవర్ పేజీ ప్రొసీజర్)

రిపోర్ట్ ఒకే ఫైల్ గా వచ్చినా లేదా నాలుగు విడివిడి సెగ్మెంట్లుగా వచ్చినా, **ప్రతి విభాగం ప్రారంభంలోనూ ఒక స్టాండర్డ్ పేజీ 1 (కవర్ పేజీ)** విధిగా ప్రింట్ అవ్వాలి.

#### 8.1. కవర్ పేజీ లేఅవుట్ పారామితులు (Cover Page Render Parameters)
ప్రతి కవర్ పేజీ పైన ఈ క్రింది డేటా ఫీల్డ్స్ మాత్రమే ప్యూర్ తెలుగు ప్రెజెంటేషన్ ఫిల్టర్ తో డిస్ప్లే అవ్వాలి:
* **శీర్షిక బ్రాండింగ్**: సమర్థవాస్తు (Footprint < 5MB Logo Slot)
* **విభాగం పేరు (Section Title)**: (ఉదాహరణకు: `12 భావాల బలాల సమగ్ర నివేదిక`)
* **జనన కాల వివరాలు (Birth Details Box)**:
  * జాతకుడి పేరు (Native Name)
  * జనన తేదీ (Date of Birth - formatted as `DD.MM.YYYY`)
  * జనన సమయం (Time of Birth)
  * జనన స్థలం (Place of Birth)
  * అక్షాంశం / రేఖాంశం (Latitude / Longitude)
>>>>>>> 0b0fa04 (initial commit)
* **రన్‌టైమ్ టైమ్‌స్టాంప్ (Execution Timestamp)**: సదరు రిపోర్ట్ ప్రింట్ తీసిన కచ్చితమైన తేదీ మరియు సమయం (మైక్రో గోచార బేస్‌లైన్ స్థిరత్వం కోసం).