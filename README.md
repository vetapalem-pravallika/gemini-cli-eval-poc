**Gemini CLI Evaluation PoC**

This project is a Proof-of-Concept framework for evaluating long-context reasoning in LLM-based developer tools like Gemini CLI.

Key Features

*Structured Task Schema: Defines metadata, environment, and task definitions for cross-module evaluation.
*Long-Context Benchmarks: Supports tasks up to 50K+ tokens, multi-file, and multi-module reasoning.
*Contamination-Aware Evaluation: Includes temporal risk scoring and contamination scrubbing to ensure model reasoning is tested, not memorization.
*AST Dependency Hops: Tracks architectural boundaries to measure real reasoning difficulty.
*Automated Validation: scripts/validate_schema.py checks task compliance with the schema.
*TestRig Integration Stubs: Ready for pipeline and leaderboard integration.

Directory Structure

schema.json        → Defines the JSON schema for tasks
scripts/           → Tools for dataset generation and validation
tasks/             → Evaluation tasks (sample_task.json included)
docs/              → Repository sources and documentation
datasets/          → Generated evaluation datasets
