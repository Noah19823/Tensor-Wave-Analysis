# Layer 2 — On-Demand → Reserved Conversion Funnel

**Master question:** For the segments TensorWave wins, how do customers journey from
trial to locked-in reserved revenue, and where do they get stuck?

**Why it matters (revenue quality):** Reserved revenue is contracted, predictable,
and investor-multiple-maximizing; on-demand revenue is churnable and discounted in
DCF/valuation terms. At a $1.55B Series B valuation, converting a customer from
on-demand to 36-month reserved doesn't just extend a contract — it moves dollars
from low-multiple uncertain revenue to high-multiple contracted revenue. It also
underwrites the 2 GW capacity commitment. **This is the highest-leverage
operational lever TensorWave has in the pricing window.**

---

## The five funnel stages

| Stage | What it is | Revenue quality |
|---|---|---|
| 0 · Benchmark / Trial | Evaluating vs alternatives; short pilots, often credited | ~zero |
| 1 · On-Demand Burst | Production workloads on hourly pricing, no reservation | Low (churnable) |
| 2 · 6-Month Reserved | Short commit for a meaningful discount | Medium |
| 3 · 12-Month Reserved | A year committed, deeper discount | High |
| 4 · 36-Month Reserved | Full multi-year commitment ($2.29/hr MI355X anchor) | Very high |

---

## Segment → funnel-position mapping

| Layer 1 segment | Natural entry stage | Why |
|---|---|---|
| Row 1 — Frontier MoE | **Skips to Stage 3–4** | Multi-year strategic from day one; deep partnerships don't run at on-demand timescales |
| Row 2 — Long-context | **Stages 2–4** | Manifest platform commitments carry switching cost |
| Row 3 — Platforms | **Stage 3–4 + co-marketing** | Platforms lock capacity for their downstream unit economics |
| Row 4 — Generative media | **Stage 3–4 (inferred)** | Predictable capacity needs + custom-kernel switching cost |
| Row 5 — Standard LLM | **Full funnel, Stage 0 → 4** | The only segment that evaluates on-demand then converts to reserved |

### The sharp finding

> **Four of five segments never traverse the funnel — they enter at the commit
> stage as strategic deals. Only Row 5 (standard LLM inference) travels the full
> funnel.** So the on-demand → reserved funnel is not a generic customer journey —
> it is specifically the Row 5 playbook. Rows 1–4 require their own non-funnel deal
> motions.

*(Caveat: this finding rests on Row 5 being a real, populated segment — which is
itself an open question, since Row 5 has no named public customer. See
[`OPEN_QUESTIONS.md`](OPEN_QUESTIONS.md).)*

---

## Barriers by transition

- **Stage 0 → 1 (Benchmark → On-Demand):** customer didn't see compelling enough
  cost/perf, or benchmarking lost momentum. Competitor CoreWeave's **ARENA** program
  attacks exactly this by letting customers benchmark production-scale pre-commit.
  TensorWave has no equivalent productized benchmarking tool publicly — likely a
  Series B investment area.
- **Stage 1 → 2 (On-Demand → 6mo):** customer hasn't seen stable enough workload to
  commit. Lever: show them their own usage data + no-brainer savings math; flexible
  expansion clause for high-growth startups.
- **Stage 2 → 3 (6mo → 12mo):** discount delta must justify doubling the lock-in.
  Competitive comparison sharpens because 12 months reaches into the Blackwell-ramp
  horizon.
- **Stage 3 → 4 (12mo → 36mo) — the critical conversion:** 3 years feels long in AI.
  Barriers: hardware obsolescence (MI400 ramps 2026), AMD longevity concern, lock-in
  fear. Levers (FP&A/contract-design owned): generation-upgrade clauses, capacity
  flexibility, possible competitive-parity repricing triggers. The $2.29/hr 36-mo
  MI355X anchor is deliberately aggressive — TensorWave pays margin to buy
  higher-quality revenue.

---

## Strategic implications

1. **The funnel investment is not one thing.** Split the Series B "sales motion"
   budget into (a) *funnel automation for Row 5* (benchmarking tool, self-serve
   reserved sign-up, usage analytics) and (b) *strategic deal orchestration for
   Rows 1–4* (SE bench, executive-deal support, custom contracts).
2. **The 12 → 36 month conversion is the single highest-leverage transition** —
   because of Blackwell timing. Every Row 5 customer locked into 36-month reserved
   *before mid-2027* is locked past the normalization event.
3. **The CoreWeave ARENA gap is operationally meaningful** for Row 5 specifically.
   A productized TensorWave benchmarking equivalent is a probable high-ROI Series B
   investment (developed further in Layer 4).

---

## Landing sentence

*The on-demand → reserved funnel is the Row 5 playbook; Rows 1–4 enter at the
commit stage through strategic deal motions. So the Series B "sales motion"
investment should split into two programs — funnel automation for Row 5, strategic
deal orchestration for everything else — and the 12 → 36 month conversion is the
highest-leverage transition because it locks customers past the Blackwell ramp.*
