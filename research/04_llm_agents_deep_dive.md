# Deep Dive: LLM Agents for Longevity

Critical analysis of the two leading open-source LLM-agent projects in the longevity space: **Longevity Genie** and **longevity-os**. Both are interesting — both are smaller than they look.

---

## Project 1: Longevity Genie

**URL:** https://github.com/longevity-genie · 51 repos · 58 followers · 2 public members

### The team (the real story)

The "organization" is effectively **2 core developers + 2 part-time contributors**:
- **Anton Kulaga** — lead. Bioinformatician at Institute of Biochemistry, Romanian Academy. Co-founder of International Longevity Alliance. ARDD 2023 speaker ("Longevity GPT"). Funded as VitaDAO project.
- **Newton Winter** (`winternewt`) — co-maintainer of the agent stack
- Alex Karmazin, Livia Zaharia — occasional contributors

Supporting affiliations claimed: HEALES, IBIMA, Systems Biology of Aging Group (Bucharest).

### What they've actually built

#### Agent framework: just-agents
[github.com/longevity-genie/just-agents](https://github.com/longevity-genie/just-agents) — **80 stars, Apache-2.0, actively maintained (last push 2025-11-22)**

- Lightweight LLM-agent library on top of `litellm`
- Four agent types: `BaseAgent`, `ChatAgent`, `ChainOfThoughtAgent`, `WebAgent` (FastAPI/OpenAI-compatible REST)
- YAML-based prompts, separated from Python
- Positioned as anti-LangChain: "no over-engineering"
- Real engineering: CI, Docker, PyPI, multi-version support, MCP-tool consumption added Oct 2025

**Verdict: the most legitimate piece of infrastructure in the org. Small but credible.**

#### Reference chat app: just-chat
[github.com/longevity-genie/just-chat](https://github.com/longevity-genie/just-chat) — 70 stars, last push 2025-11-22

Docker-compose deployable chat on top of just-agents: Python backend (8091), web UI (3000), MongoDB for history, MeiliSearch for markdown RAG, optional Langfuse. No hosted demo. Usable reference, not a product.

#### Bio MCP server catalog — 15+ servers
This is the genuine asset of the org. They've wrapped multiple aging-specific databases as MCP servers:

| MCP Server | Stars | What it wraps |
|---|---|---|
| `biothings-mcp` | 31 | mygene.info, myvariant.info, mychem.info |
| `gget-mcp` | 27 | Pachter Lab's gget (BLAST, ARCHS4, Enrichr, AlphaFold, etc.) |
| `holy-bio-mcp` | 18 | **Meta-aggregator (won Bio×AI Hackathon 2025, $10K)** |
| `opengenes-mcp` | 17 | OpenGenes DB (genes ↔ aging ↔ hallmarks) |
| `synergy-age-mcp` | 10 | SynergyAge (genetic interactions × lifespan) |
| `pharmacology-mcp` | 6 | IUPHAR pharmacology DB |
| `addgene-mcp` | 6 | Addgene plasmid repository |
| `benchling-mcp` | 5 | Benchling lab platform |
| `edison_mcp` | 5 | **FutureHouse / Edison Scientific API wrapper** |
| `biotite-mcp` | 3 | biotite structural bio library |
| `cellxgene-mcp` | 3 | CellxGene single-cell DB |
| `alphagenome-mcp` | 2 | DeepMind AlphaGenome |
| `atomica-mcp` | 1 | — |
| `boltz-mcp` | 0 | Boltz-2 structure model |
| `chembl-mcp` | 0 | ChEMBL |
| `pydna-mcp` | 0 | pydna |

**For an MCP-curious longevity researcher, this is the most aging-specific catalog on GitHub.**

#### Orchestrator: longevity-forest
[github.com/longevity-genie/longevity-forest](https://github.com/longevity-genie/longevity-forest) — **2 stars, created 2025-11-16, all 5 commits by Anton alone**

A Query Agent over 7 sub-agents (Google, PubMed/EuropePMC, AlphaFold/PDB/InterPro, BioMART, OpenGenes, OmniPath, GPU MCPs). Single-author scaffolding, very new, no traction. README claims "production-ready" — it's a prototype.

### Downstream usage

- PyPI: `gget-mcp` only 76 last-week / 445 last-month downloads
- Dependents graph: basically only internal repos
- **No meaningful external adoption.** The user base is the team + a handful of researchers.

### What's hype vs. real

**Real:**
- just-agents is a clean alternative to LangChain
- 15+ niche aging-DB MCPs nobody else has wrapped
- Holy Bio MCP won Bio×AI Hackathon 2025 (legitimate recognition)
- Anton Kulaga is a real researcher with longevity-community standing

**Overstated:**
- "Multi-agent system" longevity-forest is a 1-week-old, single-author, 2-star prototype
- Most data-MCPs are 3-15 commits by Anton alone, no second reviewer
- Several READMEs explicitly say "not manually verified," "beta," "WIP"
- No published QA accuracy benchmarks vs. FutureHouse/Elicit
- No hosted product, no demo, longevity-genie.info dormant
- `mcp-judge` (evaluation harness) is mostly empty

### Comparison to bigger players

- **FutureHouse** (Crow, Falcon, Owl, Phoenix) — hosted, benchmark-validated, Eric Schmidt-backed. Longevity Genie's `edison_mcp` actually **calls FutureHouse's API** — they consume it, not compete with it.
- vs. Elicit, Scite, OpenBioML — Longevity Genie offers **no novel reasoning or retrieval algorithm**. Differentiator: **breadth of niche aging databases** they connect to.

---

## Project 2: longevity-os

**URL:** https://github.com/albert-ying/longevity-os · 14 stars · created 2026-03-12 · all 9 commits on a single day

### Who built it

**Kejun (Albert) Ying** — Postdoc at IPD (Baker lab, UW) and Stanford Wyss-Coray lab. Formerly Harvard. **Serious aging-biology researcher (Sinclair/Wyss-Coray lineage)**, not a marketer. That materially changes the credibility read — but it doesn't change that this is a weekend prototype.

### What "10 AI physicians" actually is

9 markdown system prompts + 1 orchestrator, **all running on Claude**:

| Agent | Theme (Chinese) | Specialty |
|---|---|---|
| `SKILL.md` 御医 | Imperial Physician | Router / orchestrator |
| `shiyi.md` 食医 | Diet | Meal logging, nutrition |
| `daoyin.md` 导引 | Movement | Workout tracking |
| `zhenmai.md` 诊脉 | Pulse Reader | Weight, BP, sleep, HRV |
| `yanfang.md` 验方 | Formula Tester | Lab biomarkers |
| `bencao.md` 本草 | Herbalist | Supplements |
| `baogao.md` 报告 | Court Scribe | Reports + PubMed |
| `shixiao.md` 试效 | Trial Monitor | Pattern detection |
| `yuanpan.md` 院判 | Court Magistrate | Trial design + PubMed |
| `yizheng.md` 医正 | Medical Censor | Adversarial safety review |

The router classifies intent (`log_diet | log_exercise | query | trial_propose | …`) and dispatches to specialist prompts in parallel. Trial creation uses **adversarial review loop**: pattern → propose → critique → max 3 cycles → user approval.

**Branding:** 太医院 = Imperial Medical Academy. Marketing flavor — but the agent decomposition is well thought through.

### Tech stack

- **LLM**: Anthropic Claude (via Claude Code / OpenClaw). **Locked to Claude — no OpenAI/Gemini path.**
- **Storage**: SQLite (WAL, 0600 perms), 15KB schema
- **Stats**: real Kalman filter (BSTS) + RTS smoother + OLS interrupted time series + Mann-Whitney confounder checks. **Bayesian label overstates it** — no priors, no posterior sampling. Honest N-of-1 stats, not CausalImpact-grade.
- **Dashboard**: single-file Chart.js HTML (78KB), bilingual EN/CN, Python stdlib server
- **MCP tools**: PubMed, bioRxiv, USDA FoodData, Open Food Facts, NIH ODS

### Privacy posture (strongest part)

- SQLite with `0600` perms
- No cloud, no accounts
- Dashboard binds to `127.0.0.1`
- Nutrition lookups send ingredient names only, never health data

### What's reusable

- **Agent decomposition pattern** (router + 9 specialists + adversarial review) — well-thought-out, liftable
- **SQLite schema** for personal longevity tracking
- **Apple Health + lab importers** (39KB combined)
- **Single-file Chart.js dashboard** as reference

### What's missing

- No tests, no CI, no license, no requirements pinning
- Hardcoded `/Users/A.Y/...` paths
- No medical disclaimers despite "clinical-grade" framing
- No multi-user, no encryption at rest beyond filesystem
- No wearable integration beyond Apple Health
- **All commits on a single day (2026-03-12), 0 since.** Looks like a showcase weekend project.
- Locked to Claude — not portable
- **Ironic absence**: Albert's actual research area is epigenetic age clocks — not implemented here

### Verdict

Serious researcher's weekend prototype with thoughtful architecture and honest stats under imperial-court branding. **Worth reading for design ideas; not worth forking as a base** unless committed to Claude + local-only single-user.

---

## The Real Gaps (Where a New Project Could Add Value)

Both projects are real and useful — and both leave large open spaces.

### Infrastructure-level gaps

1. **Evaluation / benchmarks.** Nobody has published rigorous QA accuracy on aging questions vs. ground truth. No "GPQA for biogerontology." `mcp-judge` is empty.
2. **A working hosted product.** No `chat.longevity-genie.com`. Dormant blog. Hosted multi-agent UI over these MCPs is wide open.
3. **Entity resolution / grounding.** biothings-mcp explicitly flags LLM-name-ambiguity as known weakness. A dedicated bio-entity resolver (gene symbol → Ensembl + variant + ortholog) would slot in directly.
4. **Cross-MCP planning and cost control.** longevity-forest is too thin. A real planner with budgets, caching, citation deduplication across 15+ MCPs is missing.
5. **Production-grade reliability.** Single-maintainer repos with no live-DB tests are fragile. A QA harness running nightly against upstream APIs doesn't exist.

### Data-layer gaps

6. **Aging-specific datasets not in OpenGenes / SynergyAge:**
   - Clinical trials of geroscience interventions
   - Longitudinal biomarker datasets
   - AgingAtlas
   - GenAge expansions
   - None of these are wrapped as MCPs.

### Personal/product-layer gaps

7. **Real causal inference for N-of-1** — PyMC/Stan BSTS, proper CausalImpact, MLE-fit state-space
8. **Model-agnostic runtime** — neither project is portable
9. **Wearable breadth** — Oura, Whoop, Garmin, Dexcom CGM (none integrated)
10. **Multi-user + sync with E2EE** — killer missing piece for any real product
11. **Clinically validated biomarker engines** integrated with personal tracking — epigenetic age, GlycanAge, etc.
12. **Hallmark-aware reasoning** — neither project structures its knowledge around the 12 hallmarks; everything is flat database access

---

## Strategic Implications

### What this means for our project

The LLM-agent-for-longevity niche is **real and underdeveloped** — confirmed. But the leading projects are:
- **Longevity Genie:** strong on data plumbing (MCP catalog), weak on reasoning, evaluation, and product
- **longevity-os:** strong on UX pattern (agent decomposition, dashboard), weak on rigor, stalled

A new project could plausibly own one of these positions:

#### Position A — "The evaluated reasoning layer"
Build a benchmarked, hallmark-aware reasoning agent **on top of** Longevity Genie's MCP catalog. Not duplicate plumbing. Focus on: evaluation suite, citation-grounded answers, cross-MCP planning, hallmark-aware decomposition.

#### Position B — "The integrated personal longevity stack"
Take longevity-os's agent pattern, make it production-grade: multi-LLM, wearable breadth, real causal inference, biomarker integration, E2EE multi-user. This is closer to a product/startup play than research.

#### Position C — "The knowledge graph nobody built"
Structured KG connecting: interventions ↔ hallmarks ↔ trials ↔ biomarkers ↔ genes. Currently fragmented across Open Genes, SynergyAge, HAGR, clinical trial DBs. Could feed both reasoning agents and personal trackers.

#### Position D — "Hallmark-aware MCPs nobody made"
Build the missing MCPs: clinical trials of geroscience interventions, longitudinal biomarker datasets, hallmark-mapped intervention DB. Directly complement Longevity Genie rather than compete.

---

## Key URLs

**Longevity Genie:**
- Org: https://github.com/longevity-genie
- just-agents: https://github.com/longevity-genie/just-agents
- opengenes-mcp: https://github.com/longevity-genie/opengenes-mcp
- holy-bio-mcp: https://github.com/longevity-genie/holy-bio-mcp
- Anton Kulaga: https://github.com/antonkulaga

**longevity-os:**
- Repo: https://github.com/albert-ying/longevity-os
- Albert Ying: https://kejunying.com

**Comparable platforms:**
- FutureHouse (hosted, benchmark-validated): https://platform.futurehouse.org
- VitaDAO funded projects: https://www.vitadao.com/projects/longevity-genie

---

*Analysis compiled: April 2026. Based on direct repo inspection and public profiles.*
