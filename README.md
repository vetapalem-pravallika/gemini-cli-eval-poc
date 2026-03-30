# Gemini CLI Evaluation PoC

This repository contains a **Proof-of-Concept (PoC)** framework for the **Reasoning-Force Score (RFS)**, designed to benchmark long-context, cross-component reasoning in LLM-based developer tools like Gemini CLI.

## 🚀 Key Features

* **Structured Task Schema**: Defines strict metadata, environment, and task definitions for deterministic evaluation.
* **Long-Context Benchmarks**: Specifically engineered for tasks requiring **50K+ tokens** and multi-file architectural reasoning.
* **Contamination-Aware Pipeline**: Includes **Temporal Risk Scoring** and metadata scrubbing to ensure the model is reasoning, not just retrieving memorized training data.
* **AST Dependency Hops**: A novel metric that tracks architectural boundaries (class/module jumps) to measure genuine logic depth.
* **Automated Validation**: Integrated `scripts/validate_schema.py` to ensure all tasks meet the RFS Expert-tier requirements.
* **TestRig Integration**: Stubs designed for seamless compatibility with the Gemini CLI evaluation pipeline and leaderboards.

## 📊 Reasoning-Force Metric Matrix

This PoC uses a multi-dimensional scoring system to distinguish between **Retrieval** (Memory) and **Reasoning** (Logic):

| Metric | Level | Architectural Impact |
| :--- | :--- | :--- |
| **AST Hops** | 1–2 | Localized function/class reasoning. |
| **AST Hops** | 3–5 | **Cross-module invariant synchronization (Target).** |
| **RFS Score** | < 4 | High contamination risk; likely memorized behavior. |
| **RFS Score** | 7+ | **Novel logic synthesis required (Target).** |
| **Temporal Risk** | High | Task exists in model training data (Pre-2025). |
| **Temporal Risk** | Low | **Post-cutoff task; requires zero-shot reasoning.** |

## 📂 Directory Structure

* `schema.json` — The "Source of Truth" for task format and RFS requirements.
* `scripts/` — Automated tools for dataset generation, scrubbing, and validation.
* `tasks/` — Curated evaluation tasks (includes `sample_task.json` for Kubeflow).
* `docs/` — Repository sources and architectural documentation.
* `datasets/` — Generated JSONL outputs for pipeline execution.

## 🛠️ Getting Started

### 1. Clone & Setup
```cmd
git clone [https://github.com/vetapalem-pravallika/gemini-cli-eval-poc.git](https://github.com/vetapalem-pravallika/gemini-cli-eval-poc.git)
cd gemini-cli-eval-poc
pip install -r requirements.txt