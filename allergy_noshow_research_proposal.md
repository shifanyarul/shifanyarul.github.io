# Modeling Regret: How Symptom Decay Predicts Missed Appointments

### Projection Bias, Booking Lead Time, and No-Show Behavior in an Outpatient Allergy Clinic

*Research Proposal — Draft for Departmental Review*

---

## Abstract

Missed appointments ("no-shows") impose substantial costs on outpatient clinics through lost revenue, idle provider time, and delayed care for other patients. While appointment lead time (the gap between booking date and appointment date) is a well-established predictor of no-shows across specialties, the behavioral mechanism behind this relationship remains underexplored — and allergy clinics offer a uniquely powerful setting to study it. Allergy symptoms fluctuate predictably with environmental allergen levels, meaning a patient's motivational state at booking can be objectively proxied using public pollen count data. Drawing on the behavioral economics concepts of projection bias (Loewenstein, O'Donoghue & Rabin, 2003) and the hot-cold empathy gap (Loewenstein, 2005), this study hypothesizes that patients who book appointments during high-symptom ("hot-state") periods systematically overestimate their future demand for care; when the appointment arrives after symptoms have subsided, attendance drops. Using approximately [N] de-identified appointment records from [Clinic Name]'s allergy department over [X years], combined with daily local pollen count data, we will model no-show probability as a function of booking lead time, pollen conditions at booking versus at appointment, time of day, day of week, and season. We predict that no-show risk is highest for appointments booked during pollen peaks with long lead times that land in low-pollen periods — a "symptom-decay" effect consistent with projection bias. Findings will directly inform scheduling policy: optimizing slot templates by season, capping booking lead times during peak allergen periods, and targeting reminders to high-risk bookings, reducing no-show-related losses at essentially zero implementation cost.

---

## 1. Background and Significance

### 1.1 The no-show problem

No-shows disrupt clinic operations, waste provider capacity, reduce revenue, and delay access for other patients. Appointment lead time is consistently among the strongest predictors of non-attendance in the literature. In an ophthalmology clinic, no-show rates rose from 9.1% for appointments booked 0–2 weeks out to 38.3% for those booked six months out (McMullen & Netland, 2015). DuMontier et al. found no-show rates of 8%, 16%, and 22% for lead times of 0–3, 4–6, and 28–30 days respectively. In a large Iranian outpatient sample (N = 148,077), lead time over two weeks carried an odds ratio of 1.80 for no-show and was identified as the main predictor of non-attendance (Mohammadi et al., 2018). In pediatric subspecialty clinics, no-show rates roughly doubled (23% vs. 47%) when lead time exceeded 30 days.

What this literature largely treats as a mechanical "decay" effect, behavioral economics can explain as a predictable error in self-forecasting — and the allergy clinic is an ideal laboratory for testing that explanation.

### 1.2 The behavioral economics framework

**Projection bias.** Loewenstein, O'Donoghue, and Rabin (2003) formalized projection bias: people understand qualitatively that their tastes and states change over time, but systematically underestimate the magnitude of that change, projecting their current state onto their future self. Field evidence is robust. Conlin, O'Donoghue, and Vogelsang (2007) showed that catalog orders of cold-weather gear are over-influenced by the weather on the order date: a 30°F drop in order-date temperature raised the probability the item was later returned by roughly 4% — buyers in a cold "state" overestimated how much they would value warm gear once the weather (and their state) changed. Busse et al. (2015) documented the same pattern in car and housing purchases.

An allergy appointment is structurally identical to that catalog order. A patient suffering through a pollen spike (the "order date") books a specialist appointment for several weeks later (the "delivery date"). If pollen levels — and therefore symptoms — have declined by the appointment date, the projected demand for care evaporates, and the patient "returns the item" by not showing up.

**The hot-cold empathy gap.** Loewenstein (2005) describes how people in affectively "hot" visceral states (pain, discomfort, fear) overestimate the stability of their current preferences, while people in "cold" states underestimate how much hot states drive behavior. A congested, sneezing, miserable patient calling the clinic is in a hot state: at that moment, seeing an allergist feels urgent and certain. Weeks later, symptom-free in a cold state, the same patient cannot fully access that earlier urgency — the appointment now feels skippable. Loewenstein specifically notes that hot-cold gaps distort medical decision making, including leading healthy (cold-state) individuals to underweight future health needs.

**Why the allergy clinic is the ideal test bed.** In most specialties, the patient's symptom state at booking is unobservable. In allergy, it has an objective, publicly available, exogenous proxy: the daily aeroallergen (pollen) count. Saha et al. (2021) demonstrated across 28 U.S. metropolitan areas that daily pollen severity is tightly linked to allergic-rhinitis physician visits and allergy medication fills — confirming that pollen counts meaningfully track population symptom burden and care-seeking. This allows us to measure, for every appointment, the "hotness" of the booking moment and the "coldness" of the appointment moment, and test projection bias with field data — without collecting any clinical information about individual patients.

### 1.3 Significance for providers

If the symptom-decay mechanism is confirmed, the operational implications are immediate and low-cost: (a) compress booking lead times during pollen peaks (the patients most motivated to book are also most likely to no-show if made to wait); (b) build seasonal overbooking models that incorporate booking-date pollen conditions rather than appointment-date conditions alone; (c) target reminder outreach to "hot-booked, cold-arriving" appointments, the highest-risk category; and (d) redesign slot templates around the day-of-week and time-of-day patterns identified. Each of these acts on the schedule, not the patient, requiring no new clinical resources.

---

## 2. Research Questions

**RQ1.** Which scheduling characteristics (booking lead time, time of day, day of week, month/season) predict no-show probability in the allergy clinic?

**RQ2.** Does the patient's inferred symptom state at booking — proxied by the local pollen count on the booking date — predict attendance, independent of lead time?

**RQ3 (core behavioral question).** Is no-show probability highest when an appointment was booked under high pollen conditions but occurs under low pollen conditions (i.e., does the *change* in allergen conditions between booking and appointment — "symptom decay" — predict non-attendance beyond either condition alone)?

---

## 3. Hypotheses

**H1 (Lead time).** No-show probability increases with booking lead time, replicating prior literature in the allergy setting.

**H2 (Hot-state booking).** Appointments booked on high-pollen days have elevated no-show risk relative to appointments booked on low-pollen days, controlling for lead time — because hot-state bookings reflect transient, state-driven demand.

**H3 (Symptom decay / projection bias — primary hypothesis).** The interaction between booking-date pollen and appointment-date pollen predicts no-shows: risk is highest for appointments booked at high pollen that occur at low pollen, and lowest for appointments where allergen conditions at arrival match or exceed conditions at booking. Formally, no-show probability increases with Δ = (booking-date pollen − appointment-date pollen).

**H4 (Slot characteristics).** No-show rates vary systematically by time of day and day of week (e.g., early-morning and Monday slots, and post-weekend or post-holiday slots, show elevated no-show rates), consistent with default acceptance of poorly fitting slots.

---

## 4. Variables

### 4.1 Outcome variable

| Variable | Definition | Type |
|---|---|---|
| Attendance status | Attended / no-show (primary); cancellations and reschedules coded separately for sensitivity analyses | Binary (primary); categorical (secondary) |

### 4.2 Predictor variables

| Variable | Definition | Source | Type |
|---|---|---|---|
| Booking lead time | Days between booking date and appointment date | Scheduling system | Continuous (also binned: 0–7, 8–14, 15–30, 31–60, 60+ days) |
| Booking-date pollen index | Local total pollen count (or severity tier) on the date the appointment was booked | Public pollen monitoring data (e.g., National Allergy Bureau station / local counts) | Continuous or ordinal (low/moderate/high/very high) |
| Appointment-date pollen index | Same measure on the appointment date | Same | Continuous or ordinal |
| Symptom-decay score (Δ) | Booking-date pollen − appointment-date pollen | Derived | Continuous |
| Time of day | Slot start hour (binned: early morning, late morning, early afternoon, late afternoon) | Scheduling system | Categorical |
| Day of week | Mon–Fri (and Sat if applicable) | Scheduling system | Categorical |
| Season / month | Appointment month; allergen season indicator (tree / grass / weed / off-season for the local region) | Derived + pollen data | Categorical |
| Visit type | New patient vs. follow-up (if available without clinical detail) | Scheduling system | Binary |

### 4.3 Covariates / controls

| Variable | Rationale |
|---|---|
| Weather on appointment date (precipitation, temperature) | Bad weather independently raises no-shows; also correlates with pollen — must be separated from the pollen effect |
| Holiday / school-break proximity | Known attendance disruptor |
| Clinic volume on appointment date | Capacity and wait-time effects |
| Reminder sent (yes/no, type), if logged | Reminders reduce no-shows and may be unevenly applied |
| Calendar year | Secular trends (e.g., telehealth shifts, policy changes) |

*Deliberately excluded:* patient names, MRNs, dates of birth, addresses, diagnoses, test results, and all other clinical or demographic identifiers. The analysis requires only appointment-level scheduling fields. If age group or coarse home-distance bands are later deemed valuable, they will be added only with explicit IRB approval as a limited data set.

### 4.4 Key data feasibility requirement

The entire symptom-decay analysis depends on the scheduling system retaining the **original booking date** for each appointment (not just the appointment date). Confirming that this field exists and is exportable is the first feasibility step.

---

## 5. Data and Methods

### 5.1 Data sources

1. **Scheduling extract:** all allergy department appointments over the study window ([suggested: 3–5 years] to capture multiple full allergen seasons), with booking date, appointment date/time, attendance status, and visit type. De-identified at extraction.
2. **Pollen data:** daily counts from the nearest certified pollen monitoring station, by allergen category (tree, grass, weed, mold), for the same window. For the San Francisco Bay Area, tree pollen typically peaks roughly February–May and grass roughly April–June, providing strong within-year variation.
3. **Weather data:** daily temperature and precipitation from NOAA for the clinic's location.

### 5.2 Analytic plan

**Descriptive phase.** No-show rates by lead-time bin, slot time, day of week, month, and pollen tier; visualization of appointment *booking* volume against the pollen curve (testing whether bookings spike during pollen peaks — the "hot-state demand" signature) and no-show rates across the season.

**Primary models.** Logistic regression (or mixed-effects logistic regression if repeat patients can be linked via an anonymized ID) predicting no-show:

- Model 1: lead time + slot characteristics + season + controls (tests H1, H4)
- Model 2: Model 1 + booking-date pollen + appointment-date pollen (tests H2)
- Model 3: Model 2 + booking×appointment pollen interaction, or equivalently the Δ symptom-decay term (tests H3 — the projection-bias signature)

**Robustness checks.** Alternative pollen lags (patients may book a few days after a spike begins); excluding immunotherapy shot visits (which follow fixed schedules and dilute booking-driven behavior) or analyzing them separately; cancellations-included sensitivity analysis; weather-only falsification model (if "weather at booking" predicts no-shows as strongly as pollen does for non-allergy reasons, the mechanism is questionable — pollen should outperform generic weather in an allergy population specifically).

**Optional extension.** A simple gradient-boosted or regularized prediction model to estimate per-slot no-show risk for operational use, benchmarked against the literature (AUCs around 0.65–0.72 are typical for administrative-data no-show models).

### 5.3 Sample size

All eligible appointments in the window will be used. Allergy clinics typically generate thousands of appointments per year; with no-show base rates commonly in the 10–30% range, even a modest two-year extract should be well powered to detect interaction effects of operationally meaningful size. A formal power check will be run once the appointment volume is confirmed.

---

## 6. Ethical Considerations and Data Protection

This is a retrospective analysis of administrative scheduling records combined with public environmental data. No clinical information, no patient contact, and no identifiers are required. The dataset will be de-identified at extraction (no names, MRNs, birth dates, or addresses); if linkage of repeat visits is desired, a one-way anonymized patient code will be generated by the data team before the dataset reaches the analyst. Because dissemination beyond the institution (e.g., conference presentation, public methodology repository) is anticipated, the project will be submitted for IRB review — anticipated as exempt or expedited — with a request for waiver of informed consent, rather than proceeding as internal quality improvement. Data will be stored only on institution-approved systems; no patient-level data will ever be placed in public or personal repositories. Any publicly shared materials will be limited to analysis code, methodology, and aggregate results approved for release.

---

## 7. Anticipated Operational Deliverables

1. Seasonal no-show risk profile for the allergy clinic (which slots, days, and months bleed the most capacity).
2. A "hot-booking" flag definition: appointments booked during high-pollen periods with lead times beyond a data-derived threshold, suitable for targeted reminders or waitlist backfill.
3. Evidence-based recommendation on maximum booking lead times during peak season (e.g., reserving short-lead slots for pollen-peak bookings).
4. Optionally, a per-slot no-show risk score to support overbooking decisions.

---

## 8. Limitations

Pollen counts proxy population-level symptom burden, not any individual's symptoms; some patients (e.g., food allergy, drug allergy, year-round dust-mite allergy) are insensitive to pollen, which biases against finding the hypothesized effect (making any positive finding more credible, and motivating a visit-type sensitivity analysis). Booking-date data quality must be verified. Observational design limits causal claims; the projection-bias interpretation is inference to the best explanation, strengthened by the falsification tests. Results from a single clinic may not generalize, though the mechanism, if confirmed, is plausibly universal.

---

## 9. References

- Busse, M. R., Pope, D. G., Pope, J. C., & Silva-Risso, J. (2015). The psychological effect of weather on car purchases. *The Quarterly Journal of Economics, 130*(1), 371–414.
- Conlin, M., O'Donoghue, T., & Vogelsang, T. J. (2007). Projection bias in catalog orders. *American Economic Review, 97*(4), 1217–1249.
- Loewenstein, G. (2005). Hot-cold empathy gaps and medical decision making. *Health Psychology, 24*(4, Suppl.), S49–S56.
- Loewenstein, G., O'Donoghue, T., & Rabin, M. (2003). Projection bias in predicting future utility. *The Quarterly Journal of Economics, 118*(4), 1209–1248.
- McMullen, M. J., & Netland, P. A. (2015). Lead time for appointment and the no-show rate in an ophthalmology clinic. *Clinical Ophthalmology, 9*, 513–516.
- Mohammadi, I., Wu, H., Turkcan, A., Toscos, T., & Doebbeling, B. N. (2018). Data analytics and modeling for appointment no-show in community health centers. *Journal of Primary Care & Community Health.* [Verify exact citation — representative of the lead-time OR finding; replace with the specific Tehran ambulatory clinic study if used.]
- Saha, S., Vaidyanathan, A., Lo, F., Brown, C., & Hess, J. J. (2021). Short term physician visits and medication prescriptions for allergic disease associated with seasonal tree, grass, and weed pollen exposure across the United States. *Environmental Health, 20*, Article 85.

*(Citations marked for verification should be confirmed against the original papers before submission.)*
