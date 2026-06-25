# Synthetic Body Architecture

### A Comparative Design Brief — Grounded in 2026 Technology and Active Laboratory Research

**Pitarn Rungsiyapornratana** · 24 June 2026

**Version 1.2.2.** Cosmetic cleanup: removed a stale "(new, Rev 9)" marker from the §16.9 header. No content change. (The intervening tag `v1.2.1` was a release-only re-tag to register the Zenodo DOI, with identical content to V1.2.) The filename carries the version (`synthetic_body_design_V1.2.2`).

---

#### Development history

**V1.2.2** — Cosmetic: removed the stale "(new, Rev 9)" marker from the §16.9 header (the document is past Rev 9). No content change. `v1.2.1` was a release-only re-tag with identical content to V1.2, created to register the Zenodo DOI.

**V1.2** — Adds an explicit scope boundary to §16.1: the project aims to *extend* healthy lifespan and capability enough for space exploration and to reduce physical limitations — **not** to achieve individual immortality (which would require defeating senescence, §16.6, and cannot come from substrate-copy/uploading — a closed route, §9 #16). Closes the recurring "escape the lifespan ceiling by uploading" loop in writing.

**V1.1** — Folds in mid-2026 fact updates: hydrogel electrodes and non-penetrating subdural thin-film arrays (Precision Layer 7) as real 2026 de-risking routes for the electrode foreign-body problem (§7.2); functional-ultrasound BCI (fUS) as a new non-penetrating reading modality and Paradromics speech-restoration BCI (§7.3); Precision Layer 7 as a surface-interface option (§10.4/§12). Updates §16.8 and the provenance appendix. Core conclusion unchanged (perfusion remains the binding constraint).

**V1.0** — First versioned release; consolidates development revisions Rev 1–10 below.

**Revision 10** — Fact-fix (R6): corrects the BrainEx perfusion ceiling from "~36 h" to the primary-source figure (Vrselja & Sestan, *Nature* 2019: restoration up to 4 h post-mortem, ~6 h perfusion) at every occurrence; the 37 °C set-point is unchanged. Adds an "Adopted paths — what was chosen and why" table to §9, the companion to the existing rejected-options table, recording *why each chosen path was chosen* alongside *why each alternative was cut*.

**Revision 9** — Adds §16.9 (Expanded Sensorium), an *optional upgrade* (not a correction): broad-spectrum sensors routed into the nervous system via sensory substitution (Bach-y-Rita; Eagleman), letting a synthetic body sense bands biology cannot (cosmic-ray flux, magnetic fields, infrared, radio, UV). Includes the standing physics firewall — receivers only for signals that already exist in known physics; no "hidden new wave channel" (consistent with §9 #1–#2). Rev 8 and earlier unchanged.

**Revision 8** — Consistency-check corrections to two over-optimistic claims. (1) **Radiation (§16.3):** "protect the brain alone, thicker shield is better" was wrong — galactic-cosmic-ray shielding produces secondary-particle showers (thick aluminium can *raise* dose; hydrogen-rich material is needed), and the compute layer (BCI/neuromorphic) is independently radiation-sensitive and must be rad-hardened, not merely shielded; residual HZE damage to cognition does not fully vanish. (2) **Lifespan ceiling (§16.6, §10.2):** perfusion fixes *acute* ischemic death, not *chronic* neuron senescence; since identity-bearing neurons cannot be replaced (§9, #16), lifespan has a hard ceiling perfusion cannot lift. The project therefore has **two** biological bottlenecks, not one: acute perfusion **and** chronic neuron aging. Logs both as §9 #17–#18. Minor engineering caveats added (compressor COP, bandwidth order-of-magnitude, R744 transcritical pressure).

**Revision 7** — Defines the true project scope (§16): a human brain in a synthetic body for **space exploration / lifespan extension**, not a dormant lab specimen. Adds closed-loop adaptive perfusion and inline immune filtration (user-proposed), the Phase 1→3 roadmap (real brainstem → artificial), space advantages and localized radiation shielding, and the limits of nano tissue replacement (support tissue yes; identity-storing neurons no). Logs neuron-replacement as blocked by the connectome/identity wall (§9, #16).

---

## Epistemic Tag Legend

Every non-trivial claim in this document carries one of the following tags, following the author's standing attribution convention:

| Tag | Meaning |
|---|---|
| `[ESTABLISHED]` | Tested, peer-reviewed, in clinical or engineering use today |
| `[THEORETICAL]` | A hypothesis with a plausible basis but not yet experimentally confirmed |
| `[CONTESTED]` | Actively debated; no scientific consensus |
| `[MINORITY VIEW]` | Held by a small fraction of the relevant research community |
| `[HYBRID SYNTHESIS]` | Combines or adapts existing ideas from named sources |
| `[SPECULATIVE]` | Beyond the reach of current science; requires a paradigm not yet in hand |
| `[USER'S OWN]` | A design decision or framing originated by the author (Pitarn) in this work |

**Attribution rule applied here:** established science is credited to its originators by name where known; design choices made by the author during this project are tagged `[USER'S OWN]`; ideas that adapt prior work are `[HYBRID SYNTHESIS]`. Where an attribution is uncertain, that is stated explicitly rather than guessed.

---

## 1. Executive Summary

This document compares three synthetic-body architectures whose shared goal is to extend the functional lifespan of a human brain by replacing the life-support and body systems with engineered equivalents. All three are anchored to technology that exists in 2026, supplemented by research currently active in laboratories.

The principal axis of difference is **how much biological tissue is retained**, which in turn drives communication bandwidth, risk profile, and technology readiness.

The overall premise — *retain only the brain (or brain plus parts of the CNS) and build everything else, with bidirectional sensory feedback* — is an old philosophical scenario ("brain in a vat," Hilary Putnam 1981; earlier Gilbert Harman 1973) `[THEORETICAL]` and an old experimental one (isolated head/brain perfusion: Sergei Brukhonenko, 1920s; Robert J. White's primate work, 1960s–70s) `[ESTABLISHED]` as historical experiments. The specific engineering integration framed in this brief — pairing modern bidirectional BCI with full body replacement — is the author's project framing `[USER'S OWN]`, assembled from established components.

### Architectures compared

- **Architecture A — Conservative:** retain brain + brainstem + full spinal cord.
- **Architecture B — Balanced:** retain brain + brainstem; remove spinal cord.
- **Architecture C — Aggressive:** retain the brain only, in a perfusion vessel.

### Headline conclusion

Architecture A is the nearest-term and lowest-risk (≈10–20 years) because it preserves natural signal pathways. Architecture B is the mid-term balance point (≈20–40 years). Architecture C, as described, carries the largest technology gap (≈50+ years, and may not be achievable with the current paradigm).

**Project scope (defined in §16):** the goal is **not** a brain kept dormant in a jar. It is a human brain in an *actively used* synthetic body for **lifespan extension and space exploration**. This scope dissolves several apparent blind spots — an actively used body continuously feeds the brain sensory input, and a retained brainstem (Phase 1) drives sleep and autonomic function — and it changes the operating environment from "lab" to "spacecraft," where the vehicle provides shielding and support.

> **Design note (Rev 2→3):** Three principles introduced during design review shape the whole document. (1) No requirement for a *sealed-for-life* system, since nutrient/perfusate replenishment is periodic anyway — fold all servicing into one maintenance cycle `[USER'S OWN]`. (2) Separate the requirement "the brain must be still" from "the whole body must be still" — isolate only the brain vessel `[USER'S OWN]`. (3) Use active refrigeration as primary cooling rather than mimicking human sweat `[USER'S OWN]` (the refrigeration technology itself is `[ESTABLISHED]`).

---

## 2. Shared Subsystems (required by all architectures)

### 2.1 Brain Perfusion System

**Baseline:** *BrainEx* — Vrselja, Sestan et al., 2019, *Nature*; Sestan Lab, Yale `[ESTABLISHED]`. A pulsatile-perfusion system with a hemoglobin-based, acellular, non-coagulating, cytoprotective perfusate restored microcirculation and molecular-level activity in pig brains up to four hours post-mortem, with perfusion applied for ~6 hours. That single-digit-hour window (≈6 h perfusion, after up to 4 h post-mortem) is the current demonstrated ceiling; longer durations are unverified.

Required components:

- Pulsatile pump emulating a heartbeat (60–80 BPM) — derived from cardiopulmonary bypass / ECMO engineering `[ESTABLISHED]`.
- Heat exchanger holding 36.5–37.0 °C — fed by the cooling system in §2.4.
- Membrane oxygenator — ECMO-derived `[ESTABLISHED]`.
- Hemoglobin-based oxygen carrier (HBOC) to replace whole blood `[ESTABLISHED]` (as a research/clinical class; long-term CNS use is `[THEORETICAL]`).
- Dialysis loop performing the clearance roles of liver and kidney `[ESTABLISHED]` as dialysis; whole-organ substitution is `[THEORETICAL]`.
- Hormone replacement system — see §2.6 (a feedback loop, not a static reservoir).
- Real-time monitoring: pH, O₂, glucose, lactate, electrolytes `[ESTABLISHED]`.

#### 2.1.1 Vibration Isolation — applied to the brain vessel only

Principle `[USER'S OWN]`: the metal frame may vibrate freely (no nerves to injure); only the brain vessel needs isolation. This decouples a hard requirement from a non-requirement and substantially simplifies the body design.

The human brain already floats in cerebrospinal fluid, which acts as a natural vibration damper `[ESTABLISHED]` — this is why running, jumping, and light impacts are tolerated. The system reproduces that principle and adds an engineered layer:

| Method | Principle | Status |
|---|---|---|
| Fluid suspension | Brain floats in perfusate (CSF analog) — the natural first layer | `[ESTABLISHED]` (biology) |
| Magnetorheological mount | Vessel floats on magneto-active fluid; damping adapts to vibration frequency in real time | `[ESTABLISHED]` (engineering) |
| Active cancellation | Sensors detect vibration; actuators cancel it (same principle as noise-cancelling audio) | `[ESTABLISHED]` |
| Gimbal suspension | Vessel suspended in a 3-axis gimbal (same principle as a camera gimbal) | `[ESTABLISHED]` |

**Current limitation:** continuous perfusion has not exceeded single-digit hours in research (≈6 h in BrainEx); a real system must reach years. This remains the dominant open problem (see §7.1).

### 2.2 Body Framework

Candidate structural materials:

| Material | Strengths | Weaknesses | Use | Tag |
|---|---|---|---|---|
| Ti-6Al-4V | Gold standard; high strength-to-weight; corrosion-resistant | Al, V possible long-term toxicity; heavy | Primary skeleton, joints | `[ESTABLISHED]` |
| Ti-Nb-Zr alloy | No toxic metals; modulus closer to bone | Costly; hard to manufacture | Tissue-contact points | `[ESTABLISHED]` (research-grade) |
| Porous tantalum | Excellent osseointegration | Very expensive | Tissue anchoring | `[ESTABLISHED]` |
| Carbon-fiber composite | Light; strong; non-magnetic | Does not osseointegrate | Outer shell | `[ESTABLISHED]` |
| Mg / Zn biodegradable | Resorbable; tissue-friendly | Dissolves too quickly | Temporary fixation | `[ESTABLISHED]` as a class; durable load-bearing use is `[THEORETICAL]` |

Osseointegration as a principle is credited to **Per-Ingvar Brånemark** (1950s–60s) `[ESTABLISHED]`.

### 2.3 Neural Interface Stack

Common layers (details vary by architecture):

- Recording electrodes — *Utah array* (**Richard Normann**, 1990s) `[ESTABLISHED]`; ECoG `[ESTABLISHED]`; flexible mesh (mesh-electrode concept: **Charles Lieber lab, Harvard**; commercialized direction: Neuralink) `[ESTABLISHED]`.
- Stimulation electrodes for sensory feedback — intracortical microstimulation `[ESTABLISHED]`.
- Edge AI decoder — neuromorphic chips, e.g. Intel *Loihi*, IBM *TrueNorth* `[ESTABLISHED]`.
- Wireless link — UWB or optical, for low latency `[ESTABLISHED]`.
- Reflex bypass network — see §4.3 `[HYBRID SYNTHESIS]`.

### 2.4 Cooling System

Total thermal load: brain ≈20 W + BCI chips + actuators (hundreds of watts) — comparable to a workstation/server.

> **Changed in Rev 2:** primary cooling is now **active refrigeration (vapor compression)** rather than passive radiation. Rationale `[USER'S OWN]`: (1) precise temperature control to ±0.5 °C; (2) functions in hot ambient conditions (e.g. Bangkok at 35 °C, where passive radiation fails); (3) spot-cools only the brain vessel, saving power. This is the same approach every data center and supercomputer uses `[ESTABLISHED]`.

In-body AC specification:

| Part | Spec | Tag |
|---|---|---|
| Compressor | Micro-rotary ~5 cm³ (laptop/electronics-cooling derived) | `[ESTABLISHED]` |
| Evaporator | Surrounds the brain vessel; absorbs heat at source | `[ESTABLISHED]` |
| Condenser | ~A5-sized finned panel on back/chest | `[ESTABLISHED]` |
| Refrigerant | R744 (CO₂) — safe on leak, non-flammable, lower toxicity than R134a | `[ESTABLISHED]` |
| Power draw | ~30–50 W to reject 100 W; COP 2–3 | `[ESTABLISHED]` |
| Backup | Passive radiator + vent; engages if the compressor fails | `[ESTABLISHED]` |

Thermoelectric (Peltier) cooling has COP ≈0.5–1, far worse than vapor compression, and is unsuitable as primary `[ESTABLISHED]`; it may serve small localized spot-cooling. An optional evaporative analog (microfluidic "sweating" skin) exists in robotics research `[ESTABLISHED]` (as a research demonstration) and can supplement heavy-load cooling.

Cautions: compressor noise requires damping; the refrigerant subsystem adds ~2–3 kg; refrigerant must be topped up periodically (folded into §2.5).

> **Engineering caveats (Rev 8):** the COP 2–3 figure is optimistic for a ~5 cm³ micro-compressor — small-scale vapour-compression typically underperforms full-size units, so plan for a lower real COP and a larger condenser. Also, R744 runs **transcritical** (high-side pressure ~100+ bar): although CO₂ is non-toxic on leak, that is a **mechanical/pressure hazard** beside the brain and demands robust pressure containment. A lower-pressure refrigerant or a secondary coolant loop (pumped chilled fluid to the head, compressor in the torso) may be preferable.

**Set-point — lock at 37 °C, do not minimize.** The target is to *hold* 37 °C ±0.5 °C, **not** to run as cold as possible. Brain enzymes operate fully only near 37 °C (Arrhenius: −10 °C ≈ half the reaction rate), so a colder brain thinks slower and eventually malfunctions. The cooling system's job is to prevent *overheating* under heavy cognitive load, not to chill the brain. Sub-37 °C is reserved for the transport/emergency mode only (§13).

### 2.5 Maintenance Cycle

Principle `[USER'S OWN]`: because the system must be opened periodically to replenish nutrients/perfusate anyway, there is no reason to engineer it as sealed-for-life (which is dramatically harder for no benefit). All servicing is consolidated into one cycle — like a car service interval.

Tasks per cycle:

- Replenish nutrients; replace perfusate.
- Top up / check AC refrigerant.
- Replace dialysis-loop filters.
- Refill hormone reservoirs.
- Check electrode integrity; recalibrate the decoder.
- Check battery / power system.

Result: the design problem shrinks from "operate unattended for life" to "operate stably between service intervals." The interval is set by the shortest-lived consumable (likely perfusate stability).

### 2.6 Power

**Chosen (now):** Li-ion + supercapacitor hybrid as primary; betavoltaic cell as backup `[ESTABLISHED]`.

*Why this and not solid-state today:* Li-ion is the only chemistry with the technology readiness, field history, and mass-manufacturability for deployment in 2026. The supercapacitor absorbs peak actuator loads; the betavoltaic (Ni-63 / tritium) supplies 20+ year trickle power for clock/memory retention — not main drive. Hot-swappable during the maintenance cycle (§2.5).

**Deferred (near-term upgrade): solid-state battery** `[THEORETICAL]` for deployment timing.

Solid-state is superior on the dimensions that matter here — no liquid electrolyte, no thermal-runaway fire mode, wider temperature tolerance, and higher potential cycle life. Critically, solid-state's single biggest weakness — cold-start / low-temperature conductivity collapse — is **irrelevant in this application**, because the body already maintains a controlled temperature (§2.4). This makes a synthetic body an unusually *good* fit for solid-state, better than a typical EV.

*Switch trigger:* adopt solid-state as primary once **field-validated** cycle life is confirmed. As of mid-2026 the credible field-validated figure is ~6,000–8,000 cycles (Pure Lithium-class, with >12 months of infrastructure deployment) `[ESTABLISHED]` as field data — **not** the ~100,000-cycle figure claimed by Donut Labs, which remains unverified by any third party and was tested on an already-damaged cell (see §9, rejected) `[THEORETICAL]`.

*Constraint:* avoid **sulfide-based** solid electrolytes for a body-worn unit — they release toxic H₂S on contact with air/moisture (see §9). Prefer oxide- or polymer-based solid electrolytes.

---

## 3. Architecture A — Conservative

**Philosophy:** retain as much of the natural nervous system as possible; replace only what is not essential to identity.

### 3.1 Biological scope
- Brain (cerebrum + cerebellum)
- Brainstem — autonomic control
- Entire spinal cord
- Peripheral nerve roots, severed distally at the body-interface point

### 3.2 Body–brain interface
Peripheral nerve interfaces at the nerve-root ends:
- TIME / LIFE intrafascicular electrodes in median, ulnar, radial, sciatic, etc. `[ESTABLISHED]`
- Osseointegrated neural interfaces (ONI) — a Ti post through severed bone, linking the prosthesis `[ESTABLISHED]`
- Regenerative peripheral nerve interfaces (RPNI) — small muscle grafts at nerve ends acting as signal amplifiers (**Cederna & Kung, University of Michigan**) `[ESTABLISHED]`

### 3.3 Advantages
- Natural signal pathways — highest bandwidth.
- Spinal reflex arcs operate on their own — no need to rebuild them `[ESTABLISHED]` (reflex arc is basic neurophysiology).
- Full autonomic system via the brainstem — temperature, blood pressure, respiration self-regulate.
- Identity preserved — embodiment closest to the original.
- Highest TRL — all major components are already clinical.

### 3.4 Disadvantages / challenges
- Perfusion must cover the entire spinal cord — larger, more complex.
- The spinal cord is fragile; requires a protective artificial vertebral column.
- Largest life-support module of the three.
- If the spinal cord fails, most bandwidth is lost.

### 3.5 Technology Readiness

| Component | TRL | Status |
|---|---|---|
| Peripheral nerve interface | 7 | In clinical use (LifeHand, NEBIAS) |
| Osseointegrated prosthesis | 8 | FDA-approved (OPRA) |
| Spinal cord perfusion (long-term) | 3 | Animal-stage |
| Whole-CNS life support | 2 | Theory only |
| Bionic limb (full sensory) | 6 | Prototype + clinical trial |

---

## 4. Architecture B — Balanced

**Philosophy:** retain only what is essential to identity and autonomic function; remove the spinal cord and substitute BCI plus a reflex bypass.

### 4.1 Biological scope
- Brain (cerebrum + cerebellum)
- Brainstem — critical; controls respiration, heart rate, blood pressure
- No spinal cord

### 4.2 Body–brain interface
- Motor-cortex array — Utah array or flexible mesh (1,024–10,000 channels) `[ESTABLISHED]`
- Sensory-cortex array — intracortical microstimulation `[ESTABLISHED]`
- Brainstem interface — communicates with autonomic centers `[THEORETICAL]`
- Spinal-cord emulator — an ASIC reproducing central pattern generators for gait and respiration `[HYBRID SYNTHESIS]`
- Reflex bypass network — neuromorphic chips distributed in the body, responding in <20 ms `[HYBRID SYNTHESIS]`

### 4.3 Reflex Bypass Architecture (key design element)

This emulates the spinal cord's reflex architecture in edge-AI silicon. The underlying biology is established: the reflex arc, and **central pattern generators (CPGs)** — first inferred by **T. Graham Brown (1911)** and developed extensively by **Sten Grillner** `[ESTABLISHED]`. The fastest biological precedent is the **Mauthner cell** escape circuit in fish (~5–10 ms) `[ESTABLISHED]`. A working artificial CNS bypass for paralysis has been demonstrated (**Bouton et al., 2016, Battelle / Ohio State**, *Nature*) `[ESTABLISHED]`, as has an artificial-synapse circuit that simultaneously drives a reflex contraction and relays sensation to the brain (Kim et al., 2018, *Science*) `[ESTABLISHED]`.

The author's specific contribution `[USER'S OWN]` is the *framing*: a stored "reflex memory" that is **not** invoked during ordinary operation and is called only under emergency/critical conditions, while routine signals propagate normally through the system. Architecturally this maps cleanly onto a CPG-plus-edge-AI implementation — making the combined proposal a `[HYBRID SYNTHESIS]` of established mechanisms with the author's emergency-gating concept.

> **Provenance note:** the author originally reached this idea via a microtubule-as-reflex-store hypothesis. The microtubule mechanism itself is **not** required and is not used here (see §7.3); the surviving, valuable part is the emergency-gated reflex-store *behavior*, which is implementable with conventional neuromorphic hardware.

Layered implementation:
- **L1 — Sensor preprocessing:** filter, threshold, encode to spikes.
- **L2 — Reflex pattern matching:** a pre-trained spiking neural network.
- **L3 — Decision:** issue the reflex action immediately; send a copy upstream to the brain.
- **L4 — Adaptation:** adjust weights from brain feedback.

Pre-programmed reflexes: withdrawal (hot object), balance correction, blink, swallow, gait pattern, postural reflex.

### 4.4 Advantages
- Life support covers only brain + brainstem — smaller than A.
- Brainstem retained, so autonomic function works without simulation.
- Lower raw bandwidth than A, but an intent decoder compensates.
- The reflex bypass can respond faster than biology in some cases.

### 4.5 Disadvantages / challenges
- Cortical electrodes degrade within 5–10 years (scar tissue) — see §7.2.
- Limited bandwidth: today's systems resolve 10–100 degrees of freedom, not thousands.
- Sensory feedback is coarse — ICMS feels point-like, not like real touch.
- Some reflexes (fine proprioception) are hard to learn.

### 4.6 Technology Readiness

| Component | TRL | Status |
|---|---|---|
| Motor-cortex BCI | 7 | BrainGate, Neuralink — in humans |
| Bidirectional BCI | 6 | Pittsburgh group; clinical trials |
| Neuromorphic reflex chip | 5 | Loihi, TrueNorth — lab demos |
| Brainstem interface | 3 | DBS-adjacent research |
| Long-term cortical electrode (decades) | 3 | Biofouling unsolved |
| Spinal CPG emulator | 4 | Lab prototype for paralysis |

---

## 5. Architecture C — Aggressive

**Philosophy:** retain the brain only, in a perfusion vessel; sever everything below it; communicate with the body entirely through BCI.

### 5.1 Biological scope
- Cerebrum + cerebellum only
- No brainstem (severed at the midbrain) — autonomic function must be fully simulated
- Brain housed in a sealed nutrient chamber (opened during maintenance)

### 5.2 Brain vessel specification
- Vessel: titanium + sapphire window — impact-resistant; allows imaging `[ESTABLISHED]`
- Volume: ~1.5 L (1.4 L brain + perfusate)
- Vibration: magnetorheological suspension (§2.1.1)
- Inputs: 4 carotid + 2 vertebral artery analogs (perfusion in)
- Outputs: jugular vein analog (perfusion out)
- Sensor ports: 200+ channel intracortical arrays

### 5.3 Body–brain interface (entirely BCI)
- Multi-region cortical mesh — 10,000+ channels `[ESTABLISHED]` (as prototype) / `[THEORETICAL]` at the densities required
- Optical neural interface — calcium imaging + optogenetics for low-noise readout `[ESTABLISHED]` (as a lab technique)
- Whole-body reflex AI — replaces spinal cord and brainstem entirely `[SPECULATIVE]`
- Autonomic emulator — simulates respiratory, cardiovascular, thermoregulatory output `[SPECULATIVE]`

### 5.4 Advantages
- Smallest life-support footprint — best suited to mass production.
- Best brain protection — fully sealed chamber.
- The body becomes freely replaceable.
- Modular maintenance — any subsystem can be serviced without touching the brain.

### 5.5 Disadvantages / challenges (severe)
- Must simulate the entire autonomic system — complexity comparable to engineering a new organism `[SPECULATIVE]`.
- Bandwidth: current BCI moves ~KB/s; the brain needs at least MB/s.
- Sensory-deprivation risk — locked-in syndrome and suffering.
- Loss of embodiment — the brain may lose its body schema.
- Hormone simulation: 50+ feedback loops not yet fully understood (§7.5).
- Hardest to clear ethically.

### 5.6 Technology Readiness

| Component | TRL | Status |
|---|---|---|
| Brain perfusion (>1 year) | 1 | BrainEx reached 6 h |
| Full autonomic emulation | 1 | Partial theory |
| 10,000+ channel BCI | 4 | Neuralink prototype |
| Hormone replacement (full panel) | 2 | Endocrine system not fully modeled |
| Body-schema preservation | 2 | Phantom-limb research suggests feasibility |

---

## 6. Consolidated Comparison

| Dimension | A — Conservative | B — Balanced | C — Aggressive |
|---|---|---|---|
| Biological scope | Brain + brainstem + spinal cord | Brain + brainstem | Brain only |
| Bandwidth (brain→body) | Very high (near-native) | Moderate (via BCI+AI) | Low (currently) |
| Autonomic system | Natural | Natural | Fully simulated |
| Life-support size | Large (~50 L) | Medium (~10 L) | Small (~3 L) |
| Identity-loss risk | Low | Moderate | Very high |
| Locked-in / suffering risk | Low | Moderate | High |
| Modularity (body swap) | Low | Medium | Highest |
| Average current TRL | 5–6 | 4–5 | 1–2 |
| Time estimate | 10–20 yr | 20–40 yr | 50+ yr / may not succeed |
| Target user | Severe disability / aging | ALS / quadriplegia | Experimental life extension |

---

## 7. Technology Gaps That Must Be Closed First

Each gap notes why the obvious fix is insufficient and what might actually work.

### 7.1 Long-term brain perfusion
The single largest gap. BrainEx sustains ~6 hours; the target is years. Open problems:
- Microvascular degradation — cumulative capillary deterioration.
- Astrocyte / glial dysfunction.
- Waste clearance (the glymphatic system) must be emulated.
- Long-term hormone feedback (§7.5).

> **Partial mitigation:** the maintenance cycle (§2.5) helps — periodic perfusate exchange and flushing may reset waste accumulation. It does **not** fix microvascular degradation, which is intrinsic tissue aging. This remains a genuine open problem `[THEORETICAL]`.

> **Scope of what perfusion solves:** long-term perfusion addresses *acute* death from loss of blood supply. It does **not** halt *chronic* neuronal aging — neurons are post-mitotic and accumulate proteinopathy, DNA damage, and mitochondrial decline regardless of perfusion quality. That is a second, distinct ceiling (§16.6), not the same problem as keeping the tissue oxygenated.

### 7.2 Durable neural electrodes
Gap: implanted electrodes degrade within 5–10 years. Why silicone coating or a tougher organic material is not enough — the real failure has **three stacked causes**, not "material wear":
- **Foreign-body response** — the body attacks anything non-self; however inert the material, astrocytes encapsulate the electrode and the signal fades even though the electrode is intact.
- **Mechanical mismatch** — brain tissue is soft (1–3 kPa); electrodes are stiff (silicone ~1 MPa; metal 100+ GPa). Every head movement causes cumulative micro-injury.
- **Biofouling** — proteins in cerebrospinal fluid coat the electrode within the first hour, reducing conductivity.

Organic / conducting materials already tried (better, but they do not fix causes 1–2): PEDOT:PSS, graphene, carbon nanotube, silk fibroin `[ESTABLISHED]` (as materials research).

What might actually work:
- **Modulus-matched mesh electrodes** (**Lieber lab, Harvard**) — the brain treats them as native tissue and forms no scar `[ESTABLISHED]` (demonstrated in animals) — this addresses causes 1–2 at the root.
- **Hydrogel electrodes** — soft, ionically conductive, tissue-compliant interfaces that directly attack the modulus mismatch (cause 2); a major 2026 review direction (Li et al., *Advanced Materials* 2026) `[ESTABLISHED]` (as materials research). Consistent with the hydrogel buffer adopted in §14.
- **Non-penetrating subdural thin-film arrays** — high-density electrodes that sit *on* the cortical surface instead of piercing it, sharply reducing causes 1–2. **Precision Neuroscience "Layer 7"** (1,024-electrode thin-film array) was FDA-cleared as a temporary mapping device and used in first human recipients in 2025–2026 `[ESTABLISHED]` (clinical, as a temporary device).
- **Optical interface** — no implanted electrode; light reads/stimulates (requires opsin expression in neurons) `[ESTABLISHED]` (as a technique) / `[THEORETICAL]` for a whole human brain.
- **Neural dust** — sub-100 µm sensors dispersed without destroying tissue (**Seo, Carmena, Maharbiz et al., UC Berkeley**) `[ESTABLISHED]` (proof of concept).

> **Key point:** the lever is not "find a tougher material" but "stop the brain from seeing the implant as foreign" — addressed by modulus matching, hydrogel compliance, or staying on the surface, not by coating. **Honest caveat (2026):** these *reduce* the foreign-body response; they do not eliminate it. Every conductive material still differs chemically from neural tissue, and even the most flexible electrode remains orders of magnitude stiffer than brain — so this is de-risking, not a closed problem.

### 7.3 BCI bandwidth and the "direct interface" idea
Gap: current BCI moves <1 MB/s; the brain processes on the order of GB/s. *(Caveat: the "GB/s" figure is an order-of-magnitude estimate and is genuinely contested — the brain's effective I/O bandwidth depends heavily on how it is defined. The qualitative gap is real; the exact number should not be treated as settled.)*

The author's "connect straight to the endpoint" idea — a **direct synaptic / molecular-level interface** that communicates with the synapse or molecular machinery rather than reading extracellular signals `[USER'S OWN]` framing:
- Status: no such technology exists. There are 100+ trillion synapses; none can be individually addressed.
- "Writing" directly into a synapse means changing molecular state deterministically — not currently possible.
- Microtubule-based readout (Penrose–Hameroff *Orch-OR*) — even if the theory were correct, there is no method to read/write the tubulin protein `[THEORETICAL]` `[CONTESTED]`. *Orch-OR* is a **minority position** among neuroscientists `[MINORITY VIEW]`.

Closest real research:
- **Optogenetics** (**Boyden & Deisseroth, 2005**) — opsin genes let light drive neurons (good at writing, poor at reading) `[ESTABLISHED]`.
- **Calcium imaging** — readout ~100× finer than current BCI `[ESTABLISHED]`.
- **Functional ultrasound BCI (fUS)** — reads neural activity acoustically (via local blood-flow changes) **without penetrating the brain**; demonstrated real-time decoding of movement direction stable over a month in primates `[ESTABLISHED]` (primate-stage). A genuinely new, non-penetrating reading modality — it sidesteps the foreign-body problem entirely, at the cost of slower (hemodynamic) signals and, so far, less depth/resolution than intracortical electrodes.
- **Speech-restoration BCIs** — decoding attempted speech rather than cursor control: **Paradromics "Connect-One"** (high-bandwidth, fully implantable; FDA early-feasibility) entered first-in-human in 2025–2026 `[ESTABLISHED]` (clinical trial). Raises the practical decoding bandwidth bar but does not close the order-of-magnitude gap above.
- **Organoid intelligence** (term coined by **Thomas Hartung, Johns Hopkins**, 2023) — culturing small brains in dishes to learn encode/decode methods `[THEORETICAL]` (emerging field).

> **Honest assessment:** a direct molecular interface is likely 50–100 years out, or requires a neuroscience paradigm not yet in hand. It is not an engineering problem solvable with current technology `[SPECULATIVE]`.

### 7.4 Power and heat
Gap: the brain dissipates ~20 W continuously, plus hundreds of watts of other systems, in a confined space.

Solution (revised from Rev 1): active refrigeration as primary (full detail in §2.4).
- Vapor-compression AC — COP 2–3; precise temperature control; works in hot ambient `[ESTABLISHED]`.
- R744 (CO₂) refrigerant — safe on leak `[ESTABLISHED]`.- Passive radiator + vent — backup, not primary `[ESTABLISHED]`.
- Evaporative analog (microfluidic skin) — optional supplement if sweat-like cooling is desired `[ESTABLISHED]` (research demo).

> **Human comparison:** a person rejects ~100 W (skin ~40 W + sweat ~50 W + breath ~10 W); sweat is the dominant mechanism. A synthetic body need not imitate it — AC gives better engineering control, exactly as in every data center `[ESTABLISHED]`.

### 7.5 Endocrine simulation
Gap (most acute in Architecture C): hormones operate in feedback loops not yet fully understood.

The correction to "just inject synthetic hormones" (the "refuel" model): synthetic hormones **can** be added (insulin, thyroxine, cortisol are clinical today) `[ESTABLISHED]` — but the hard part is that they must form **situation-responsive feedback loops**:
- Example: a startle → brain command → adrenal release of cortisol + adrenaline within 30 s → arousal → decline over ~20 min.
- A constant high dose → chronically elevated cortisol → organ damage + immune suppression.
- A constant low dose → no response to danger.

What must actually be built (equivalent to recreating the entire endocrine system):
- Sensors reading the brain/brainstem's hormonal demand.
- A decision system setting dose and timing.
- Pulsatile delivery — growth hormone releases during sleep; LH pulses every ~90 minutes; not continuous.
- Multi-hormone orchestration — insulin–glucagon and T3–T4–TSH must balance simultaneously.

Axes to emulate: pituitary–hypothalamus, HPA (stress), reproductive hormones, circadian regulation `[ESTABLISHED]` as physiology; full artificial emulation is `[THEORETICAL]`/`[SPECULATIVE]`.

> **Why this makes Architecture C hard:** Architectures A and B sidestep it by retaining the brainstem and nervous system, so most natural feedback loops keep working.

---

## 8. Recommendations

For development over the next 10–30 years, **Architecture A** is the most defensible choice — not because it is "less science-fiction," but because each component is already in clinical use or trials; the work is integration.

**Architecture B** suits the mid-term (20–40 years) and needs breakthroughs in two areas: long-term electrodes (§7.2) and a brainstem interface.

**Architecture C**, as described, is still too speculative to be an engineering project today; it fits better as a thought experiment / research north star. Its blocking gaps are §7.1, §7.3, and §7.5, none of which have a proven solution.

### Path to a first prototype
1. **Phase 1 (5 yr):** integrate peripheral nerve interface + osseointegration + biometal limb for amputees, with bidirectional sensory feedback.
2. **Phase 2 (10 yr):** extend to full-body skeleton replacement for muscular dystrophy / advanced stages.
3. **Phase 3 (15–20 yr):** integrate brain perfusion for end-of-life patients whose bodies have failed but whose brains are intact.
4. **Phase 4 (20+ yr):** pursue Architecture B if electrode/interface technology has advanced sufficiently.

### Design principles drawn from this review
- Solve only the constraints that actually exist, not imagined ones ("the brain must be still" is real; "the whole body must be still" is not) `[USER'S OWN]`.
- Do not imitate every human mechanism; use what engineering does better (AC instead of sweat) `[USER'S OWN]`.
- No sealed-for-life requirement when a maintenance cycle already exists — consolidate all servicing `[USER'S OWN]`.
- Beware "easy fixes" that do not touch the root cause (coating does not fix the foreign-body response; modulus matching does).

### Ethics — prerequisites before any human trial
- **Reversibility** — can it be undone if the patient asks?
- **Consent capacity** — can a near-death patient truly consent?
- **Identity continuity** — what criterion establishes that it is still the same person?
- **Suffering monitoring** — how is locked-in / distress detected?
- **Exit pathway** — if the system fails, can the patient die with dignity?

---

## 9. Design Decision Log — Rejected & Superseded Options

**Purpose:** this log records options that were considered and rejected, with the reason. It exists to prevent re-opening settled questions and recycling ideas that have already been ruled out. **Do not reintroduce a rejected option without new evidence that specifically overturns the stated reason.** Every future revision appends to this log rather than silently dropping ideas.

**Adopted paths — what was chosen and why** (the companion to the rejected-options table below: this records *why each chosen path was chosen* and what it beat; the table after it records *why each alternative was cut*).

| Decision area | Adopted | Chosen over | Why adopted | Rejected alt. |
|---|---|---|---|---|
| Tissue retained | Three-way A/B/C comparison; lead with A | (a single fixed design) | A preserves natural signal pathways and has the highest TRL; B/C progressively trade bandwidth for modularity | — |
| Primary cooling | Active vapour-compression AC | passive radiation; thermoelectric (Peltier) | holds 37 °C ±0.5; works in hot ambient; can spot-cool the brain | §9 #4, #5 |
| Brain vessel | Retain the original skull | a synthetic Ti vessel | natural armour; preserves meninges + native vasculature; far less dissection | — |
| Containment | Skull + outer carapace (double) | a single shell | redundancy; the carapace bears pressure so the skull need not seal | — |
| Buffer / fluid | One perfusate + open-cell hydrogel | separate fluids; a rigid mount | one fluid does vibration damping + thermal mass + cooling-loop transport | — |
| Neural link | Split-plug: permanent brain-side port + swappable body plug | a single through-plug; a fixed interface | moves the fast-degrading parts to the body side; a sealed hub removes the puncture-infection path | §9 #8; part of #2 |
| Maintenance | Dual-loop + backup-perfusion bridge | "do it fast" (accept brief ischemia) | never a no-perfusion moment; removes the single point of failure | §9 #14 |
| Transfer | Deep hypothermia + anaesthesia; vessel-level handoff | cutting warm; hibernation; peel-out dissection | hours of ischemia margin (real cases); humane; avoids re-anastomosing thousands of microvessels | §9 #15 |
| Perfusion control | Closed-loop adaptive | constant pressure | matches regional demand (approximates autoregulation) | — |
| Power | Li-ion + supercap now; solid-state later | solid-state now | Li-ion is deployable in 2026; solid-state is not yet field-proven at scale | §9 #10, #11 |
| Roadmap | Phase 1 real brainstem → Phase 3 artificial | starting at Architecture C | deploy before perfecting; sidesteps the chicken-and-egg of an unproven artificial brainstem | — |
| Sensorium | Broad-spectrum via sensory substitution | human senses only; tapping a "new" channel | strict upgrade over biology; firewalled to known physics | §9 #1–#2 |

**Rejected & superseded options** (why each alternative was cut):

| # | Option considered | Verdict | Reason | Tag |
|---|---|---|---|---|
| 1 | Quark-wave actuation of metals | **Rejected** | No such phenomenon. Quarks are confined by QCD color confinement and cannot be emitted as a "wave" to actuate anything. | `[ESTABLISHED]` |
| 2 | Direct brain-wave actuation of external metal | **Rejected** | Brain EM signals are ~10⁹× too weak. Metals can *detect* brain signals (EEG electrodes) but brain waves cannot *drive* metal. | `[ESTABLISHED]` |
| 3 | Microtubule (Orch-OR) as the read/write neural interface mechanism | **Rejected as mechanism** | Orch-OR is contested and a minority position; no method exists to read or write tubulin-protein state. The *emergency-gated reflex-store behavior* derived from this idea was **retained** and reimplemented on conventional neuromorphic hardware (§4.3). | `[CONTESTED]` `[MINORITY VIEW]` |
| 4 | Passive radiation / sweat-analog as **primary** cooling | **Superseded** | Cannot hold ±0.5 °C and fails in hot ambient (e.g. 35 °C). Replaced by active vapor-compression AC as primary; passive retained only as backup (§2.4). | `[ESTABLISHED]` |
| 5 | Thermoelectric (Peltier) as **primary** cooling | **Rejected** | COP 0.5–1, far worse than vapor compression's 2–3. Retained only for tiny localized spot-cooling. | `[ESTABLISHED]` |
| 6 | Sealed-for-life enclosure | **Rejected** | Unnecessary and dramatically harder, since nutrient/perfusate replenishment is periodic anyway. Replaced by a unified maintenance cycle (§2.5). | `[USER'S OWN]` |
| 7 | Whole-body vibration isolation | **Rejected** | Over-constrained. The frame may vibrate freely (no nerves to injure); only the brain vessel needs isolation (§2.1.1). | `[USER'S OWN]` |
| 8 | Silicone / organic coating as the electrode-longevity solution | **Rejected as sufficient** | Does not address the two root causes (foreign-body response, mechanical mismatch). Modulus-matched mesh electrodes address the root (§7.2). | `[ESTABLISHED]` |
| 9 | "Inject hormones at a constant rate" (refuel model) | **Rejected as sufficient** | Constant dosing causes organ damage (chronic high) or non-response (chronic low). Requires situation-responsive feedback loops (§7.5). | `[ESTABLISHED]` |
| 10 | Donut Labs 100,000-cycle solid-state battery as a deployment basis | **Rejected (claim unverified)** | No third-party verification across 5 reports; the test cell was already damaged (lost pouch vacuum). Not used as a basis for any deployment claim. Credible field figure is ~6,000–8,000 cycles (§2.6). | `[THEORETICAL]` |
| 11 | Sulfide-based solid-state electrolyte for a body-worn unit | **Rejected** | Reacts with air/moisture to release toxic H₂S — unacceptable next to a living brain. Prefer oxide/polymer electrolytes. | `[ESTABLISHED]` |
| 12 | Direct synaptic / molecular-level interface as a **near-term** path | **Deferred** | No method to address individual synapses (100+ trillion); ~50–100 years out or needs a new paradigm. Retained as a research north star only (§7.3). | `[SPECULATIVE]` |
| 13 | Artificial brain cells from metal alloy to replace biological neurons | **Rejected (category error + scale)** | Artificial neurons emulate neuron *function* in silicon (CMOS: Loihi, TrueNorth) or organic-electrochemical substrates — they are not metal-alloy biological replacements. Metal is used for electrodes/interconnects, not the cell body. They exist only at single-device / small-circuit scale vs ~86 billion neurons. The architecture keeps the **real** brain; artificial neurons are relevant only to peripheral emulation layers (§4.3, §10.4), where biohybrid organic neurons are an emerging option. | `[ESTABLISHED]` (state of the art) / `[SPECULATIVE]` (whole-brain) |
| 14 | Speed-dependent body swap (accept brief loss of perfusion, "do it fast") | **Rejected** | Creates a single point of failure — a slip, jam, or power glitch causes permanent brain damage. Replaced by a permanently sealed inner loop (swap touches only the outer layer) and, for deep maintenance, a backup-perfusion bridge connected *before* the old line is removed (§15). No moment without perfusion; no need for speed. | `[USER'S OWN]` |
| 15 | True hibernation / synthetic torpor in humans (to protect the brain during transfer) | **Rejected as current mechanism** | Humans are not hibernators and have no torpor biochemistry; human synthetic torpor is early-stage research only. The intended protective effect is achieved instead with established **deep hypothermia + anesthesia** (§11, §13). | `[SPECULATIVE]` |
| 16 | Nano-material replacement of identity-storing neurons (gradual swap during infusion) | **Deferred (connectome + identity wall)** | Unlike support tissue, a neuron's "content" is its ~1,000–10,000 weighted synaptic connections — replacing it requires reading and reproducing the full connectome, which cannot currently be read for even 1 mm³ at speed, let alone a whole brain. Also raises an unresolved Ship-of-Theseus identity question. **Replacing support tissue (glia, vasculature) is not blocked** and may help extend brain life (§16.6); replacing identity-bearing neurons is. | `[SPECULATIVE]` |
| 17 | "Shield the brain alone; a thicker shield is always safer" | **Partially rejected (radiation physics)** | Galactic cosmic rays (esp. HZE) hitting shielding produce **secondary-particle showers** (spallation neutrons, pions). Biological dose reaches a *minimum* near ~20 g/cm² aluminium and **rises** with more aluminium (forward-scattered secondaries); secondary pions can add ~10% of dose and cause lasting cognitive impairment. Hydrogen-rich material (polyethylene, water) emits far fewer secondaries and is preferred. Two further corrections: **(a)** the **compute layer (BCI/neuromorphic) is independently radiation-sensitive** (SEU, latch-up) and must be **rad-hardened by design** (rad-hard parts, redundancy, ECC, active detection) — shielding does not fix it; Architecture C, most compute-dependent, is most exposed. **(b)** Residual HZE penetrating any practical shield still damages neurons/cognition permanently — the risk is reduced, not eliminated. | `[ESTABLISHED]` |
| 18 | "Long-term perfusion unlocks lifespan extension" | **Scope correction (two ceilings, not one)** | Perfusion solves *acute* death from loss of blood supply. It does **not** halt *chronic* neuronal aging — neurons are post-mitotic and accumulate proteinopathy, DNA damage, and mitochondrial decline regardless of perfusion. Because identity-bearing neurons cannot be replaced (#16), there is a **hard lifespan ceiling perfusion cannot lift**. Support-tissue upkeep (§16.6) helps partially. Conclusion: the project has **two** biological bottlenecks — acute (perfusion) **and** chronic (neuron senescence) — not one. | `[ESTABLISHED]` |

> **Standing practice (from Rev 4 onward):** every design choice in this document states *why it was chosen* and *why the alternatives were cut*. Rejected ideas are logged here permanently, not deleted. This prevents the project from re-deriving and re-killing the same dead ends.

---

## 10. System Stability — Weakest-Link Analysis

**Principle:** total system stability equals the stability of the *weakest* subsystem. A coherent design document is not a buildable system. This section tracks the real bottleneck honestly and is updated every revision, so progress can be measured against the constraint that actually binds.

### 10.1 Current stability by subsystem (mid-2026)

| Subsystem | Real stability ceiling | Status | Bottleneck |
|---|---|---|---|
| Body frame + joints (biometal) | High — clinical today | Solid | — |
| Cooling (active AC) | High — mature engineering | Solid | — |
| Power (Li-ion) | High — deployable now | Solid | — |
| Limb + sensory feedback | Medium — prototype/trial | Partial | Coarse bandwidth |
| Reflex bypass | Medium–low — lab demo | Partial | Not yet integrated |
| **Brain perfusion (long-term)** | **Low — ~6 hours** | **Blocking** | **Ex-vivo tissue survival** |
| Durable neural electrode | Low — degrades 5–10 yr | Blocking (Arch B/C) | Foreign-body response |
| Autonomic / hormone emulation | Near zero | Blocking (Arch C only) | Not yet modeled |

### 10.2 Binding constraint

As of mid-2026 the headline binding constraint is **acute — brain perfusion at ~6 hours** (§7.1). Even if every other subsystem were 100% ready, the integrated system is capped at this figure for survival. This is a **biology** problem — keeping neural tissue alive outside the body — not a body-engineering problem. Body engineering is the part that is nearly solved; tissue survival is the part that is not. The project's honest "stability number" is therefore **< 2 days, with no consciousness yet demonstrated inside it.** (A second, *chronic* biological constraint — neuron aging — is covered below; it does not affect the ~6 h survival number but it caps lifespan.)

**What is *not* the bottleneck (resolved in design):** the *transfer window* — the act of moving the brain into the vessel — is manageable, not blocking. Deep hypothermia plus anesthesia buys hours of safe ischemia-protected time (real cases show 5–9 h of hypothermic cardiac arrest with full neurological recovery; §11), and a backup-perfusion bridge removes any no-perfusion gap during maintenance (§15).

**Status of the two former blockers:**
- **Electrode foreign-body response (5–10 yr)** — *de-risked by design* via the split-plug port (§12): the fast-degrading interface sits on the swappable body side, while the brain-side port is built for longevity. Remaining work is materials science (make the brain-side port last), not a logical blocker.
- **Long-term post-transfer perfusion (6 h → years)** — *still a hard blocker — the acute one (bottleneck #1 below).* It is intrinsic neural-tissue survival and cannot be designed around; it must be solved at the tissue level (§7.1, §16.6).

**Space scope adds no *new* bottleneck, but radiation is more involved than first stated (§16.3):** the spacecraft/habitat provides bulk shielding, thermal control, and resupply, and a synthetic body is in several ways *better* suited to space than a biological one (no muscle atrophy, no bone loss, lighter payload). However, radiation is not fully solved by "shield the brain": cosmic-ray secondary showers mean thicker shielding can *worsen* dose (hydrogen-rich material required), and the compute layer must be **rad-hardened** independently of shielding (§9, #17).

**The binding constraints are biological, and there are two of them — not one:**
1. **Acute — long-term perfusion** (6 h → years): keeping the tissue alive and oxygenated. Cannot be engineered around (§7.1).
2. **Chronic — neuron senescence**: even with perfect perfusion, post-mitotic neurons age (proteinopathy, DNA damage, mitochondrial decline), and identity-bearing neurons cannot be replaced (§9, #16). This sets a lifespan ceiling perfusion cannot lift (§16.6).

Both are tissue biology, not engineering. The earlier "single binding constraint" framing was incomplete: solving perfusion extends survival but does not, by itself, deliver open-ended lifespan.

### 10.3 Brain maintenance / preservation — what is actually available (2026)

Three categories with **fundamentally different goals** — they are not interchangeable:

| Approach | Goal | What it achieves | Fits living-brain architecture? |
|---|---|---|---|
| **Active perfusion** — BrainEx (Vrselja & Sestan 2019) `[ESTABLISHED]` | Keep the brain biologically **alive** | ~6 h; restored microcirculation + molecular activity in pig brain post-mortem | **Yes** — required by Architectures A/B/C |
| **Aldehyde-stabilized cryopreservation (ASC)** — McIntyre & Fahy 2016, 21st Century Medicine `[ESTABLISHED]` | Preserve **structure** (connectome) indefinitely | "Near-perfect" ultrastructure at −135 °C, EM-verified; 2026 protocols made compatible with physician-assisted death | **No** — tissue is chemically **fixed (dead)**; different philosophy: preserve now, scan/emulate later |
| **Straight vitrification** — classical cryonics `[CONTESTED]` | Preserve for future revival | Shrinks brain ~50%, compresses/obscures connectome | Weakest for structure; revival unproven |

> **Critical distinction:** active perfusion and ASC answer different questions. Active perfusion asks *"can the brain keep working now?"* (answer: briefly). ASC asks *"can we freeze the structure to read or emulate later?"* (answer: yes, but the brain is no longer alive). The architectures here depend entirely on the **active-perfusion** path, whose ~6 h ceiling is the project's true bottleneck. ASC is logged not as a competitor but as a different escape route that abandons the living-brain premise.
>
> *Forecast context:* practitioners surveyed in 2025 estimate aldehyde-free connectome preservation by ~2030–2040 (≈56% at 50% confidence), while ≈25% would not be 90%-confident before 2100 or ever `[CONTESTED]` (forecast, not result).

### 10.4 On "artificial brain cells"

We **cannot** build artificial brain cells from metal alloy to replace biological neurons (§9, #13). Artificial neurons exist in two forms, both of which *emulate function* rather than biologically replace a neuron:

- **Silicon CMOS neuromorphic** (Loihi, TrueNorth) — computational emulation `[ESTABLISHED]`.
- **Organic electrochemical neurons (OECN)** — operate in liquid, respond to ions and neurotransmitters (e.g. dopamine), emulate Na⁺/K⁺ channel dynamics, and form biohybrid interfaces with living cell membranes (Nature Electronics 2022; npj Flexible Electronics 2026 — first organic spiking neuron with excitatory + inhibitory synapses) `[ESTABLISHED]` as research.

Metal serves as electrodes/interconnects, **not** as the cell body; the substrates in use are metal-oxides, organic polymers, and phase-change materials, not "metal alloy." Scale gap: the brain has ~86 billion neurons; this research is at the single-device / small-circuit level.

**Implication for this project:** the brain itself must remain the real, biological brain — there is no substrate that can replace it. Artificial neurons are relevant only to the peripheral emulation layers (reflex bypass, spinal CPG; §4.3), where biohybrid organic neurons are a promising emerging option. This reinforces why §10.2's bottleneck is *keeping the real brain alive*, not *replacing it*.

---

## 11. Transfer Protocol — Moving the Brain Into the Vessel

This section addresses the **transfer window**: the surgical act of moving the brain into its life-support vessel. It reduces ischemic damage *during* the move. It does **not** solve long-term perfusion (§7.1) — that is a separate, post-transfer problem.

### 11.1 Principle: cool first, never cut warm

The brain must be protected *before* circulation is interrupted, not after. Lowering temperature drops metabolic demand (Arrhenius), so the brain tolerates far longer without oxygen. The ordering is non-negotiable: **anesthesia → cooling → vascular handoff**, never cutting at normal temperature.

Real-world basis `[ESTABLISHED]`: in accidental deep hypothermia, patients have achieved **full neurological recovery after 5–9 hours** of hypothermic cardiac arrest, provided hypothermia *preceded* the arrest and rewarming followed promptly (documented cases at 26 °C core temperature, CPR + extracorporeal support up to 8 h 42 min, recovery to normal life). The clinical maxim is *"nobody is dead until warm and dead."* This is the empirical anchor for the transfer window.

### 11.2 Two distinct mechanisms — do not conflate

- **Anesthesia** — ensures no awareness or distress during the procedure. Required for humane transfer; a cooled-but-unanesthetized brain might still experience the early phase.
- **Deep hypothermia (18–26 °C)** — protects tissue against ischemia. This is *not* "hibernation": humans have no torpor biochemistry (§9, #15); the protective effect comes from induced hypothermia, an established clinical tool.

### 11.3 Procedure

1. Induce anesthesia.
2. Controlled cooling to 18–26 °C (sub-37 °C transport mode, §13).
3. **Vascular handoff at the large vessels, not tissue dissection.** Connect perfusion to the carotid + vertebral arteries (4–6 large vessels), then cut at the vessel level and lift the brain + brainstem as one unit — the BrainEx approach. Do **not** dissect brain tissue free vessel-by-vessel; thousands of cerebral microvessels cannot be individually re-anastomosed (this is why fine "peel it out slowly" approaches fail).
4. Retain the **skull** as the inner vessel (§14) — no need to shell the brain out; the skull is the best natural armor and preserves the meninges and native vasculature. Seal the foramen magnum and remaining foramina.
5. Maintain continuous perfusion; rewarm to 37 °C only once inside the vessel and stable.

> **Scope flag:** §11 protects the brain *during the move* (now hours of margin, not minutes). It does not extend how long the brain survives *after* the move — that ceiling remains ~6 h (§7.1, §10.2).

---

## 12. Modular Neural Port — Plug-and-Play Body Coupling

A standardized neural port permanently fixed to the brain, with the **body** as a swappable plug. This partially addresses Blind Spot 2 (electrode swap): the fast-degrading parts move to the body side (easy to replace), leaving only a long-life port on the brain side.

### 12.1 Two-layer architecture (not a single through-plug)

A single plug piercing into the brain reintroduces infection risk at the puncture. Instead, three nested stages:

- **Permanent neural interface** (organic/OECN or modulus-matched mesh) — sits against neural tissue, designed for maximum longevity, never removed.
- **Sealed signal hub** in the vessel wall — no open puncture; signal crosses by inductive/optical coupling. This eliminates the percutaneous infection path.
- **External port** on the vessel surface — the body plugs in here; freely replaceable.

### 12.2 Components and status

- Organic electrochemical interface operating in the perfusate `[ESTABLISHED]` (research); the perfusate is formulated to also preserve the interface (controlled pH, anti-fouling).
- Quick-disconnect self-sealing coupling for fluid/signal lines `[ESTABLISHED]` (medical/aerospace) — enables body swaps without leakage.
- Hermetic feedthrough for signal lines `[ESTABLISHED]` (used in pacemakers).

### 12.3 What it solves and does not

- **Solves:** easy body replacement; moves the fast-wearing components off the brain; removes the open-puncture infection path.
- **Does not solve:** bandwidth (a detachable 10,000-channel port is still 10,000 channels; §7.3), nor the foreign-body response at the tissue-contact layer (still needs mesh/optical; §7.2). The port is the *connection* layer, not the *reading* layer.
- **Alignment caveat:** each body swap must remap channels to the previously mapped neuron groups via software, or recalibration is required each time.

---

## 13. Dual Thermal Mode

The system runs in one of two temperature regimes, never confusing them:

| Mode | Target | Purpose |
|---|---|---|
| **Operating** | **37 °C ±0.5 °C (locked)** | Full cognition. Cooling prevents overheating under load; the brain is *not* run cold (a colder brain thinks slower — §2.4). |
| **Transport / emergency** | 18–26 °C | Tissue protection when the brain is *not* working — during transfer (§11) or a body/maintenance swap. Always paired with anesthesia. |

The cooling fluid circulates as a **closed loop**: it picks up heat around the brain and skull cavity, flows down the body through quick-disconnect couplings to the heat exchanger / AC unit in the torso, and returns cooled. Heat thus *leaves the system*, rather than merely being buffered inside the head (§14.2).

> **Correction logged:** an earlier framing ("lock at the lowest possible temperature") was wrong and is rejected in spirit by this section. Lowest-possible would impair cognition. The correct target is a *stable 37 °C* in operating mode.

---

## 14. Double Containment & Buffer Layer

### 14.1 Nested structure

The brain is protected by two shells, not one:

- **Inner: the original skull** — holds the brain, preserves meninges and native vasculature, and serves as natural armor. It does not need to bear perfusion pressure.
- **Outer: an engineered carapace** — provides the hermetic seal and bears pressure, so the skull is relieved of sealing/pressure duty. Fitted with diving-helmet-style sealing: bulkhead/gland fittings for fluid lines, hermetic feedthroughs for the neural port, quick-disconnect couplings for body swaps.

This double containment adds redundancy: a minor skull-seal leak is caught by the carapace.

### 14.2 Buffer layer — one fluid, three jobs

The skull-to-carapace gap is filled with an **open-cell hydrogel** saturated with the **same perfusate** used around the brain `[ESTABLISHED]` (hydrogels are used in contact lenses, wound dressings, tissue scaffolds). This single design element does three things at once:

- **Vibration damping** — a soft, fluid-swollen layer cushions the skull, adding a second layer to the brain's natural CSF cushioning (§2.1.1).
- **Thermal mass + transfer** — the added fluid volume buffers heat (water's high heat capacity), and because the buffer fluid is part of the circulating loop (§13), heat is carried out to the body heat exchanger rather than merely stored.
- **Single-fluid simplicity** — one fluid for brain perfusion, cushioning, and cooling; replenished together in one maintenance cycle.

> **Conditions flagged:** (1) the hydrogel must be **open-cell with flow channels** so the fluid circulates (convection), not stagnant — a buffer that only stores heat eventually overheats; real cooling needs the loop. (2) Hydrogels degrade over time → chosen for stability and replaced on the maintenance schedule. (3) More fluid means more pump load and head weight → balanced against thermal benefit. (4) Porous media can harbor biofilm → antimicrobial in the fluid + scheduled replacement.

---

## 15. Maintenance Architecture — Servicing Without a Perfusion Gap

Two service cases, handled differently. Neither relies on speed.

### 15.1 Case A — Body swap (frequent)

Touches only the **outer layer** (§12 external port). The inner sealed loop (brain + skull + perfusate) is never opened. Quick-disconnect couplings self-seal on both sides, so no fluid is lost and the brain is never deprived. No speed required.

### 15.2 Case B — Inner maintenance (rare): replace carapace or spent buffer

The key is **separating the brain-perfusion loop from the buffer cavity**, so most inner servicing never touches the fluid that perfuses the brain:

```
Inner:  brain + skull + perfusate   ← own SEALED loop, in/out via quick-disconnect
Middle: hydrogel buffer + fluid      ← separate; replaceable without opening the inner loop
Outer:  carapace                     ← removable without opening either
```

- Replace **buffer** → open the middle cavity; the inner perfusion loop stays sealed. No interruption.
- Replace **carapace** → remove the outer shell; inner stays sealed. No interruption.

### 15.3 If the inner loop itself must be opened — backup-perfusion bridge

When the perfusate or inner loop genuinely must be accessed, use the medical "bridge" principle (as in ECMO circuit changes): **connect the new/standby line before disconnecting the old one.**

1. Anesthesia + cooling (transport mode, §13) — buys hours of margin.
2. Connect a **backup perfusion line** from a bedside unit; fluid now flows via two paths.
3. Close/remove the original line; flow continues from the backup — the brain is never without perfusion.
4. Service the loop / replace perfusate.
5. Reconnect the primary, resume flow, remove the backup.

> **Principle:** never a moment without perfusion. Like a climber clipping the new rope before unclipping the old — there is never an instant with nothing holding. This replaces the rejected "do it fast" approach (§9, #14), which created a single point of failure.

---

## 16. Project Scope, Adaptive Life-Support, and Roadmap

This section defines what the project actually is, consolidates the life-support upgrades developed in design review, and states the development sequence. It also resolves a set of apparent blind spots that only existed under a wrong assumption (a brain kept dormant in a jar).

### 16.1 Scope statement

The goal is **lifespan extension and space exploration** via a human brain in an *actively used* synthetic body — not a dormant brain-in-a-jar. This distinction matters because two feared failure modes disappear under the real scope:

- **Sensory deprivation** is not a risk: an actively used body (vision, hearing, touch, proprioception via the body's sensors) continuously feeds the brain meaningful input, the same way an embodied human receives it. (Caveat: if the brain is held vessel-only with no body for a long maintenance period, substitute input — e.g. simulated/VR streams — is still needed.)
- **Sleep / autonomic regulation** is handled by the retained brainstem in Phase 1 (§16.7).

**The goal is bounded — extension, not immortality.** The aim is to *extend* healthy human lifespan and capability enough to travel and persist farther in space, and to live with fewer of the body's physical limitations. It is **not** to make any individual immortal. Indefinite individual lifespan would additionally require defeating neuronal senescence (§16.6), and it cannot be reached by copying the mind into a substrate — that produces a copy, not continuity (a closed route; §9 #16). The synthetic body is a tool for reach and resilience, not a path to immortality.

> **Scope note:** consciousness and sensory input are *not the same thing* (§16 supersedes an earlier conflation). "Inserting consciousness" does not supply input; an actively used body does. The architecture already plans bidirectional BCI + sensory feedback, so an embodied, working brain is fed by definition.

### 16.2 Why a synthetic body suits space

A synthetic body is in several respects *better* suited to space than a biological one — the major astronaut health problems largely vanish:

- No muscle atrophy (no muscle), no bone density loss (no biological bone) in microgravity.
- No food/water/air consumption on the biological scale → far lighter payload.
- Metal structure tolerates radiation far better than soft tissue, so the *structure* needs little protection — but two things still do: the **brain** (radiation-sensitive tissue) and the **compute layer** (BCI/neuromorphic chips, which suffer single-event upsets and must be rad-hardened). "Only the brain needs protection" is therefore incomplete — see §16.3.
- Can tolerate vacuum if well sealed → reduced need for bulky pressure suits.

### 16.3 Radiation — localized but not trivial (corrected, Rev 8)

The spacecraft/habitat provides bulk shielding, thermal control, and resupply, so those are not body-design problems. But the residual radiation problem is **more involved than "just shield the brain,"** and an earlier draft was over-optimistic here. Three corrections:

**(a) Thicker shielding is not monotonically safer — secondary showers.** Galactic cosmic rays, especially high-charge high-energy (HZE) nuclei, undergo nuclear interactions in shielding material and produce **secondary particles** (spallation neutrons, pions, fragment nuclei). For aluminium, biological dose reaches a *minimum* around ~20 g/cm² and then **rises** with additional thickness, because forward-scattered secondaries outweigh the primaries removed; secondary pions alone can contribute on the order of 10% of dose and are linked to lasting cognitive impairment. **Implication:** use **hydrogen-rich shielding** (polyethylene, water, or the perfusate itself) around the brain, not thick metal — H-rich media produce far fewer secondaries per areal density. The carapace shield must be designed on dose, not thickness.

**(b) The compute layer must be rad-hardened, not just shielded.** BCI front-ends and neuromorphic chips are independently radiation-sensitive (single-event upsets, latch-up), and shielding cannot eliminate single-event effects from the highest-energy particles. They require **rad-hardening by design** — radiation-hard parts, triple-modular redundancy, ECC memory, and active fault detection/scrubbing. Architecture C, which is the most compute-dependent (it emulates autonomic function in silicon), is therefore the **most radiation-exposed** of the three, not the least.

**(c) Residual HZE risk does not vanish.** Even with optimal shielding, some HZE flux penetrates and causes cumulative, permanent damage to neurons and cognition. Shielding *reduces* this; it does not remove it. For multi-year missions this residual is a real contributor to the lifespan/cognition question (§16.6), not a rounding error.

So radiation is *localized* (we protect a ~1.5 L brain plus the compute, not a whole body) but it is **not** a solved "thick wall" problem — it is a dose-optimized, material-specific shield **plus** rad-hardened electronics **plus** an accepted residual.

### 16.4 Closed-loop adaptive perfusion `[USER'S OWN]`

Upgrade from constant-pressure perfusion to demand-responsive perfusion, using sensors already specified (pressure, O₂, glucose, flow) plus a variable pump — the same closed-loop principle used for the hormone system:

- If cerebral perfusion pressure drops, or local O₂/glucose falls below baseline (a sign that region wants more blood), raise pressure/flow to match demand.
- This approximates the brain's natural autoregulation (regions working harder draw more blood).

> **Approximation flag:** true autoregulation is *per-region and simultaneous* (one area up while another is down). Whole-system pressure adjustment raises flow everywhere, not just where needed — close, but not identical. Adequate in practice if region-level precision is not required; flagged as an approximation, not an exact reproduction.

### 16.5 Inline immune filtration `[USER'S OWN]`

The brain, severed from the body, loses systemic immunity, and the perfusate loop is a direct route to the brain. Reuse the existing circulating loop to add an immune-substitute stage: **inline filtration + sterilization (membrane filter, UV, antimicrobial) + reconditioning before return.** This protects against pathogens *in the perfusate*. It does not provide an adaptive immune *response* to pathogens entering by other routes, but with a well-sealed system (the double containment of §14) that residual risk is low and accepted.

### 16.6 Tissue maintenance during infusion — what can and cannot be replaced

The idea of gradually replacing degraded brain tissue with nano-material during infusion is **valid for support tissue and blocked for identity-bearing neurons** — these must not be conflated:

| Can be replaced/repaired `[SPECULATIVE]` but not against principle | Cannot currently be replaced `[SPECULATIVE]`, blocked |
|---|---|
| Support tissue — glia (≈ as numerous as neurons, do not store memory directly), vasculature, blood-brain barrier, meninges | **Identity-storing neurons** — memory/self lives in the *weighted synaptic connectome*, not in individual cells |

Why neuron replacement is blocked: replacing a neuron means reproducing its ~1,000–10,000 synaptic connections at the correct weights and dynamics. We cannot yet read a full connectome (mapping even 1 mm³ of mouse brain takes years and enormous data), and getting it slightly wrong alters the memory/identity stored there. There is also an unresolved Ship-of-Theseus identity question (is a fully nano-replaced brain still the same person, or a copy that believes it is?). **Implication:** the path to longer brain life is keeping the *original* neurons alive longer (→ §7.1 perfusion), not replacing them. Support-tissue upkeep may help; it does not bypass the perfusion bottleneck.

**The neuron-senescence ceiling (Rev 8 — corrects a scope error).** The document elsewhere implied that solving perfusion "unlocks lifespan extension." That conflates two different problems:

- **Acute failure** — the brain dies quickly without blood supply. Perfusion fixes this. (§7.1)
- **Chronic aging** — neurons are **post-mitotic** (they do not divide and are not replaced) and accumulate damage over time: protein aggregation, DNA damage, mitochondrial decline, lipofuscin. Perfusion does **not** stop this.

Because identity-bearing neurons cannot be replaced (above; §9 #16), chronic aging sets a **hard lifespan ceiling that perfusion cannot lift**. Support-tissue upkeep (glia, vasculature) may slow some decline but does not reset neuronal age. Honest framing: this project can plausibly aim to **extend healthy brain lifespan** (defeat acute ischemic death, maintain a clean environment), but "indefinite" lifespan would additionally require defeating neuronal senescence itself — an unsolved biology problem outside this document's scope, and arguably outside any current paradigm. So the project has **two** biological ceilings, not one (§10.2).

### 16.7 Development roadmap

```
Phase 1: Retain the real brainstem  → autonomic + sleep work natively
         (= Architecture A/B, the highest-TRL path)
            ↓
Phase 2: Develop an artificial brainstem in parallel, until validated
            ↓
Phase 3: Transition to the artificial brainstem (→ full Architecture C)
```

This resolves Architecture C's chicken-and-egg problem: start with the real brainstem (deployable now), use the system, and upgrade later — deploy before perfecting. Honest caveat: Phase 2 (artificial brainstem) is a large `[SPECULATIVE]` barrier (the brainstem controls respiration, heart rate, blood pressure, arousal, sleep simultaneously and is not yet fully understood), so Phase 1 may be where the project lives for a long time — and Phase 1 still faces the perfusion bottleneck.

### 16.8 Resolved vs remaining (after this review)

| Item | Status |
|---|---|
| Sensory input | Resolved by scope — actively used body feeds input |
| Sleep / autonomic | Resolved in Phase 1 — retained brainstem |
| Immune (in-loop) | Resolved — inline filtration/sterilization (§16.5) |
| pH / CO₂ buffering | Resolved — sensors + dialysis loop |
| Vascular autoregulation | Resolved (approximation) — closed-loop perfusion (§16.4) |
| Electrode foreign-body | De-risked by design — split-plug (§12); residual is materials science |
| Electrode foreign-body — 2026 materials | Further de-risked — hydrogel electrodes, non-penetrating subdural arrays (Precision Layer 7), fUS non-penetrating reading (§7.2–§7.3); reduced, not eliminated |
| Space environment (thermal, resupply, bulk shielding) | Handled by vehicle |
| Radiation — brain shield | **Not a simple "thick wall"** — needs H-rich, dose-optimized shielding (secondary showers); residual HZE remains (§16.3, §9 #17) |
| Radiation — compute | Must be **rad-hardened by design**, not shielded; Arch C most exposed (§16.3) |
| Support-tissue upkeep | Possibly addressable (§16.6) `[SPECULATIVE]` |
| **Acute: long-term perfusion (6 h → years)** | **Hard blocker #1 — tissue biology (§7.1)** |
| **Chronic: neuron senescence** | **Hard blocker #2 — post-mitotic aging; perfusion cannot lift it (§16.6)** |
| Identity-neuron replacement | Blocked — connectome + identity (§9, #16) |
| Artificial brainstem (Phase 2–3) | Open — large barrier, 50+ yr `[SPECULATIVE]` |
| Expanded sensorium | **Added (§16.9)** — optional upgrade, not a blocker |

**Bottom line (revised):** across many design iterations, the *engineering* problems have been solved or de-risked. What remains is **biology, in two distinct forms**: (1) keeping neural tissue alive long-term (acute — perfusion), and (2) the aging of irreplaceable post-mitotic neurons (chronic — senescence). The first is the gate to making the system work at all; the second caps how far "lifespan extension" can actually go. Radiation is engineering-tractable but more than a thick wall (dose-optimized shielding + rad-hardened compute + accepted residual). The project is engineering-ready almost everywhere — the two places it is not are both tissue biology.

### 16.9 Expanded Sensorium — a real upgrade biological humans cannot have `[HYBRID SYNTHESIS]`

A synthetic body need not merely reproduce the human senses; it can carry a **broad-spectrum sensorium** mapped into the existing nervous system. This is one of the few places the synthetic body is strictly *superior* to biology, not merely equivalent. It is an **optional upgrade, not a requirement** — nothing else in the document depends on it.

**The narrowness is real `[ESTABLISHED]`.** Human senses sample a tiny slice of what physics offers: vision ~380–750 nm, hearing ~20 Hz–20 kHz. Many real, known signals fall entirely outside this band, and other animals already sense them — bee ultraviolet vision, pit-viper infrared (pit organs), bird magnetoreception (Wiltschko & Wiltschko), electric-fish electroreception, bat/dolphin echolocation. The bands exist; humans simply lack the receptors.

**The brain can learn new channels `[ESTABLISHED]`.** Sensory substitution shows the cortex will adopt and interpret novel input streams: Paul Bach-y-Rita (original 1969 *Nature* paper, "Vision substitution by tactile image projection") routed a camera feed to a 20×20 tactile array on the skin and later the tongue (TVSS / BrainPort, commercialized by Wicab, later FDA/EU-cleared), and subjects came to "see" through touch — even experiencing objects as *projected* into external space. David Eagleman's VEST mapped sound to skin vibration ("sensory addition," Novich & Eagleman 2015). The brain is substrate-agnostic about the *carrier* of information, provided the mapping is consistent and learnable — "we see with the brain, not the eyes."

**Application.** Equip the carapace with sensors for bands relevant in space — cosmic-ray flux, stellar/planetary magnetic fields, infrared of cold bodies, radio, ultraviolet — and route them through a substitution interface into the nervous system. Payoff in the operating environment of §16: a directly *felt* radiation field (complementing the dose-management of §16.3), magnetic-field navigation, and thermal sensing of dark/cold objects — none of which a biological crew can have. **Attribution:** the sensory-substitution science is Bach-y-Rita and Eagleman `[ESTABLISHED]`; the specific integration into the synthetic body is the author's application `[USER'S OWN]`.

**Boundary (firewall) `[ESTABLISHED]`.** This adds receivers only for signals that *already exist in known physics*. The electromagnetic spectrum is fully mapped and the four fundamental forces are measured; there is **no "hidden new wave channel"** waiting to be tapped. A genuinely new carrier would be **Type-A new physics** requiring independent evidence — it cannot be inferred from the true-but-irrelevant premise that "our senses are narrow." This is the same firewall that rejected the quark-wave and brain-wave-actuation routes (§9, #1–#2): narrow senses do not imply an undiscovered channel.

---

## Appendix: Concept Provenance Summary

| Concept | Origin | Tag |
|---|---|---|
| Brain perfusion (acellular, cytoprotective) | Vrselja & Sestan et al., 2019 (BrainEx), Yale | `[ESTABLISHED]` |
| Isolated brain/head perfusion (historical) | Brukhonenko 1920s; R. White 1960s–70s | `[ESTABLISHED]` (historical) |
| "Brain in a vat" scenario | Putnam 1981; Harman 1973 | `[THEORETICAL]` |
| Osseointegration | Brånemark, 1950s–60s | `[ESTABLISHED]` |
| Utah array | Normann, 1990s | `[ESTABLISHED]` |
| Mesh / modulus-matched electrodes | Lieber lab, Harvard | `[ESTABLISHED]` |
| Neural dust | Seo, Carmena, Maharbiz et al., UC Berkeley | `[ESTABLISHED]` |
| RPNI | Cederna & Kung, U. Michigan | `[ESTABLISHED]` |
| Bidirectional BCI (sensory feedback) | Gaunt, Collinger et al., Pittsburgh | `[ESTABLISHED]` |
| Artificial CNS bypass for paralysis | Bouton et al., 2016, Battelle/Ohio State | `[ESTABLISHED]` |
| Artificial-synapse reflex + sensation | Kim et al., 2018, Science | `[ESTABLISHED]` |
| Central pattern generators | T. Graham Brown 1911; Grillner | `[ESTABLISHED]` |
| Mauthner-cell escape reflex | Classical neurophysiology | `[ESTABLISHED]` |
| Optogenetics | Boyden & Deisseroth, 2005 | `[ESTABLISHED]` |
| Organoid intelligence (term) | Hartung, Johns Hopkins, 2023 | `[THEORETICAL]` |
| Microtubule consciousness (Orch-OR) | Penrose & Hameroff | `[CONTESTED]` `[MINORITY VIEW]` |
| Neuromorphic compute (Loihi/TrueNorth) | Intel; IBM | `[ESTABLISHED]` |
| Active refrigeration as primary cooling | Standard engineering; design choice by author | `[ESTABLISHED]` tech / `[USER'S OWN]` choice |
| Brain-vessel-only vibration isolation | Author | `[USER'S OWN]` |
| Unified maintenance cycle (no sealed-for-life) | Author | `[USER'S OWN]` |
| Emergency-gated reflex memory store | Author's framing over established CPG + neuromorphic HW | `[HYBRID SYNTHESIS]` |
| Direct-to-synapse / molecular interface | Author's framing | `[USER'S OWN]` `[SPECULATIVE]` |
| Three-tier A/B/C architecture | Author + collaborative structuring in this work | `[HYBRID SYNTHESIS]` |
| Scope: synthetic body for space / lifespan extension | Author | `[USER'S OWN]` |
| Synthetic-body advantages in space (no atrophy/bone loss) | Established space-medicine reasoning | `[ESTABLISHED]` |
| Localized brain radiation shielding in the carapace | Author's framing over established shielding | `[HYBRID SYNTHESIS]` |
| Closed-loop adaptive perfusion (demand-responsive) | Author | `[USER'S OWN]` |
| Inline immune filtration in the perfusate loop | Author | `[USER'S OWN]` |
| Support-tissue (glia/vasculature) upkeep vs neuron replacement | Author's idea, bounded by connectome science | `[HYBRID SYNTHESIS]` |
| Phase 1→3 roadmap (real → artificial brainstem) | Author | `[USER'S OWN]` |
| Hydrogel electrodes for the tissue interface | Li et al., *Advanced Materials* 2026 (review) | `[ESTABLISHED]` |
| Non-penetrating subdural thin-film array | Precision Neuroscience "Layer 7" (1,024-ch, FDA-cleared temporary) | `[ESTABLISHED]` |
| Functional-ultrasound BCI (non-penetrating reading) | fUS-BMI primate demonstrations | `[ESTABLISHED]` |
| Speech-restoration high-bandwidth BCI | Paradromics "Connect-One" (FDA early-feasibility); CorTec Brain Interchange (closed-loop, first-in-human) | `[ESTABLISHED]` |
| GCR secondary-shower limit on shielding; H-rich material | Established radiation-transport physics (consistency check) | `[ESTABLISHED]` |
| Compute must be rad-hardened independently of shielding | Established space-electronics practice (consistency check) | `[ESTABLISHED]` |
| Neuron-senescence lifespan ceiling (acute vs chronic) | Established neurobiology (consistency check) | `[ESTABLISHED]` |
| Sensory substitution (learning a novel input channel) | Bach-y-Rita (TVSS / BrainPort, *Nature* 1969); Eagleman (VEST, "sensory addition") | `[ESTABLISHED]` |
| Broad-spectrum sensorium integrated into a synthetic body | Author's application over established sensory-substitution science | `[USER'S OWN]` / `[HYBRID SYNTHESIS]` |
| "No hidden new wave channel" firewall (known spectrum only) | Established physics (EM spectrum mapped; four forces measured) — consistency check | `[ESTABLISHED]` |
| Cool-first transfer (hypothermia + anesthesia before cutting) | Author's framing over established deep-hypothermia medicine | `[HYBRID SYNTHESIS]` |
| Hours-long ischemia tolerance under hypothermia | Accidental-hypothermia clinical literature | `[ESTABLISHED]` |
| Skull retained as inner vessel | Author | `[USER'S OWN]` |
| Modular plug-and-play neural port (2-layer, sealed) | Author's framing over established couplings/feedthroughs | `[HYBRID SYNTHESIS]` |
| Diving-helmet-style seals (bulkhead, quick-disconnect, hermetic feedthrough) | Established marine/medical/aerospace engineering | `[ESTABLISHED]` |
| Double containment (skull + carapace) | Author | `[USER'S OWN]` |
| Single-fluid hydrogel buffer (damping + thermal mass) | Author's framing over established hydrogel materials | `[HYBRID SYNTHESIS]` |
| Closed-loop cooling through torso heat exchanger | Author | `[USER'S OWN]` |
| Lock operating temperature at 37 °C (not minimized) | Established thermophysiology; corrects an earlier framing | `[ESTABLISHED]` |
| Dual-loop maintenance + backup-perfusion bridge | Author's framing over established ECMO bridge practice | `[HYBRID SYNTHESIS]` |

---

*Document prepared as a design brief. Established science is the foundation; hypotheses are flagged; contested claims are marked; the author's own contributions are identified. Nothing here contradicts established physics or empirical data without being flagged as such.*
