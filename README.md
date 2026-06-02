# Energy-Efficient Multi-Modal LLM Serving
### A Sub-phase Characterization Study

A phase-level characterization of multimodal LLM inference (**InternVL3-8B**) on an NVIDIA A100, profiling
where time, compute, power, and energy actually go across the four inference phases — and what that means for
energy-efficient serving.

🔗 **Project page:** https://mllm-energy.github.io/MLLM-Energy/
📄 **Paper:** [`paper.pdf`](paper.pdf)

## TL;DR

- **Decode dominates** wall-clock time (88.7% of a request) while sustaining only **14% SM** and **23% DRAM**
  throughput — the slowest phase wastes the most hardware.
- **Throughput and power both saturate at SM ≈ 36.** Output-heavy work gains under 9% from the remaining 67% of
  the GPU, and power plateaus at **~230 W — below the A100's 250 W TDP**, so single-job SM masking can't reclaim
  the stranded capacity.
- **Batching is asymmetric:** a strong energy lever for output-heavy workloads (**12.9×**) but weak for
  input-heavy ones (**1.9×**), because the vision encoder's fixed cost never amortizes across a batch.

## Repository contents

| Path | Description |
|------|-------------|
| `index.html` | The interactive project page (served via GitHub Pages) |
| `paper.pdf` | The full paper |
| `paper/` | LaTeX source — `main.tex`, `refs.bib`, `figs/` |
| `figs/` | Figures used by the project page |

## Authors

Aashrith Attelli · Amaury Jayr · Nathan Lemma · Mahin Naveen
— The University of Texas at Austin, Spring 2026
