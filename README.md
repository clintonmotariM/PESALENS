# PESALENS
An antiscaming data tool to verify transactions.
# PesaLens: Project Brief, Research Summary and Data Plan

**Challenge brief:** Utilization of Funds (KEPRO), circular economy
**Team:** Joy, Victor (team lead), Caleb, Clinton
**Version:** Draft v1, prepared 25 November 2026 (update after the context call)

**Legend**
- ✅ Confirmed from a source (see Sources at the bottom)
- 🔶 Our inference or hypothesis, to be validated
- ❓ Open question, to ask KEPRO

---

## 1. Our team and our role

### 1.1 Who we are (as stated in the team chat)

| Member | Background | Proposed contribution (to be confirmed) |
|---|---|---|
| Joy | CS student, prior Business IT. Python, SQL, data analysis, FastAPI. Creates economics content. | Sector research, financial and business validation, user needs, realism checks on data assumptions |
| Victor (team lead) | AI/ML, Python, data analysis, full-stack. Hackathon experience. | Team coordination, ML pipeline, model design |
| Caleb | BSc Mechatronic Engineering. Python, ML/AI engineering. Previously IoT and embedded systems. | Data engineering, ML models, possible sensor/weighing-data simulation |
| Clinton | Full-stack dev and CS student. React, Node, Python, Supabase. UI/UX, pitching, KRA eTIMS integration. | Data model and schema, prototype app, verification flow, UI/UX, pitch |

Roles are **proposed**. The team agreed to allocate tasks formally after the guidance session. Record the final allocation here once it is settled.

### 1.2 What we have decided so far
- Brief chosen: **Utilization of Funds (KEPRO)**. One open slot remains for a non-technical teammate, depending on matching.
- Joy's framing: close the gap between money spent and actual impact. Example: not just "a waste manager received and spent KSh 500,000" but what it achieved, how much waste was verifiably collected or recycled, and the cost per verified tonne.
- Direction: an AI-powered fund-to-impact intelligence system.
- Process rule (Caleb): start from the data that exists or will be made available.
- Process rule (Victor): research KEPRO itself so we design for its real workflow, then validate on the context call.
- Group call: planned for an evening (date TBC). Context call with the organization: before proposal submission (date TBC).

### 1.3 Our own ideas on the table
- Receipt and expense verification using KRA eTIMS to link spending to proof (Clinton).
- Retail anchor point: informal shops (dukas) as verifiable nodes with identity, stock-in and waste-out records (Clinton, hypothesis only).
- Reuse (refill, shared containers) as a differentiator that needs its own metric.

---

## 2. Research done so far

| Topic | What we looked at | Status |
|---|---|---|
| KEPRO website, About page | Mission, vision, history, model, programs | Done |
| TakaTrace portal | KEPRO's traceability platform and roles | Done |
| Legal framework | Sustainable Waste Management Act 2022, EPR Regulations 2024, plastic packaging rules, enforcement status | Done (needs full-text read) |
| Waste scope | Which product categories KEPRO covers vs other PROs | Done |
| Retail structure | Retail categories in Kenya, informal share | Done |
| eTIMS for small traders | Current KRA requirements and options | Done |
| Not yet done | KEPRO annual reports or impact figures, fee schedule details, how funds are allocated, benchmarking other PROs | To do |

---

## 3. The organization: KEPRO

### 3.1 What it is
- ✅ Kenya Extended Producer Responsibility Organization, a Producer Responsibility Organization (PRO) that brings stakeholders together to manage **non-hazardous post-consumer packaging waste**.
- ✅ Industry-led. Incubated from the Kenya Association of Manufacturers (KAM).
- ✅ Timeline: 2018 mission to Denmark, 2019 Kenya Plastic Action Plan, 2020 model PRO business plan, 2021 KEPRO launched and incorporated.
- ✅ Board represents the private-sector value chain from production to recycling.

### 3.2 Goals
- ✅ **Mission:** build inclusive platforms for players from production to recycling, working toward zero waste and a circular economy.
- ✅ **Vision:** a transparent and impactful EPR scheme that funds awareness and capacity building, moving Kenya from a linear and recycling economy to a circular one.
- ✅ Also states an aim to increase reuse and repair of packaging before recycling.

### 3.3 Why they exist (the reasoning)
- ✅ The 2022 Act and 2024 Regulations make producers responsible for packaging after sale (polluter-pays).
- ✅ Regulations allow a producer to transfer part or all of its EPR obligations to a collective scheme by joining a PRO.
- 🔶 KEPRO lets producers meet the duty collectively instead of each building its own take-back system. Member benefits include assisted compliance, networking, brand credibility and training.

### 3.4 Materials and programs
- ✅ In scope: plastics (flexible, PET, rigid), paper and carton, glass, aluminium, composites.
- ✅ Out of scope (other PROs): hazardous waste, e-waste and batteries. Vehicles and carbon are outside KEPRO's mandate.
- ✅ Programs listed on the site: TakaTrace, Rada Safi, Youth Chapter, Consumer-Led Transformation, Waste Redefined, CE Accelerator Program, Take-Back Model, Recovery and Recycling. We have only read TakaTrace in detail.

### 3.5 Systems
- ✅ **Members Portal / KEPROms:** members declare packaging volumes monthly and download certificates, invoices and tax receipts.
- ✅ **TakaTrace:** traceability and EPR compliance platform with portals for aggregators (receipts, stock, transfers), recyclers (processing, evidence, claims), collectors (deliveries, receipts, payments) and the public (collection points, dumping reports with photo and GPS). Incentives depend on eligibility and verification.

---

## 4. Legal and regulatory frame

| Instrument | What it does for us |
|---|---|
| Sustainable Waste Management Act, 2022 | Core law. Codifies polluter-pays, zero waste and circular economy. Introduces mandatory EPR. Counties must set up materials recovery facilities. |
| Sustainable Waste Management (EPR) Regulations, 2024 (Legal Notice 176) | Operationalizes EPR. Producers register with NEMA, run take-back systems, pay fees tied to volumes, submit annual reports. Importers need an EPR certificate per consignment. PRO payments feed the Restoration Fund. PRO plans must include a product traceability system and financial flows across value-chain actors. False information on quantities is an offence. |
| Plastic Packaging Materials Regulations, 2024 (under EMCA) | Licensing and rules for plastic packaging. Retailers such as Naivas already ask suppliers for an EPR certificate, a PRO membership certificate and a packaging licence. |
| Enforcement | ✅ NEMA announced full enforcement in December 2025 after conservatory court orders were lifted. 🔶 We have not verified whether any litigation remains open. |
| County laws | Waste is a devolved function. Example: Murang'a County has its own waste act and rules. |
| Kenya Data Protection Act, 2019 | Applies to any system handling collector, payment or location data. |
| KRA eTIMS rules | KRA's position is that all businesses, including informal traders, must issue eTIMS invoices. eTIMS Lite exists for non-VAT traders (USSD *222# and eCitizen). Buyer-initiated invoicing exists for small traders. Exemption rules have shifted over time, so verify. |

❓ Fee rates, the basis for calculating fees, and penalty amounts are unconfirmed. Do not build fee logic until we read the gazetted text and hear from KEPRO.

---

## 5. Target clients and stakeholders

### 5.1 Ecosystem map

| Group | Who | What they need |
|---|---|---|
| Payers | Producers: manufacturers, importers, refillers, repackagers, rebranders, brand owners, converters | Proof that fees produced real recovery, and compliance certificates |
| Operator | KEPRO secretariat and board | Prove outcomes, justify spending, manage programs |
| Regulator | NEMA | Annual reports, 5% remittance of membership fees to the Restoration Fund, verified outcomes |
| Chain workers | Collectors, aggregators, recyclers, transporters | Fair, timely payment and a way to prove their work |
| Enforcers and public | Large retailers, counties, consumers | Compliance evidence, clean communities |

### 5.2 Who our solution probably serves
🔶 The buyer is most likely **KEPRO**, with benefits flowing to members (proof), NEMA (verified reporting) and collectors (traceable payment). Tenants, clients and vendors from other app projects do not map directly to this ecosystem. ❓ Confirm on the call.

### 5.3 Retail and the duka hypothesis
- ✅ Retail categories: modern trade (supermarkets), convenience stores, wholesalers and cash-and-carry, informal and traditional trade (dukas, kiosks, market stalls), specialty retail, e-commerce, hospitality and foodservice.
- ✅ Informal trade is the biggest category: estimates cluster around 70% of retail sales and about 80% of FMCG sales. A USDA report puts it at 85-90% of food sales.
- 🔶 Anchor idea: a **verified duka node** with identity, stock-in from vendors and waste-out to collectors, giving a mass balance (packaging in vs packaging recovered).
- Risks: dukas may fear tax exposure if tied to KRA identity, identity is not proof of impact, and unregistered shops could be excluded.
- ❓ Are dukas part of KEPRO's recovery network at all? Does TakaTrace onboard them? If not, we may need another anchor (aggregators or collectors).

---

## 6. How KEPRO is probably handling its goals today

| Area | What we know | Hypothesis and gap |
|---|---|---|
| Membership and fees | ✅ Members register and declare volumes monthly via KEPROms | 🔶 Declarations are self-reported. How they are audited is unknown. |
| Traceability | ✅ TakaTrace records collector, aggregator and recycler activity with evidence | 🔶 Adoption level unknown. Informal actors and retailers may be thinly covered. |
| Fund allocation | ✅ Fees fund recovery, awareness and capacity building | ❓ The split between programs, collectors, recyclers and admin, and who decides it |
| Payments to chain workers | ✅ TakaTrace links payments to eligibility and verification | ❓ Payment channel (M-Pesa, bank, cash) and proof required before payment |
| Impact measurement | ✅ Aims to be "transparent and impactful" | 🔶 Likely tonnes collected and recycled. Cost per verified tonne and reuse likely not tracked. |
| Regulatory reporting | ✅ NEMA requires reports and the Restoration Fund remittance | ❓ Format and how verification is demonstrated |
| Fraud and double-counting | No public information | ❓ Where it actually happens today |

**Gap we are targeting:** a system that links *money in* to *money out* to *verified physical impact*, producing cost per verified tonne, a verification confidence score per claim, and early flags for underperforming or suspicious initiatives.

---

## 7. Problem framing for the AI

### 7.1 Questions our AI should answer
1. What is the **cost per verified tonne** for each program, actor and material?
2. Which claims or payments look **anomalous** (inflated weights, duplicate claims, ghost actors, mismatched location or time)?
3. Which initiatives are **underperforming** relative to the money received?
4. What is the **verification confidence score** for each transaction, based on how much independent evidence supports it?
5. What recovery is **forecast** for the next period, and what funding does it imply?
6. (Stretch) How do **reuse cycles** compare to recycling per shilling spent?

### 7.2 Core principle
The AI is only as good as the data. If KEPRO's real data is limited, we **create realistic, clearly-labeled synthetic data** built on real parameters, with known seeded anomalies so we can measure how well the AI finds them.

### 7.3 Proposed data entities (draft)
- **Member / producer:** id, category, registration status, declared volumes by material and period
- **Fund inflow:** payer, amount, date, period, source type
- **Program / initiative:** id, objective, budget, region, owner
- **Disbursement:** from program to actor, amount, date, payment reference, evidence link
- **Actor:** collector, aggregator, recycler, transporter or duka node, with region, onboarding date, verification level (pseudonymized)
- **Collection event:** actor, material, weight, location, time, evidence
- **Transfer:** between actors, weight, time, both-party confirmation flag
- **Processing record:** recycler input, output, yield loss, date
- **Evidence:** type (photo, GPS, weighbridge ticket, QR scan, M-Pesa reference, eTIMS invoice number, signed confirmation), timestamp, hash
- **Verification result:** transaction, score, reasons
- **Impact metric:** tonnes, cost per tonne, reuse cycles, by program and period

---

## 8. Priority questions for the context call

1. Which funds exactly does "utilization" cover, and who decides how they are spent?
2. Who is the problem for: member trust, NEMA reporting, donor reporting, or internal management?
3. What does TakaTrace already capture, and what is missing?
4. What data can we get (samples, API, anonymized records) and under what restrictions?
5. How will submissions be judged?
6. How are collectors and recyclers paid, and what proof is required first?
7. Where does fraud or double-counting happen today, and how are producer declarations checked?
8. Are dukas or informal retailers part of the network?
9. Is reuse tracked or funded?
10. Is there a pilot route after the challenge?

A longer question list lives with the team chat checklist. Record answers directly under each question after the call.

---

## 9. Task list: from first step to final submission

**Convention:** `[ ]` open, `[x]` done. Owners are *proposed*. A **Gate** is a decision the team must make before moving on.

### Stage 0: Team setup
- [ ] Confirm roles and owners for every stage below (all)
- [ ] Create shared repo and shared drive with this brief as the root document (Clinton)
- [ ] Agree naming conventions, a single data dictionary file and a decisions log (all)
- [ ] Fix the date and time of the group call and the context call (Joy)
- **Gate:** every stage has an owner and a deadline backwards from the submission date (date TBC)

### Stage 1: Deep desk research on KEPRO and the law
- [ ] Read the EPR Regulations 2024 in full. Extract duties, reporting obligations, fee provisions and offences into a table (Joy, Clinton)
- [ ] Read the relevant parts of the Sustainable Waste Management Act 2022 and the NEMA EPR FAQ (Joy)
- [ ] Map every TakaTrace screen and role, and note what data each captures (Clinton)
- [ ] Collect any public KEPRO reports, press and impact figures (Joy)
- [ ] Draw our hypothesis diagram of the money flow from producer to recycler (Clinton)
- [ ] Benchmark how other PROs report impact and verify claims (Victor)
- **Gate:** a one-page "how KEPRO works" the whole team agrees on

### Stage 2: Context call and data discovery
- [ ] Finalize the question list. Assign a speaker and a note-taker (Victor, Joy)
- [ ] Ask explicitly for sample data, field definitions and permitted use
- [ ] Ask what TakaTrace exports (API, CSV, none) and whether dukas are in scope
- [ ] Record all answers in this document and update every 🔶 and ❓ above (note-taker)
- **Gate (data path):**
  - **A:** KEPRO provides real data
  - **B:** partial or anonymized data
  - **C:** no data, synthetic only

### Stage 3: Problem framing and AI use cases
- [ ] Select 3-4 use cases from section 7.1 (all)
- [ ] Write KPI formulas: cost per verified tonne, verification confidence score, underperformance index (Joy, Victor)
- [ ] Decide the anchor: duka node, aggregator, collector, or a combination, based on the call (all)
- [ ] Decide how reuse is measured (cycles, packaging avoided) if it is in scope (Joy)
- **Gate:** a signed-off problem statement and 3-4 AI questions

### Stage 4: Data requirements and schema
- [ ] Turn section 7.3 into an entity-relationship diagram and field-level data dictionary (Clinton)
- [ ] For each AI use case, list the fields needed and where each will come from (Victor, Caleb)
- [ ] Design the evidence model: which proof types count and how they combine into a confidence score (Clinton, Victor)
- [ ] Data protection review: minimize personal data, pseudonymize actors, avoid unnecessary precise location (Joy, Clinton)
- [ ] Create the database schema in Supabase (Clinton)
- **Gate:** schema v1 frozen

### Stage 5: Acquire real and public data
- [ ] Ingest any data from KEPRO into the schema, noting its source and date (Caleb)
- [ ] Gather public parameters: recyclable prices per kg by material, typical collector earnings, transport costs, county waste and population statistics (Joy)
- [ ] Gather registry and regulatory reference data (material categories, counties, producer categories) (Joy)
- [ ] Log every source with licence and retrieval date (Joy)
- **Gate:** parameter sheet exists, with a source or an explicit "assumption" label on each value

### Stage 6: Create the dataset (synthetic where real data is missing)
- [ ] Build the generator parameters from the Stage 5 sheet (Caleb)
- [ ] Generate base entities: producers, programs, funds, actors across counties with realistic clustering (Caleb, Victor)
- [ ] Generate activity: collection events, transfers, processing records, disbursements, with seasonality and realistic yield loss (Caleb)
- [ ] Generate evidence records with realistic gaps (missing photos, late scans, no invoice) (Clinton)
- [ ] Enforce mass balance: material in roughly equals material out, within a plausible loss (Caleb)
- [ ] **Seed labeled anomalies:** inflated weights, duplicate claims, ghost actors, GPS or time mismatches, round-number payments, payments without evidence, colluding clusters (Victor)
- [ ] Use a fixed random seed. Version every dataset and keep a changelog (Caleb)
- [ ] Mark every synthetic file clearly as synthetic, in file names and in the proposal (all)
- **Gate:** dataset v1 produced with ground-truth anomaly labels

### Stage 7: Validate and prepare the data
- [ ] Run data quality checks: duplicates, impossible values, missing fields (Caleb)
- [ ] Business realism review of volumes, prices and cost per tonne against real benchmarks (Joy)
- [ ] Compare distributions to any real data or published figures (Victor)
- [ ] Document known limitations and what the data cannot prove (Joy)
- [ ] Split into train, validation and test, including a held-out scenario (Victor)
- **Gate:** dataset v2 accepted for modeling

### Stage 8: Build the AI components
- [ ] Baseline with simple rules (for example weight vs vehicle capacity, payment without evidence) (Caleb)
- [ ] Compute cost per verified tonne and the underperformance index (Victor)
- [ ] Anomaly detection model and verification confidence scoring (Victor, Caleb)
- [ ] Forecast model for recovery and funding needs, if time allows (Caleb)
- [ ] Grounded natural-language layer: ask questions of the data and generate plain-language reports, answering only from retrieved records (Victor)
- [ ] Explainability: each flag shows the evidence and reasons behind it (Victor, Clinton)
- **Gate:** models beat the rule baseline on the test set

### Stage 9: Build the prototype
- [ ] Dashboard for KEPRO: money in, money out, verified impact, flags (Clinton)
- [ ] Verification flow demo: QR handover scan, two-party confirmation, GPS and timestamp, M-Pesa reference (Clinton)
- [ ] Role views for funder, operator, regulator and collector (Clinton)
- [ ] Low-bandwidth design: a simple capture path for basic phones (Clinton, Caleb)
- [ ] Optional: duka node onboarding flow if the anchor holds (Clinton)
- **Gate:** end-to-end demo works on the generated dataset

### Stage 10: Evaluate
- [ ] Measure anomaly precision and recall against the seeded labels (Victor)
- [ ] Walk through 3 scenarios end to end (honest claim, inflated claim, ghost collector) (all)
- [ ] Record failure cases and limitations honestly (Victor, Joy)
- [ ] Draft the roadmap from synthetic data to a real pilot (Joy)
- **Gate:** evaluation results written up

### Stage 11: Proposal and pitch
- [ ] Narrative: problem, who it serves, solution, why now (Joy, Clinton)
- [ ] Business and impact case grounded in sourced numbers only (Joy)
- [ ] Demo script and slides (Clinton)
- [ ] Q&A preparation covering data realism, fraud, data protection and adoption (all)
- [ ] Dry-run the pitch at least once (all)
- **Gate:** proposal approved by the team lead

### Stage 12: Submit and follow up
- [ ] Final check against the brief and submission rules (Victor)
- [ ] Submit before the deadline (date TBC)
- [ ] Archive the dataset, code and documents (Clinton)
- [ ] If shortlisted, plan a pilot using real KEPRO data (all)

---

## 10. Principles and risks

- **Be honest about synthetic data.** Label it, never present it as real KEPRO data, and show how performance was measured.
- **Do not overclaim.** Every number in the proposal needs a source or an "assumption" tag.
- **Protect people.** Pseudonymize collectors, keep only the location precision we need, and follow the Data Protection Act.
- **Identity is not impact.** Verifying who acted is not the same as verifying what happened. Combine several independent pieces of evidence.
- **Do not lock into dukas too early.** Treat the duka anchor as a hypothesis until the context call answers whether dukas are in KEPRO's network.
- **Keep reuse measurable.** Reuse produces no recycled tonne, so it needs its own metric.

---

## Sources

- KEPRO home: https://www.kepro.co.ke/
- KEPRO About us: https://www.kepro.co.ke/about-us
- TakaTrace: http://takatrace.kepro.co.ke/
- EPR Regulations 2024 (Legal Notice 176) gazette text: https://ke.chm-cbd.net/sites/ke/files/inline-files/L.N._176-177_%20EPR%20and_Water_quality%29%5B1%5D.pdf
- NEMA EPR FAQ: https://nema.go.ke/images/Docs/EPR%20ACT/FAQ_on_EPR_-_15th_March_2025.docx
- Legal overviews: https://www.clydeco.com/en/insights/2025/02/the-extended-producer-responsibility-regulations and https://www.cliffedekkerhofmeyr.com/en/news/publications/2025/Practice/Environmental-Law/environmental-law-alert-23-january-in-pursuit-of-a-circular-economy-kenya-enacts-extended-producer-responsibility-regulations
- Act summary: https://netzerocompare.com/policies/kenya-sustainable-waste-management-act-2022
- Enforcement news: https://www.dawan.africa/news/nema-enforces-2022-waste-law-as-court-blocks-lifted
- Retailer compliance and price concerns: https://www.standardmedia.co.ke/sports/amp/enterprise/article/2001540005/new-regulations-spark-fears-of-price-hikes-for-consumers
- County example (Murang'a): https://muranga.go.ke/resources/policies/002.pdf
- Informal retail share: https://www.technoserve.org/wp-content/uploads/2020/11/Smart-Duka-Developing-Kenyas-Micro-Retail-Sector.pdf and https://chilealimentos.com/wp-content/uploads/2025/06/Retail-Foods-Annual-Tanzania_Nairobi_Kenya_KE2025-0015.pdf
- Retail market overview: https://foodexport.org/assets/Kenya-Market-Assessment-2024.pdf
- eTIMS for small traders: https://peopledaily.digital/business/kra-outlines-three-features-of-a-valid-etims-receipt/amp and https://businessradar.co.ke/?p=10818 and https://techbullion.com/kra-etims-at-the-till-what-a-kenyan-duka-chemist-or-mini-mart-must-do-in-2026/
