# GitHub Landscape: Open-Source Longevity Research (2024-2026)

Survey of active open-source projects in aging research, biological age estimation, senescence detection, AI for longevity, and related fields.

---

## 1. Aging Clocks & Biological Age Tools

The fastest-evolving area. Shift from R/elastic-net to Python/deep learning.

### Python ecosystem (newer, growing)

- **[pyaging](https://github.com/rsinghlab/pyaging)** — ~124 stars, updated May 2026. GPU-optimized Python compendium of aging clocks (Horvath, Hannum, PhenoAge, GrimAge, DunedinPACE, etc.). PyTorch-based. **Most comprehensive modern unified framework.**
- **[CpGPT](https://github.com/lcamillo/CpGPT)** — ~72 stars, Dec 2025. **Foundation model (transformer) for DNA methylation.** Pre-trained on millions of CpG profiles. "BERT for methylation." Cutting-edge.
- **[ComputAge](https://github.com/computationalAGINGlab/ComputAge)** — ~36 stars, Jan 2025. Full-stack clock design + ComputAgeBench — only standardized benchmark for comparing clocks on aging-disease datasets.
- **[scAge](https://github.com/alex-trapp/scAge)** — single-cell epigenetic age (Trapp/Gladyshev lab, Harvard). Foundational for single-cell rejuvenation studies.

### R/Bioconductor (classical, well-validated)

- **[methylclock](https://github.com/isglobal-brge/methylclock)** — standard reference, Hannum/Horvath/Zhang/PhenoAge/DNAmTL
- **[methylCIPHER](https://github.com/MorganLevineLab/methylCIPHER)** — from Morgan Levine's Yale lab (PhenoAge co-creator). 30+ CpG clocks
- **[dnaMethyAge](https://github.com/yiluyucheng/dnaMethyAge)** — clean API, broad clock support
- **[EpigeneticPacemaker](https://github.com/NuttyLogic/EpigeneticPacemaker)** — non-linear alternative to elastic-net clocks
- **[EpigeneticAgePipeline](https://github.com/CastellaniLab/EpigeneticAgePipeline)** — end-to-end pipeline, updated 2025

### Curated lists

- **[Aging_clock](https://github.com/mdozmorov/Aging_clock)** — Mikhail Dozmorov's curated index of clock papers, datasets, code

---

## 2. Senescence Detection (Bioinformatics)

A genuine hot area in 2025-2026. Foundation models entering the field.

- **[SenePy](https://github.com/SanbornLab/SenePy)** — single-cell senescence detection, trained on 1.6M cells. Nature Communications 2025
- **[SenSeqNet](https://github.com/HanliJiang13/SenSeqNet)** — deep-learning senescence predictor from protein sequences (Aging Cell 2026)
- **[hUSI](https://github.com/WJPina/HUSI)** — Human Universal Senescence Index, transcriptome-based (Nature Aging 2025)
- **DeepScence** — single-cell/spatial transcriptomics senescence (Cell Genomics 2025)

---

## 3. Telomere Analysis

- **[tidk](https://github.com/tolkit/telomeric-identifier)** — Bioinformatics 2025, Rust, fast
- **[Telomerecat](https://github.com/cancerit/telomerecat)** — WGS-based, Sanger
- **[Teloscope](https://github.com/vgl-hub/teloscope)** — genome assemblies, updated Apr 2026
- **[Telogator2](https://github.com/zstephens/telogator2)** — chromosome-specific & allele-specific length from long reads
- **[TelSeq](https://github.com/zd1/telseq)** — classic WGS telomere length tool

---

## 4. AI/LLM for Aging Research

**The fastest-growing 2025-2026 niche.** LLM agents over aging databases.

### Longevity Genie organization
[github.com/longevity-genie](https://github.com/longevity-genie) — **51 repos**, most active longevity-LLM org on GitHub.

- **just-agents** (80 stars) — minimal agent framework for biomed
- **just-chat** (70 stars) — LLM agent chat
- **opengenes-mcp** — MCP server exposing OpenGenes aging DB to Claude/GPT
- **longevity-forest** — multi-agent system for longevity literature research
- **biotite-mcp**, **edison_mcp** — biomedical MCPs (FutureHouse)

### Other projects

- **[longevity-os](https://github.com/albert-ying/longevity-os)** — "Agentic Longevity OS with 10 AI physicians" — multi-agent personalized health interpretation. Updated March 2026

**Note:** Insilico Medicine's PandaOmics/Chemistry42 are NOT open source. The open-source aging-drug-discovery scene is academic-driven.

---

## 5. Hallmarks Databases & Knowledge Graphs

- **[Open Genes](https://github.com/open-genes)** — open-source DB of human aging/lifespan genes. Includes lifespan-extending interventions, hallmark mappings, age-related changes. Mozilla Public License. Maintained 2024-2025
- **[HALD](https://github.com/zexuwu/hald)** — Human Aging and Longevity Database. Text-mining knowledge graph from PubMed (Scientific Data 2023)
- **[HAGR (Human Ageing Genomic Resources)](https://genomics.senescence.info/)** — GenAge, LongevityMap, CellAge, DrugAge, AnAge. Standard reference
- **[opengenes-mcp](https://github.com/longevity-genie/opengenes-mcp)** — MCP exposing Open Genes for LLM reasoning

---

## 6. Active Organizations on GitHub

| Org | Description |
|---|---|
| [longevity-genie](https://github.com/longevity-genie) | Most active longevity-LLM org (51 repos) |
| [open-genes](https://github.com/open-genes) | Open Genes DB maintainers |
| [open-longevity](https://github.com/open-longevity) | Open Longevity community |
| [longevity-consortium](https://github.com/longevity-consortium) | NIH Longevity Consortium |
| [MorganLevineLab](https://github.com/MorganLevineLab) | Yale, PhenoAge co-creator |
| [vgl-hub](https://github.com/vgl-hub) | Vertebrate Genomes Lab (telomere tools) |

**Notable absence:** Buck Institute, SENS Research Foundation, Methuselah Foundation do not maintain meaningful GitHub orgs.

---

## 7. Quantified Self / Personal Longevity

- **[qs_ledger](https://github.com/markwk/qs_ledger)** — personal data aggregator across wearables, blood tests
- **[awesome-quantified-self](https://github.com/woop/awesome-quantified-self)** — curated list
- **[garmin-grafana](https://github.com/arpanghosh8453/garmin-grafana)** — ~2.5k stars. Garmin → InfluxDB → Grafana for HRV, sleep, VO2max
- **[Gadgetbridge](https://github.com/Freeyourgadget/Gadgetbridge)** — ~4.5k stars. Open wearable replacement (Mi Band, Amazfit, Garmin)
- **[ActivityWatch](https://github.com/ActivityWatch/activitywatch)** — ~16k stars. Time/behavior tracking
- **[longevity-master](https://github.com/banghuazhao/longevity-master)** — iOS habit-tracking for evidence-based longevity. Updated April 2026
- **[youlldie](https://github.com/admbrgd/youlldie)** — R Shiny life expectancy predictor

---

## 8. Notable Individuals to Follow

- **Alex Trapp** (Gladyshev lab) — scAge, single-cell rejuvenation
- **Morgan Levine** (Yale, Altos Labs) — methylCIPHER, PhenoAge
- **Lucas Camillo** — CpGPT (methylation foundation model)
- **Mikhail Dozmorov** (VCU) — curated Aging_clock, methylation tooling
- **Mark Sanborn** (UIC) — SenePy
- **Anton Kulaga / Longevity Genie team** — LLM-for-longevity ecosystem
- **Zach Stephens** — Telogator/Telogator2

---

## Key Trends (2024-2026)

1. **Python is overtaking R** for new aging-clock work (pyaging, CpGPT, ComputAge)
2. **Foundation models for methylation** (CpGPT) and senescence (SenSeqNet, DeepScence) emerged 2025-2026 — real shift from elastic-net clocks to deep learning
3. **LLM agents over aging databases** (Longevity Genie's MCP servers) — fastest-growing niche
4. **Commercial leaders are closed source.** Insilico Medicine, Altos Labs etc. do not publish code — OSS is academic-driven
5. **Real gap:** structured open-source intervention-tracking platforms for individuals. Most personal-longevity tools are closed/SaaS

---

## Implications for Our Project

### Where the field is crowded
- Epigenetic clocks — saturated, multiple high-quality implementations
- Senescence detection — actively being solved
- Personal QS dashboards — many options, mostly fragmented

### Where there are real gaps
1. **Integration / cross-hallmark analysis** — confirmed: no major project maps connections between hallmarks
2. **Open intervention-tracking platforms** — closed-source SaaS dominates
3. **Aging-specific drug discovery (open)** — commercial players are closed; academic OSS is thin
4. **Knowledge graphs combining clinical trials + hallmarks + drug-target interactions** — fragmented
5. **LLM agents specialized for longevity research workflows** — only Longevity Genie is serious here; room for more

### Possible Angles
- **Meta-research / integration layer** — aggregate existing tools (pyaging + SenePy + Open Genes) into a unified workflow
- **LLM-agent built on top of Longevity Genie's MCPs** for hallmark-aware drug-target reasoning
- **Knowledge graph** connecting interventions ↔ hallmarks ↔ trials ↔ biomarkers (none exists in mature form)
- **Personal longevity stack** — open-source intervention tracker grounded in actual hallmark evidence

---

## Aggregator

- **[longevitech.io](https://longevitech.io/)** — curated index of OSS longevity projects across all categories. Good entry point.

---

*Analysis compiled: April 2026. Sources cross-referenced from GitHub topic pages, organization pages, and 2024-2026 publications.*
