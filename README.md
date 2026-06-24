# Synthetic Body Architecture

**A comparative design brief for housing a living human brain in a synthetic body — for lifespan extension and space exploration.**
Grounded in 2026 technology and active laboratory research.

Author: **Pitarn Rungsiyapornratana** · ORCID [0009-0004-6411-2201](https://orcid.org/0009-0004-6411-2201)
Current version: **V1.2** · License: **CC-BY-4.0** (see `LICENSE`)

---

## What this is

An engineering design brief comparing three architectures for keeping a real, biological human brain alive and active inside a synthetic body. It is a **speculative-but-grounded** document: established science is the load-bearing spine; every non-trivial claim carries an epistemic tag; nothing that contradicts physics or measured data is asserted without being flagged.

It is **not** a brain-in-a-jar concept. The brain is *embodied and actively used* — the body feeds it sensory input, and (in the near-term path) a retained brainstem drives sleep and autonomic function.

## The three architectures

- **A — Conservative:** brain + brainstem + full spinal cord; peripheral-nerve interfaces; highest technology-readiness, largest life-support.
- **B — Balanced:** brain + brainstem; spinal cord removed; BCI + neuromorphic reflex bypass.
- **C — Aggressive:** brain only in a perfusion vessel; everything via BCI; autonomic function emulated — the largest technology gap.

A **Phase 1 → 3 roadmap** starts with a real brainstem (A/B) and develops an artificial brainstem in parallel before any transition to C.

## Core finding (honest bottom line)

The *engineering* problems are largely solved or de-risked. What remains is **biology, in two distinct forms**:

1. **Acute — long-term brain perfusion.** BrainEx (Vrselja & Sestan, *Nature* 2019) sustains an isolated brain for ~6 hours; a real system needs years. This cannot be engineered around — it must be solved at the tissue level.
2. **Chronic — neuron senescence.** Even with perfect perfusion, post-mitotic neurons age, and identity-bearing neurons cannot be replaced (connectome + identity wall). This caps lifespan independently of perfusion.

Radiation is engineering-tractable but more than a thick wall: it needs hydrogen-rich, dose-optimized shielding (cosmic-ray secondary showers) plus independently rad-hardened compute.

## How to read

- `synthetic_body_design_V1.2.pdf` — rendered, with color-coded epistemic tags. **Start here.**
- `synthetic_body_design_V1.2.md` — Markdown source (single source of truth).
- `synthetic_body_design_V1.2.docx` — Word version.

## Epistemic tag legend

| Tag | Meaning |
|---|---|
| `[ESTABLISHED]` | Tested / peer-reviewed; in clinical or engineering use today |
| `[THEORETICAL]` | Plausible basis, not yet experimentally confirmed |
| `[CONTESTED]` | Actively debated; no scientific consensus |
| `[MINORITY VIEW]` | Held by a small fraction of the relevant field |
| `[HYBRID SYNTHESIS]` | Combines or adapts existing ideas from named sources |
| `[SPECULATIVE]` | Beyond current science; needs a paradigm not yet in hand |
| `[USER'S OWN]` | A design decision or framing originated by the author |

## Attribution policy

Established science is credited to its originators by name (e.g. BrainEx — Vrselja & Sestan; sensory substitution — Bach-y-Rita, Eagleman; osseointegration — Brånemark; RPNI — Cederna & Kung). Recombinations of prior work are marked `[HYBRID SYNTHESIS]`. The author's name is attached **only** to genuine originations and design decisions. The full provenance table is in the Appendix of the document.

## Decision log

§9 records both **why each chosen path was chosen** (Adopted paths table) and **why each alternative was cut** (Rejected & superseded options, 18 entries) — so settled questions are not re-litigated.

## Citing

See `CITATION.cff`. Version history is in `CHANGELOG.md`.

## Status

This is an independent theoretical/engineering brief, not a peer-reviewed publication or a buildable specification. It is shared for discussion and critique.
