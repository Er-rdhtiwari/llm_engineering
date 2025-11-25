
# Interview Prep Map – llm_engineering

## How to use this map
- Skim the Quick Index to choose the track relevant to the prompt you expect.
- Pair the Platform section with questions on onboarding, reliability, or cost control.
- Use each weekly section to craft STAR style case studies that start with the named business challenge.
- When you discuss outcomes, cite the evaluation and diagnostic files noted here to prove measurement.

## Quick index

| Track | Repo anchors | Interview angle |
| --- | --- | --- |
| Platform setup | `README.md`, `setup/`, `pyproject.toml`, `environment.yml` | Show you can bootstrap cross platform environments, defend uv choices, and reason about API costs. |
| Guides | `guides/*.ipynb` | Highlight practical fluency across CLI, git, notebooks, async Python, and infrastructure. |
| Weekly builds | `week1` ... `week8` | Provide end to end stories that progress from prompt engineering to agentic systems. |
| Extras and community | `extras/`, `community-contributions/` | Demonstrate curiosity plus domain specific experiments beyond the core path. |

## Platform setup and operational readiness

### Setup playbooks and diagnostics
- `README.md` – *comment:* Explains uv adoption, Ollama first run, API selection, and budgeting guidance; reference this when interviewers probe platform tradeoffs or operational guardrails.
- `setup/SETUP-new.md` – *comment:* Cross platform uv instructions plus gotcha lists about permissions, antivirus, and SSL; use this to describe how you unblock teammates quickly.
- `setup/SETUP-PC.md`, `setup/SETUP-linux.md`, `setup/SETUP-mac.md` – *comment:* Provide OS specific clones, Git, and Cursor flows; mention them when emphasising inclusive onboarding support.
- `setup/troubleshooting.ipynb`, `setup/diagnostics.ipynb`, and `setup/diagnostics.py` – *comment:* Notebook and script to probe environment health (API reachability, GPU, Python); cite when asked how you debug install issues remotely.

### Dependency and environment specs
- `pyproject.toml` and `uv.lock` – *comment:* Document uv based dependency graphs; prep to explain why uv replaced the original Anaconda flow and how you pin toolchains.
- `requirements.txt` and `environment.yml` – *comment:* Legacy compatibility manifests for pip or Conda; talk about supporting mixed ecosystems in enterprise teams.
- `venv/` – *comment:* Captures a ready made virtual environment; mention isolation strategy when discussing reproducibility and cost of context switching.

## Foundational guides (rapid refresh)

### Workflow and collaboration (Guides 01–04)

| Notebook | Theme | Interview comment |
| --- | --- | --- |
| `guides/01_intro.ipynb` | Course orientation, productivity systems, study plan | Use this to explain how you ramp a cohort and set success metrics. |
| `guides/02_command_line.ipynb` | Shell navigation, pipes, automation | Reference it when claiming CLI comfort or scripting habits. |
| `guides/03_git_and_github.ipynb` | Branching, pull requests, conflict resolution | Cite this when emphasising team workflows or code review etiquette. |
| `guides/04_technical_foundations.ipynb` | LLM architecture, hardware, context tradeoffs | Mention it when interviewers ask about system level understanding. |

### Python, notebooks, debugging (Guides 05–10)

| Notebook | Theme | Interview comment |
| --- | --- | --- |
| `guides/05_notebooks.ipynb` | Notebook best practices, magics, exports | Show that you can move from exploration to scripts cleanly. |
| `guides/06_python_foundations.ipynb` | Core Python syntax, typing, packaging | Reassure interviewers that fundamentals are solid. |
| `guides/07_vibe_coding_and_debugging.ipynb` | Iterative development workflow | Connect this to how you collaborate with AI pair programmers. |
| `guides/08_debugging.ipynb` | Systematic debugging drills | Reference when asked about troubleshooting under pressure. |
| `guides/09_ai_apis_and_ollama.ipynb` | API key management, local inference, rate limits | Demonstrate awareness of vendor lock-in versus local hosting. |
| `guides/10_intermediate_python.ipynb` | Iterators, generators, dataclasses | Use to justify efficiency and readability improvements. |

### Shipping features fast (Guides 11–14)

| Notebook | Theme | Interview comment |
| --- | --- | --- |
| `guides/11_async_python.ipynb` | asyncio patterns, concurrency gotchas | Reference when claiming large scale ingestion knowledge. |
| `guides/12_starting_your_project.ipynb` | Scoping, backlog planning, MVP slicing | Helps you explain delivery strategy questions. |
| `guides/13_frontend.ipynb` | Frontend stacks that pair with AI backends | Use it to show empathy for UX teams. |
| `guides/14_docker_terraform.ipynb` | Containerisation and IaC primers | Mention when interviewers ask about deployment readiness. |

## Weekly build roadmap

### Week 1 – Prompting, scraping, and brochure generation
**Focus:** Build the first frontier LLM lab, wire Chat Completions to Ollama, practice token budgeting, and convert a site into a marketing brochure.  
**Key files:** `week1/scraper.py`, `week1/solution.py`, `week1/day4.ipynb`, `week1/day5.ipynb`, `week1/week1 EXERCISE.ipynb`.  
**Interview comments:**
- Use `week1/scraper.py` to discuss sanitising HTML, custom headers, and why you cap characters before summarisation.
- `week1/solution.py` lets you explain system versus user prompts, persona control, and how to swap OpenAI for Ollama by changing the base URL.
- `week1/day4.ipynb` covers tokenizer behaviour and context illusions; cite it when asked about hallucination or cost containment.
- `week1/day5.ipynb` frames a business challenge (brochure builder) so you can show impact beyond toy demos.

### Week 2 – API orchestration and UI
**Focus:** Call multiple frontier APIs, build Gradio interfaces, wire conversational callbacks, and add tool use plus multimodal responses.  
**Key files:** `week2/day2.ipynb`, `week2/day3.ipynb`, `week2/day4.ipynb`, `week2/day5.ipynb`, `week2/scraper.py`, `week2/week2 EXERCISE.ipynb`.  
**Interview comments:**
- `week2/day2.ipynb` demonstrates how to translate product requirements into Gradio layouts with authentication hooks; use it to discuss rapid prototyping.
- `week2/day3.ipynb` shows the `chat(message, history)` callback contract so you can argue for stateless server functions.
- `week2/day4.ipynb` and `week2/day5.ipynb` illustrate tool calling, flight data lookups, and multimodal prompts for the Airline assistant; cite them when discussing guardrails.

### Week 3 – Colab, HuggingFace, and meeting minutes
**Focus:** Move heavy work to Google Colab, compare HuggingFace pipelines with lower level model calls, inspect tokenizers, and ship a meeting minutes generator with Drive integration.  
**Key files:** `week3/day1.ipynb`, `week3/day2.ipynb`, `week3/day3.ipynb`, `week3/day4.ipynb`, `week3/day5.ipynb`.  
**Interview comments:**
- Use `week3/day1.ipynb` to explain why you would burst to Colab GPUs versus maintaining local hardware.
- `week3/day2.ipynb` and `week3/day4.ipynb` help you compare managed pipelines against manual model loading, which is a common interview question.
- `week3/day3.ipynb` covers tokenizer internals so you can talk about domain specific vocabulary packing.
- `week3/day5.ipynb` (Meeting minutes creator) shows Drive mounting plus practical audio transcription, a strong story for productivity tooling.

### Week 4 – Code generation into C++ and Rust
**Focus:** Use high end and local frontier models to translate Python routines into optimised native code, decorate the experience with custom UI, and capture system fingerprints before compiling.  
**Key files:** `week4/day3.ipynb`, `week4/day4.ipynb`, `week4/day5.ipynb`, `week4/main.cpp`, `week4/main.rs`, `week4/styles.py`, `week4/system_info.py`.  
**Interview comments:**
- The notebooks walk through prompting GPT 5 class models plus Groq or Ollama for safer code generation; reference them to discuss prompt scaffolding and verification.
- `week4/main.cpp` and `week4/main.rs` are concrete outputs you can point to when explaining benchmarking or multi language deliverables.
- `week4/system_info.py` inventories compilers, CPU features, and package managers, which helps you answer DevOps questions about tailoring generated code to the target box.
- `week4/styles.py` reveals how you polish Gradio frontends, reinforcing a narrative about developer experience.

### Week 5 – Retrieval augmented Insurellm assistant
**Focus:** Build a production style RAG stack with ingestion, vector search, chat UI, and automatic evaluation.  
**Key files:** `week5/implementation/ingest.py`, `week5/implementation/answer.py`, `week5/app.py`, `week5/evaluation/eval.py`, `week5/evaluator.py`, `week5/knowledge-base/`.  
**Interview comments:**
- `week5/implementation/ingest.py` shows how you crawl markdown folders, tag metadata, chunk with overlap, and choose between OpenAI and HuggingFace embeddings; describe these tradeoffs when asked about data prep.
- `week5/implementation/answer.py` plus `week5/app.py` illustrate retrieval plus chat streaming using LangChain and Gradio, a solid story for enterprise copilots.
- `week5/evaluation/eval.py` and `week5/evaluator.py` implement automated retrieval metrics (MRR, nDCG, coverage) and LLM as judge scoring; use them to prove you measure quality before shipping.

### Week 6 – Product pricer data pipeline
**Focus:** Curate 400k Amazon listings, clean and tokenize them, establish baseline regressors, and prepare fine tuning datasets.  
**Key files:** `week6/items.py`, `week6/loaders.py`, `week6/testing.py`, `week6/day1.ipynb` ... `week6/day5.ipynb`, `week6/human_input.csv`, `week6/human_output.csv`.  
**Interview comments:**
- `week6/items.py` details tokenizer based filtering plus prompt templating, so you can speak about dataset quality gates.
- `week6/loaders.py` uses ProcessPoolExecutor with the McAuley Amazon dataset; reference it to show you can scale ETL jobs and respect price bounds.
- `week6/testing.py` builds a RMSLE based harness with scatter plots; cite it when interviewers ask how you evaluate regression models and communicate uncertainty.
- The day4 and day5 notebooks transition into fine tuning plans, perfect for discussing when to stay with frontier inference versus bespoke models.

### Week 7 – Fine tuning open source models in Colab
**Focus:** Execute the pricer fine tuning pipeline on managed GPUs, monitor cost, and export weights for downstream agents.  
**Key files:** `week7/day1.ipynb`, `week7/day2.ipynb`, `week7/day3 and 4.ipynb`, `week7/day5.ipynb` (each links directly to Colab notebooks).  
**Interview comments:**
- These notebooks emphasise how to burst to Colab when local GPUs are unavailable; explain environment replication and secrets handling.
- Tie the Colab steps back to the JSONL and CSV artifacts from Week 6 to prove you understand data lineage.
- Use the links to discuss scheduling long running fine tunes, collecting evaluation metrics remotely, and pulling weights back into Modal or local inference.

### Week 8 – Agentic Price is Right system
**Focus:** Combine fine tuned models, frontier APIs, random forest baselines, RAG lookups, RSS scraping, alerts, and a live Gradio UI into a seven agent framework.  
**Key files:** `week8/deal_agent_framework.py`, `week8/price_is_right.py`, `week8/agents/`, `week8/memory.json`, `week8/day2.0.ipynb` ... `week8/day5.ipynb`.  
**Interview comments:**
- `week8/agents/scanner_agent.py` demonstrates structured outputs with GPT-4o-mini to summarise RSS feeds, so you can discuss grounding and validation.
- `week8/agents/ensemble_agent.py` stitches together the `SpecialistAgent` (Modal fine tune), `FrontierAgent` (RAG plus GPT or DeepSeek), and `RandomForestAgent`; this is a compelling architecture story.
- `week8/agents/messaging_agent.py` shows how you integrate Pushover or Twilio alerts, covering incident response topics.
- `week8/agents/deals.py` plus `week8/agents/planning_agent.py` reveal how you dedupe feeds, maintain `memory.json`, and trigger notifications only when discounts exceed thresholds.
- `week8/deal_agent_framework.py` and `week8/price_is_right.py` capture orchestration logic, timers, persistence, and visualization; use them to highlight production readiness.

## Extras and community builds
- `extras/trading/` – *comment:* Prototype trader notebooks and scripts that run multiple agent prompts against the same market data; perfect for finance or multi agent interview prompts.
- `extras/community/prototype_signal.ipynb` – *comment:* Demonstrates signal routing for multiple agents; cite it when discussing experimentation outside the main sprint.
- `community-contributions/` plus the per week `community-contributions` folders – *comment:* Student showcases ranging from RAG to agents; pick one aligned with your domain to show breadth or leadership.

## Turning coursework into interview stories
- **Search and summarise narrative (Weeks 1–2):** Start with the brochure and airline labs (`week1/scraper.py`, `week2/day4.ipynb`) to show progression from data ingestion to multi modal assistants; emphasise prompt strategy and UI polish.
- **Enterprise RAG narrative (Week 5):** Walk through ingestion (`week5/implementation/ingest.py`), answering (`week5/implementation/answer.py`), and evaluation (`week5/evaluation/eval.py` plus `week5/evaluator.py`); quantify improvements via MRR or judge scores.
- **Data curation to fine tuning narrative (Weeks 6–7):** Explain how `week6/loaders.py` and `week6/items.py` built a clean dataset, then how the Colab notebooks fine tuned a specialist pricer that fed Week 8 agents.
- **Agentic commerce narrative (Week 8):** Use `week8/deal_agent_framework.py`, `week8/agents/ensemble_agent.py`, and `week8/agents/messaging_agent.py` to show orchestration, ensemble learning, and alerting; close with the Gradio UI to prove stakeholder value.
