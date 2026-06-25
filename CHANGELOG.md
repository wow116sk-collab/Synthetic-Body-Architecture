# Changelog

All notable changes to the Synthetic Body Architecture document.
Format: versions from V1.0 onward; the pre-1.0 development revisions (Rev 1–10) are preserved as history.

## [1.2.2] — 2026-06-24
Cosmetic only — no content change.
- Removed a stale "(new, Rev 9)" marker from the §16.9 header.
- Note: `v1.2.1` was a release-only re-tag (identical content to V1.2) created to register the Zenodo DOI.

## [1.2] — 2026-06-24
- §16.1: added an explicit scope boundary — the project aims to *extend* healthy lifespan and capability enough for space exploration and to reduce physical limitations, **not** to achieve individual immortality (which would require defeating senescence, §16.6, and cannot come from substrate-copy/uploading — a closed route, §9 #16).

## [1.1] — 2026-06-24
Folds in mid-2026 fact updates. Core conclusion unchanged (long-term perfusion remains the binding constraint).
- §7.2: added hydrogel electrodes (Li et al., *Advanced Materials* 2026) and non-penetrating subdural thin-film arrays (Precision Neuroscience "Layer 7", FDA-cleared temporary) as real 2026 de-risking routes for the electrode foreign-body problem, with the honest caveat that these reduce but do not eliminate it.
- §7.3: added functional-ultrasound BCI (fUS) as a new non-penetrating reading modality, and Paradromics "Connect-One" / CorTec Brain Interchange as speech-restoration / closed-loop BCI milestones.
- §16.8 and the provenance appendix updated accordingly.
- Author and date now shown on the document.

## [1.0] — 2026-06-24
First consolidated, versioned public release. Consolidates development revisions Rev 1–10.
The filename now carries the version (`synthetic_body_design_V1.0`).

---

## Development history (pre-1.0)

### Rev 10
- Fact-fix (R6): corrected the BrainEx perfusion ceiling from "~36 h" to the primary-source figure (Vrselja & Sestan, *Nature* 2019: restoration up to 4 h post-mortem, ~6 h perfusion) at every occurrence; 37 °C set-point unchanged.
- Added the "Adopted paths — what was chosen and why" table to §9, alongside the existing rejected-options table.

### Rev 9
- Added §16.9 Expanded Sensorium (optional upgrade): broad-spectrum sensors via sensory substitution (Bach-y-Rita; Eagleman), with a physics firewall (known-spectrum signals only; no hidden new wave channel).

### Rev 8
- Radiation correction (§16.3): secondary-particle showers mean thick shielding can raise dose (hydrogen-rich material needed); compute must be rad-hardened independently; residual HZE risk does not vanish.
- Lifespan-ceiling correction (§16.6, §10.2): perfusion fixes acute ischemic death, not chronic neuron senescence — two biological bottlenecks, not one.
- Minor engineering caveats (compressor COP, bandwidth order-of-magnitude, R744 transcritical pressure).

### Rev 7
- Defined project scope (§16): a human brain in an actively used synthetic body for space exploration / lifespan extension.
- Added closed-loop adaptive perfusion, inline immune filtration, the Phase 1→3 roadmap, space advantages, localized radiation shielding, and the limits of nano tissue replacement.

### Rev 1–6
- Built the three-architecture comparison (A/B/C); shared subsystems (perfusion, biometal frame, neural interface, active cooling, maintenance, power).
- Added the transfer protocol (§11), modular neural port (§12), dual thermal mode (§13), double containment + buffer (§14), maintenance architecture (§15).
- Established the epistemic tag system, the design decision log, and the concept provenance appendix.
