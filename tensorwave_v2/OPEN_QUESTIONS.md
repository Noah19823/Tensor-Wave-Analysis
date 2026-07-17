# Open Questions — Cells Flagged for Internal Verification

These are inferences drawn from public data. They are flagged explicitly so the
TensorWave team can confirm or correct rather than excavate. Bringing these as a
working draft — not a finished claim — is the point.

## Highest priority

1. **Is Row 5 (Standard LLM Inference) a real, populated segment?**
   No named public customer identified. Inferred from Bare Metal reserved-tier
   pricing + benchmarks. This is the most important question in the analysis: the
   Series B headcount/quota math (Layer 3) depends on the answer.
   - If populated → funnel automation is the top Series B investment.
   - If not populated → the 200 new hires are *creating* the segment, not scaling
     it — a different sales motion, ramp time, and burn profile.

2. **Row 4 (Generative media / Luma): what are the real economics?**
   Public benchmarks don't cover diffusion-model inference on MI355X vs B200. Does
   TensorWave's internal data on Luma's workload show favorable per-output
   economics? Is there a pipeline of similar customers (Runway, Pika), or is Luma a
   one-off?

3. **Row 3 (Fireworks): what % of their downstream traffic runs on TensorWave, and
   which model classes?** The win-condition depends on Fireworks's aggregated
   workload mix, which is opaque from outside.

## Secondary

4. **Is Moreh a Row 5 customer or a Row 1 (frontier) customer?** The "frontier LLM
   inference" language could go either way. If Row 5, it partially firms up that
   segment.

5. **Does the bimodal (Row 1) finding generalize beyond GLM-5 / FP8 / SGLang?** The
   mechanism (AMD wins at high interactivity) should generalize, but the exact
   crossover point is workload-specific.

6. **Contract structure reality:** are the Bare Metal reserved tiers visibly booked
   with customers, or is that newly-raised capacity not yet filled?

## Financial-inference questions (for Layer 3, verify with Strategic Finance)

7. Implied ARR target from valuation math (15–25x AI-infra multiple → $60–100M+):
   is that in the right range?

8. Implied per-rep quota at ~70–80 reps ($1–2M ARR/rep): consistent with internal
   targets?

9. Does the financial thesis actually require Row 5 to be the scaling segment, or
   are strategic-deal sizes larger than public comps suggest?

10. Current customer-mix split across training vs inference (for Layer 5 exposure
    analysis)?
