# Layer 1 — Workload-Segment Conversion Map

**Master question:** What distinct workload segments does TensorWave serve, on what
evidence, and with what operational characteristics?

Each row is a *workload type*, not a customer type. Every cell traces to a source
in [`SOURCES.md`](SOURCES.md). Confidence and evidence type are marked per row —
they are not uniform.

---

## The five segments

### Row 1 — Frontier MoE serving
Giant frontier Mixture-of-Experts models (DeepSeek V3.2, Kimi K2.6, GLM 5.1) served
in production. MoE = only a few "expert" sub-networks fire per token, but *all*
experts must live in GPU memory — so these workloads are memory-heavy relative to
compute, which is where MI355X's 288 GB helps.

- **Proof point:** Zyphra Cloud, launched May 4 2026 on MI355X via TensorWave.
- **Competitive position:** **Bimodal.** MI355X ~40% cheaper than B200 on GLM-5
  FP8 SGLang at high interactivity (60+ tok/s/user); Nvidia GB300 wins per-dollar
  at lower interactivity (up to 265% cheaper at ~41 tok/s/user). Winner depends on
  the customer app's target tokens-per-second-per-user.
- **Sales motion:** SE-led, deep engineering partnership (custom kernels).
- **Contract:** Multi-year strategic.
- **Deployment friction:** High during integration, lower long-term (integration
  work protects retention).
- **Evidence type:** Customer-validated.
- **Status:** 🟡 Yellow — real named customer, but competitive position is
  operating-point-conditional and Zyphra is AMD-strategically-aligned, so
  repeatability with non-aligned customers is unproven.

### Row 2 — Long-context inference (>128k tokens)
Models processing very long inputs. The binding constraint is the **KV cache**,
which grows with context length and must sit in GPU memory. Memory capacity =
feasible context length.

- **Proof point:** Manifest (TensorWave's own enterprise-inference platform,
  positioned for "larger context windows with reduced latency") + Zyphra's
  long-context emphasis.
- **Competitive position:** **Structural** memory advantage — MI355X 288 GB vs
  B200 192 GB, plus FP8 KV cache via vLLM-ROCm ~halves cache memory. Not
  operating-point-dependent like Row 1.
- **Sales motion:** Mixed — self-serve via Manifest or SE-led for custom algorithms.
- **Contract:** 12–36 mo enterprise.
- **Deployment friction:** Lower — Manifest abstracts ROCm-level work.
- **Evidence type:** Customer-validated + product-validated.
- **Status:** 🟢 Green — structural hardware advantage + productized offering +
  multiple proof points. Strongest cell on the board.

### Row 3 — Inference-platform integrators
Third-party platforms (Fireworks-class) that resell AI serving to many downstream
customers. TensorWave's customer is the *platform*, whose aggregated workload mix
decides whether AMD wins.

- **Proof point:** Fireworks AI, named in the Series B announcement. Partnership
  scope detail is thin in public sources.
- **Competitive position:** **Mixed** — depends on the platform's opaque
  aggregated workload mix.
- **Sales motion:** Executive-sponsored, CEO-to-CEO, often with co-marketing.
- **Contract:** 12–36 mo reserved capacity.
- **Deployment friction:** Low-moderate (platforms know how to onboard capacity).
- **Evidence type:** Customer-validated (existence), inference-heavy (economics).
- **Status:** 🟡 Yellow — real proof point, but win-condition depends on data that
  is opaque from outside. Leverage play: one platform win = many downstream wins.

### Row 4 — Generative video / image inference
Diffusion-model inference (video/image), not text. Different compute pattern,
different success metric (latency-to-completion, not tok/s), different kernel
libraries.

- **Proof point:** Luma AI, named in the Series B announcement.
- **Competitive position:** **Largely unbenchmarked publicly** — InferenceX
  focuses on text LLMs. Memory advantage *should* help diffusion batch inference,
  but no public benchmark confirms it.
- **Sales motion:** SE-led with executive sponsorship.
- **Contract:** Multi-year (inferred).
- **Deployment friction:** Moderate-high (diffusion kernel libraries less mature on
  ROCm than text-LLM).
- **Evidence type:** Customer-validated (existence), inference-heavy (economics).
- **Status:** 🟡 Yellow — growth segment, opaque economics. **Highest-value row to
  verify internally** — TensorWave's own data would firm this to green or red.

### Row 5 — Standard LLM inference (Llama 70B-class, FP8, SGLang)
Bread-and-butter production inference on mature open-weight models via mature
frameworks (vLLM/SGLang) at FP8 precision. Largest customer category by count,
smaller per-customer ARR, huge in aggregate.

- **Proof point:** **No named public customer identified.** Segment inferred from
  the Bare Metal reserved-tier pricing structure (6mo–36mo, $2.29/hr MI355X at
  36mo) built for it, plus public benchmarks (LMSYS/SGLang, AMD MLPerf 6.0)
  confirming competitive economics. Possible Moreh fit — verify.
- **Competitive position:** Strong on FP8 SGLang for specific model classes
  (MI355X 40% cheaper than B200 on GLM-5); ~90–95% of H100 throughput on
  Llama-class per MLPerf.
- **Sales motion:** Self-serve or low-touch SE. **The segment that scales with
  sales headcount.**
- **Contract:** 6–36 mo Bare Metal tiers; strong on-demand → reserved funnel.
- **Deployment friction:** Low — mature stack, minimal porting.
- **Evidence type:** Benchmark-validated + strategically-inferred.
- **Status:** 🟡 Yellow (downgraded from green) — strong technical/pricing case but
  **no customer-side public validation.** Its realness is the single most
  important open question for the Series B thesis (see Layer 3).

---

## Cross-row patterns

1. **Two greens, two reasons.** Row 2 is green on *hardware architecture* (memory);
   Row 5's technical case is strong for a different reason (*framework + pricing
   maturity*). Different GTM motions, even where the case is strong.
2. **Three yellows, three different risks.** Row 1 = operating-point bimodality;
   Row 3 = opaque platform mix; Row 4 = missing benchmarks. "Yellow" is not one
   risk category.
3. **Bimodality is the master insight.** Row 1's finding — AMD wins at high
   interactivity, loses at low — likely generalizes (Row 3's mix, Row 4's variants).
   GTM needs a *qualification framework* keyed to tokens-per-second-per-user, not a
   generic pitch.
4. **The five segments imply the Series B sales playbook.** Self-serve/inbound for
   Row 5; outbound for Row 2; SE-led/executive for Rows 1, 3, 4. Not one playbook —
   at least three.

---

## Two customer types, one thesis

| | Rows 1–4 (strategic) | Row 5 (volume) |
|---|---|---|
| Why customers stay | Technical switching costs | Price advantage |
| Sensitivity to Blackwell ramp | Low | **High** |
| Operational urgency | Steady growth, no clock | **Lock contracts NOW** |
| Sales motion | High-touch, executive, SE-led | Scalable, self-serve → reserved |
| Series B investment | SE bench, deal orchestration | Sales headcount, funnel automation |

This split is the spine of the whole v2. Layer 2 develops the funnel side; Layer 3
develops the finance implications.
