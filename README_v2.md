# SCS Carport Configurator — Phase 3 Prototype

**Student:** Sara Perovic | Matriculation number: 1058826
**Course:** E-Commerce · TH Rosenheim · SPO 2022
**Client:** Scheiffele-Schmiederer KG (SCS) · scs-holzshop.de
**Live URL:** https://sunsflake.github.io/SCSPhase03-Sara/index.html
**Password:** scs2026
**Submission date:** June 2026
**Live until:** 31 July 2026 minimum (GitHub Pages, free tier, no expiry)

---

## What this prototype is

This is a fully connected hi-fi prototype of the SCS carport configurator flow built as a single HTML file. It covers the complete buyer journey: a landing page showing both carport types with a realistic price range, a step-by-step configurator showing the price impact of every option, and a configuration summary before checkout. The prototype is password protected and hosted permanently on GitHub Pages.

It is built as a direct response to findings from Phase 1 (competitor analysis and PDP evaluation) and Phase 2 (hypothesis testing with Tobii eye tracking). Every design decision connects to a specific finding from those phases.

---

## Project history and phase decisions

### Phase 1: Competitor analysis

The analysis produced Balanced Scorecards, Customer Journey Maps, PDP Scorecards, Organic Search Scorecards, and Communication Channel Scorecards for each competitor.
The most significant finding from the carport segment was that EasyCarport.de scored 10/10 on pricing clarity in the PDP Scorecard. EasyCarport shows a live price update with every option selected in its configurator, making the cost of each choice immediately visible. The SCS configurator updated the total price but did not show what each individual selection contributed. This was identified as the primary conversion risk for SCS: buyers working within a personal budget had no way to understand what was driving the price without mentally subtracting previous totals.

A second finding was that the SCS PDP showed only a single starting price (€4,833.84 for the Einzelcarport) with no indication of the realistic price range. Since the starting price is the minimum base configuration and most buyers configure significantly above it, this set a misleading price anchor before the buyer even entered the configurator.

### Phase 2: Hypothesis testing and prototypes

Phase 2 produced two hypotheses tested in a UX lab using Tobii eye tracking software with a think-aloud protocol.

**Hypothesis 1 (configurator, teammate):** Showing the individual cost of each selectable option alongside the running total reduces buyer uncertainty and increases configuration completion rate.

**Hypothesis 2 (PDP):** Showing a realistic price range on the SCS carport PDP rather than a single starting price reduces sticker shock at the configuration summary step and produces more committed buyers.

The user test used A/B testing: one group saw the current SCS page with only the starting price, the other saw a static image showing a price range. Participants stated their budget expectation before configuring and then compared it to the summary total. Eye tracking data (TTFF, Dwell Time, Fixation Count) was used alongside think-aloud verbalisations to measure surprise and hesitation at the summary step.

Results showed that participants focused on the starting price and expressed hesitation when they reached the configured total. Elevated fixation counts on the summary price indicated re-reading consistent with unexpected numbers. The debriefing confirmed that participants expected the final price to stay very close to the PDP starting price or even be the same as shown.

Phase 2 produced two separate HTML prototypes:
- Prototype 1 (configurator): https://sunsflake.github.io/SCS-Carport-Configurator---Hypothesis-1---Per-option-price-delta/prototype1_configurator.html
- Prototype 2 (PDP): https://sunsflake.github.io/SCS-PDP---Hypothesis-2---Range/prototype2_landing.html

### Phase 3: This final prototype

Phase 3 integrates both hypotheses into a single connected prototype covering the full buyer journey: PDP landing page → configurator → configuration summary. The Phase 2 prototypes were separate files; this prototype connects them into one seamless flow. It is built as a maintainable, portable single HTML file with no build tools or external dependencies beyond Google Fonts.

---

## Design decisions and rationale

### Price range on PDP (from Hypothesis 2)
The landing page shows a price range (for example €4,833 to €7,900 for the Single Carport) instead of a single starting price. This directly addresses the anchoring problem confirmed in the Phase 2 user test: participants who saw only the starting price anchored their budget to it and expressed surprise at the summary total.

### Per-option price delta in configurator (from Hypothesis 1)
Every selectable option in the configurator shows its price impact immediately below the option name. The running total updates with every selection and the sidebar shows a full breakdown of which choices added cost. This addresses the Phase 1 finding that SCS's configurator gave buyers no visibility into what each choice cost.

### Connected flow
Phase 2 prototypes were not connected. This prototype connects all three steps: clicking "Configure this carport" on either product card launches the configurator pre-set for that carport type, and completing all steps flows into the summary page.

### Real product images
Product images are the actual SCS photography from scs-holzshop.de, embedded as base64 in the HTML file so the prototype works without external image files.

### Trust signals on product cards
The real SCS landing page places trust information only in the global site header, visually disconnected from the product cards. This prototype moves key trust signals directly onto each card at the point where the buying decision is made.

### Breakdown table
A simplified two-column table on the landing page explains what drives the price range, listing each configurable option and its maximum additional cost. This was added because Phase 2 test debriefing showed that participants did not understand which choices drove the price up.

### Password protection
The prototype uses a JavaScript password prompt (password: scs2026). A production implementation would use server-side authentication.

---

## Version history

| Version | Date | Changes |
|---|---|---|
| v0.1 | May 2026 | Initial Phase 2 PDP prototype. Static HTML, price range display only, no configurator connection (Hypothesis 2). |
| v0.2 | May 2026 | Phase 2 configurator prototype. Separate file, per-option price delta, no connection to PDP (Hypothesis 1). |
| v0.3 | May 2026 | Real SCS product photography embedded as base64 in both Phase 2 prototypes. |
| v0.4 | May 2026 | All copy translated to English for academic submission context. |
| v1.0 | June 2026 | Phase 3 prototype. Single connected HTML file covering full buyer journey: PDP to configurator to summary. Password protection added. Price range displayed without bar or typical price label. Trust signals on cards. Full breakdown table. SCS yellow (#F5A800) used as primary accent colour throughout. |
| v1.1 | June 2026 | German product names removed. Cards renamed from "SCS Einzelcarport / SCS Doppelcarport" to "Single Carport / Double Carport" for full English consistency. Redundant category tag above each card title removed. Base price sentence removed from under the price range as it added unnecessary information at the decision point. Font changed from Inter to Syne (headings) and DM Sans (body) for a cleaner, more distinctive typographic identity. Breakdown table simplified from three columns to two, removing the "Base value" column to reduce visual noise. |

---

## Decision notes on v1.1 changes

**Removing German product names**
The Phase 3 prototype is presented in an academic context and the full configurator flow is in English. Keeping German product names (Einzelcarport, Doppelcarport) created an inconsistency. Since the prototype is not being used for a live Tobii session in this phase, the realism argument for German names no longer applies. The cards now read "Single Carport" and "Double Carport" throughout, including in the configurator header and summary page.

**Removing the category tag above the title**
Each card previously had a small pill label ("SINGLE CARPORT") directly above the product title ("SCS Einzelcarport"). With the title renamed to "Single Carport", the tag became a direct repetition of the same information. It was removed to reduce visual clutter and let the title carry the information on its own.

**Removing the base price sentence**
The sentence "Base price €4,833. Final price depends on roof type, covering, size, and side cladding selected" appeared below the price range on each card. The Phase 2 hypothesis and test were specifically designed to test whether showing a range (without a single anchor figure) reduces sticker shock. Including a base price sentence underneath the range partially reintroduced the anchor that the range was designed to replace. Removing it keeps the price communication consistent with the hypothesis intent.

**Font change**
Inter was replaced with Syne for headings and DM Sans for body text. Inter is a highly generic sans-serif widely used across web products. The font change makes the prototype feel more intentional and distinctive without departing from the clean, readable style appropriate for an e-commerce context.

**Simplified breakdown table**
The original table had three columns: option, base value, and maximum additional cost. The base value column (showing things like "Lean-to roof (Pultdach)" and "3.0 x 5.0 m standard") added length without helping the buyer understand the price. The simplified two-column version shows only what the buyer needs: what the option is and how much it can add to their total.

---

## Screenshot reference

The screenshot below shows the v1.0 state of the landing page before v1.1 changes. Visible in this version: the German product names (SCS Einzelcarport, SCS Doppelcarport), the category tags above each title (SINGLE CARPORT, DOUBLE CARPORT), and the base price sentence below the price range numbers. All three of these elements were removed in v1.1 for the reasons documented above.

> Screenshot: landing page v1.0 showing SCS Einzelcarport and SCS Doppelcarport cards with category tags, German names, and base price sentence visible. [Insert screenshot here — use the landing page screenshot from the v1.0 review session.]

---

## How to run locally

1. Download `index.html` from this repository
2. Open it in any modern browser
3. Enter password: `scs2026`


---

## File structure

```
/
├── index.html      — complete prototype (landing page, configurator, summary, all images embedded)
└── README.md       — this file
```

---

## Documented deviations from original concept

- The price bar and typical purchase label from the Phase 2 PDP prototype were removed in v1.0. The bar added visual complexity without actionable information and the typical label created a second anchor that partially contradicted the purpose of showing a range.
- German product names were removed in v1.1 for English consistency in the academic presentation context.
- Google Analytics 4 integration was scoped as optional and not implemented. Event tracking could be added in a future version with GA4 script insertion and gtag event calls on step completion and checkout initiation.
- The Doppelcarport uses the same configurator steps and pricing logic as the Single Carport with a higher base price. A fully accurate implementation would use different size ranges and cladding costs for the wider structure. This is a known simplification documented here.

---

*Sara Perovic · 1058826 · TH Rosenheim · E-Commerce · June 2026*
