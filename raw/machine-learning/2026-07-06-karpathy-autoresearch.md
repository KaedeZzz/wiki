---
source_url: https://github.com/karpathy/autoresearch
fetched: 2026-07-06
author: Andrej Karpathy
license: MIT
default_branch: master
---

# karpathy/autoresearch — raw

## Repository description (GitHub about)

> AI agents running research on single-GPU nanochat training automatically

- 90,000+ stars, 13,000+ forks (as of fetch)
- MIT licensed
- Community forks support MacOS, Windows, AMD

## README.md

# autoresearch README

## Overview

This project enables autonomous AI research by allowing an agent to modify and iterate on machine learning training code overnight. The agent edits `train.py`, runs 5-minute training experiments, and logs improvements—demonstrating how "frontier AI research" could be conducted by autonomous systems rather than humans.

## Key Components

Three essential files structure the project:

- **prepare.py**: Fixed utilities for data preparation and evaluation (unmodified)
- **train.py**: The sole file agents modify, containing the GPT model, optimizer, and training loop
- **program.md**: Instructions provided by humans to guide agent behavior

## Core Design Principles

The system uses a **5-minute fixed time budget** for all experiments, making results comparable across different hardware configurations. The evaluation metric is **val_bpb** (validation bits per byte), where lower scores indicate better performance.

## Getting Started

Requirements include a single NVIDIA GPU, Python 3.10+, and the `uv` package manager. Setup involves:

1. Installing dependencies via `uv sync`
2. Running `uv run prepare.py` for data preparation
3. Executing `uv run train.py` for initial training

## Autonomous Mode

Users can prompt Claude or similar agents with something like: "Look at program.md and let's start a new experiment!" The agent then autonomously modifies code and runs iterative training cycles.

## Platform Considerations

While currently NVIDIA-GPU focused, several community forks support alternative platforms (MacOS, Windows, AMD). The documentation provides optimization guidance for smaller compute systems, including dataset selection, vocabulary reduction, and architecture simplification.

The project maintains MIT licensing and encourages community contributions through documented forks.

## program.md

# autoresearch Framework Summary

This document describes an autonomous machine learning experimentation framework where an LLM iteratively improves a language model's validation bits-per-byte (val_bpb) metric.

## Key Constraints

The setup requires:
- A fresh git branch named `autoresearch/<tag>`
- Fixed 5-minute training time budget
- Read-only `prepare.py` file (evaluation, data loading, tokenizer)
- Modification rights only to `train.py`
- No new package dependencies

## Core Loop

The autonomous researcher:

1. Modifies `train.py` (architecture, hyperparameters, batch size, optimizer)
2. Commits changes
3. Executes `uv run train.py > run.log 2>&1`
4. Extracts results: "grep "^val_bpb:\|^peak_vram_mb:" run.log"
5. Records findings in `results.tsv` (tab-separated)
6. Keeps improvements, reverts failures via git reset

## Success Criteria

- Minimize val_bpb (lower is better)
- Prefer simplicity; complexity must justify gains
- VRAM is a soft constraint
- Run continuously until manually stopped
- Never pause to ask for permission

Results are logged with commit hash, val_bpb, memory (GB), status (keep/discard/crash), and brief description.
