# TensorWave Customer Retention Analysis

> **What this is:** a public-data analysis of why TensorWave wins on memory-per-dollar — and which customers are most likely to churn when Nvidia supply normalizes.

Independent analysis of TensorWave's competitive positioning and customer retention challenges in the AI infrastructure market. Built for the May 2026 Las Vegas AI Builders meetup.

> **v2 is in progress** — rebuilt around workload-capability fit (not pricing) and the June 2026 Series B. See [`tensorwave_v2/`](tensorwave_v2/). v1 (below) remains the pricing/memory-per-dollar foundation.

## Key Findings

1. TensorWave offers 8.6x more memory per dollar than CoreWeave (5.7x vs Lambda Labs)
2. Large-model workloads (70B+) break even in under 3 months versus CoreWeave
3. The advantage is a step function: it appears once a model forces competitors onto extra GPUs while still fitting on one MI300X (70B+)
4. Retention risk is inversely correlated with model size and usage — small, light-usage workloads take longest to recoup migration cost and are the most churn-prone

## Notebooks

- `01_pricing_analysis.ipynb`: GPU price and memory-per-dollar comparison across providers
- `02_breakeven_calculator.ipynb`: ROI/break-even analysis, customer retention quadrant, and a scored churn-risk worklist

Rendered charts are written to `visualizations/` (`pricing_comparison.png`, `breakeven_analysis.png`, `retention_quadrant.png`).

## Methodology & assumptions

- Memory footprint = FP16 weights (`params x 2 bytes`); a conservative floor that ignores KV-cache/activation overhead
- GPUs needed = `ceil(memory / VRAM_per_GPU)`, minimum 1 (capacity-based packing)
- Monthly cost = `GPUs x price_per_hour x wall-clock_hours_per_month`
- Break-even (months) = one-time migration cost / monthly savings; migration cost = engineer-hours x $150/hr
- Memory-per-dollar measures capacity efficiency, not compute throughput

## Data Sources

All data from public pricing pages (May 2026):
- tensorwave.com
- coreweave.com
- lambdalabs.com
- runpod.io

## Built by

Noah Assefa | Ed W. Clark High School | Las Vegas, NV | May 2026
