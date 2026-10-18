# EcoScope: 1st Prize, ZEISS Energy Smart AI Challenge

**Re_Make Hackathon 2026 · Das Habitat Augsburg · April 20–21, 2026 · 🏆 Winning team**

Microscope workstations in research labs use a lot of energy, and a surprising share of it is wasted: live view left running when nobody is watching, scans repeated when an earlier result could be reused, machines sitting idle at full power after an experiment ends. ZEISS asked hackathon teams to find that waste in real workflow data and suggest fixes, without making the science slower or worse.

Our team of four built **EcoScope** in two days, and it won first place.

**[→ Try the live demo](https://ecoscope-five.vercel.app/)** · **[Prototype & pitch notes](https://rural-rudbeckia-0ce.notion.site/EcoScope-ZEISS-3652159900248002b042e08e747fedef)** · **[Source code (Tooba's repo)](https://github.com/toobahasnain/ecoscope)**

---

## What EcoScope does

A scientist uploads the telemetry from a microscope session. EcoScope splits it into workflow phases (tile scan, live view, processing, idle), compares each phase with what an efficient run looks like, and flags anything that uses more than it should. Then it explains, in plain language, what to change.

- **Phase-by-phase analysis** of power, GPU use and user interaction
- **AI recommendations** written by Google Gemini, each linked to a circular-economy "R-strategy" (Rethink, Reduce, Reuse)
- **Baseline vs improved** comparison showing the energy saved
- **What-if simulator** with sliders to test savings live
- **Energy labels** from A++ to G, like EU appliance labels
- **A chatbot** for asking questions about the workflow data

## Why rule-based + LLM, not a black-box model

With two days and ten training scenarios, a trained ML model would have been hard to trust and impossible to explain to lab staff. So we split the job:

1. **The rules do the measuring.** From scenarios S1–S10 we took the most efficient half of the runs for each phase and used them as the reference. A phase more than 20% above that reference gets flagged.
2. **The LLM does the explaining.** Gemini only receives anonymised numbers (phase name, average power, deviation), never the raw lab data, and turns them into recommendations people can act on.

That made the results explainable, kept research data private, and let us check accuracy against ground-truth labels. We demonstrated it live on a held-out test scenario the system had never seen.

## My role

I led the product side of the project:

- **Defined the problem** with the team: where the energy waste actually comes from, and who needs to act on it
- **Scoped the MVP** and wrote the user stories
- **Took the product from research to requirements to a UX/UI prototype** in Figma
- **Built the pitch deck** and presented the **live demo** to the ZEISS judges
- **Coordinated the team of four** under hackathon time pressure, keeping the build, the story and the demo on track together

## Team and credit

EcoScope was a team effort. The application code was written by **[Syeda Tooba Hasnain](https://github.com/toobahasnain)**, and the full source is in her repository: **[toobahasnain/ecoscope](https://github.com/toobahasnain/ecoscope)**. This page is my write-up of the project and my part in it.

## Built with

Next.js · TypeScript · Google Gemini API · PapaParse · Recharts · Vercel · Figma (prototype)

## What I took away from it

- In a short build, **explainability beats cleverness**. Judges, like future users, trusted results they could follow.
- **Privacy can be designed in from the start.** Sending only aggregated metrics to the LLM made the tool realistic for actual lab use.
- A clear story matters as much as the code. The demo and the pitch were planned around one question: *how much energy does this save, and what should the scientist do next?*

---

**Rafia Imran** · AI product development · Munich / remote
[GitHub profile](https://github.com/rafiasimran) · [Live CV](https://rafiaimran.cloud) · imranrafia25789@gmail.com
