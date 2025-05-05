# Multi‑Agent Collaborative System (MACS)

> **Course:** ITAI 2376 – Deep Learning in Artificial Intelligence  •  **Term:** Spring 2025  •  **Professor:** Dr. Lina Awodogan
>
> **Team | Group 1 – AI Dreamers:** Win Aung • Troy Frost • Hisham Macaraya • Soriel Martinez • Jenner Ramos

---

## Table of Contents

1. [Problem Statement](#problem-statement)
2. [System Architecture](#system-architecture)
3. [Agent Roles](#agent-roles)
4. [Tech Stack](#tech-stack)
5. [Getting Started](#getting-started)
6. [Project Roadmap](#project-roadmap)
7. [Evaluation Strategy](#evaluation-strategy)
8. [Contributing](#contributing)
9. [Authors](#authors)
10. [License](#license)

---

## Problem Statement

Traditional academic collaborations often suffer from communication delays, redundant effort, and inconsistent quality. **MACS** streamlines complex, multi‑step research workflows by delegating each stage—research, critique, editing, and coordination—to specialized intelligent agents that communicate through a central coordinator, ensuring faster turnaround and consistent, high‑quality output.

## System Architecture

```
┌──────────────┐       gathers ⇒   ┌───────────────┐
│ Researcher   │ ──── data ───▶  │   Critic       │
└──────────────┘                 └───────────────┘
        ▲                               │ reviews &
        │                               │ validates
 summaries                            feedback ▼
        │                               │
┌──────────────┐  organizes & edits ▶ ┌───────────────┐
│  Coordinator │ ◀──────── comms ─── │    Editor      │
└──────────────┘                       └───────────────┘
```

The **Planning‑then‑Execution** pattern governs task routing and synchronization. `SPADE` handles inter‑agent messaging; each agent runs as an independent XMPP‑based service.

## Agent Roles

| Agent           | Responsibilities                                              |
| --------------- | ------------------------------------------------------------- |
| **Researcher**  | Query Kaggle & web APIs, extract and synthesize key findings  |
| **Critic**      | Fact‑check credibility, flag inconsistencies, score relevance |
| **Editor**      | Refine narrative flow, enforce style & formatting guidelines  |
| **Coordinator** | Orchestrate task sequence, track progress, resolve conflicts  |

## Tech Stack

* **Google Colab** (Pro/Pro+) – development & runtime environment
* **Kaggle API** – dataset retrieval & metadata
* **SPADE** – multi‑agent framework
* **NLTK / pandas / requests** – NLP & data wrangling
* **Python 3.10** (≥)

## Getting Started

### Prerequisites

* Python 3.10+ and `pip`
* Kaggle account & API token (`~/.kaggle/kaggle.json`)
* Google account (for Colab)

### Quick Start (Colab)

1. **Clone the repo & open the notebook**

   ```bash
   git clone https://github.com/<your‑org>/multi‑agent‑collaboration.git
   ```
2. Launch `Multi_Agent_Collaboration.ipynb` in Google Colab.
3. **Install requirements** inside Colab:

   ```python
   !pip install -r requirements.txt
   ```
4. **Load your Kaggle token**:

   ```python
   import os, json, zipfile, pathlib, shutil
   # upload kaggle.json via Colab UI, then run:
   !mkdir -p ~/.kaggle && mv kaggle.json ~/.kaggle/ && chmod 600 ~/.kaggle/kaggle.json
   ```
5. **Run the notebook cells** to start individual agents and the coordinator.

### Local Execution

```bash
pip install -r requirements.txt
python agents/launch_all.py  # spawns all four agents
```

Logs appear in `logs/`.

## Project Roadmap

| Phase                       | Dates           | Milestones                                  |
| --------------------------- | --------------- | ------------------------------------------- |
| **1 Planning**              | Apr 1 – Apr 7   | Finalize architecture & proposal            |
| **2 Prototype**             | Apr 8 – Apr 21  | Build MVP agents, integrate Kaggle API      |
| **3 Integration & Testing** | Apr 22 – Apr 28 | Plug into SPADE, conduct functional tests   |
| **4 Finalization**          | Apr 29 – May 5  | Optimize, record demo video, deliver report |

## Evaluation Strategy

* **Functional testing**: unit & integration tests (`pytest`)
* **Performance metrics**: latency (ms) per task, accuracy scores, resource usage
* **User testing**: qualitative feedback on usability & output quality

Success Criteria:

1. All core agent functions operational.
2. Task completion faster than manual baseline by ≥25%.
3. ≥80% positive feedback in user surveys.

## Contributing

Contributions are welcome! Please open an issue or submit a PR following our [contribution guidelines](CONTRIBUTING.md).

## Authors

Win Aung • Troy Frost • Hisham Macaraya • Soriel Martinez • Jenner Ramos

## License

Distributed under the **MIT License**. See `LICENSE` for more information.
