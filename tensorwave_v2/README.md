# TensorWave Customer Retention Analysis — v2

**Workload-Segment Conversion Map**
Independent analysis · Noah Assefa · June 2026

---

## Purpose

This is v2 of an independent customer-retention analysis of TensorWave, rebuilt
after v1 feedback and the June 2026 Series B.

- **v1** framed retention around pricing (memory-per-dollar advantage vs
  Nvidia-based competitors).
- **Feedback received:** retention is less about price and more about whether a
  customer's *specific workload* performs on the hardware.
- **v2** reframes the analysis around **workload-capability fit**, keyed to
  TensorWave's post-Series-B operating state.

Every claim traces to a public source (see `SOURCES.md`). This synthesis draws on
individually-published material (SemiAnalysis InferenceX, TensorWave's own posts,
SEC filings of comparable NeoClouds, AMD/ROCm technical docs). The integration
into a workload-segment conversion map keyed to TensorWave's post-Series-B state
is, to my knowledge, not duplicative of publicly available analyses, though it may
overlap with internal TensorWave thinking. **Offered for collaborative markup, not
as a finished analytical claim.**

---

## What changed since v1

1. **Series B closed June 10, 2026** — $350M at $1.55B valuation, co-led by
   Magnetar and AMD Ventures. Plans: expand to ~2 GW long-term capacity, roughly
   double headcount (~160 → 300–400) over 12 months, including sales and CS.
2. **New named customer wins are public** — Zyphra, Fireworks AI, Luma AI, Moreh —
   each a distinct workload segment with a distinct conversion path.
3. **Competitive economics are confirmed workload-specific** — SemiAnalysis
   InferenceX shows MI355X vs Nvidia GB300/B200 depends on model, precision, and
   interactivity operating point. Not a generic "AMD wins" story.

These shift the GTM problem from *"prove the AMD thesis"* to *"convert workload-fit
wins into reserved-capacity revenue at the rate the doubling headcount can
sustain."*

---

## v2 Thesis

> TensorWave has two structurally distinct customer-retention drivers. **Technical
> switching costs** lock in the strategic segments (frontier MoE, long-context,
> platforms, generative media) regardless of Nvidia pricing. **Pricing advantage**
> is the only thing holding the standard-LLM-inference segment — which is
> price-sensitive and mobile once Nvidia's Blackwell supply normalizes. The Series
> B should fund two different operational programs in parallel: funnel automation
> for the price-sensitive segment, and solutions-engineering + strategic-deal
> orchestration for the technically-locked segments. They look like one
> "sales-motion" budget line but they are not the same investment.

**One-sentence pitch:**
*Banks aside — for a GPU cloud, retention isn't price, it's whether the customer's
specific models run well on the chip. I mapped TensorWave's customer base into five
workload segments, tied each to a named customer and the InferenceX competitive
data, and the sharpest finding is that four of five segments never touch the
on-demand → reserved funnel — only standard LLM inference does — which changes how
the doubled sales headcount should be deployed.*

---

## The five layers

| Layer | Question it answers | Lens | Status |
|---|---|---|---|
| 1 | Which workload segments does TensorWave win, and on what evidence? | Customer segmentation | ✅ Built |
| 2 | How do customers journey from trial to locked-in revenue? | Sales motion + revenue quality | 🛠 Drafted |
| 3 | What does the Series B math require, per rep, per segment? | Strategic finance | 🔜 Planned |
| 4 | How does onramp friction compare to competitors? | Competitive benchmarking | 🔜 Planned |
| 5 | Given the training→inference shift, what should TensorWave do? | Macro synthesis | 🔜 Planned |

- **Layer 1** defines the segment vocabulary every other layer uses.
- **Layers 2–4** are parallel applications of Layer 1 (funnel, finance, competitive).
- **Layer 5** synthesizes everything into a sequenced recommendation.

See:
- [`layer1_workload_segment_map.md`](layer1_workload_segment_map.md)
- [`layer2_conversion_funnel.md`](layer2_conversion_funnel.md)
- [`SOURCES.md`](SOURCES.md)
- [`OPEN_QUESTIONS.md`](OPEN_QUESTIONS.md) — cells flagged for internal verification

---

## Methodology notes

- **Evidence types are marked, not uniform.** Some rows are *customer-validated*
  (named public customer), some *benchmark-validated* (public benchmarks confirm
  competitive economics but customer-side validation is thinner), some
  *strategically-inferred* (product/pricing structure implies the segment exists).
  All are legitimate but they do not carry equal weight.
- **Inferences are flagged explicitly** in `OPEN_QUESTIONS.md` so the team can
  confirm or correct rather than excavate.
- **No internal TensorWave information is used or claimed.**
