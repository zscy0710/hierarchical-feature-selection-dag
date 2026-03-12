# FS-MGKC (MATLAB) — Hierarchical Feature Selection for DAG/Tree Labels

A research-oriented MATLAB implementation for **hierarchical feature selection** under DAG/tree label structures.

This repository focuses on:
- splitting multi-level labels into local subtasks,
- structure-aware regularization (parent-child / sibling relationship constraints),
- top-down hierarchical evaluation pipelines.

---

## What this repo implements

The core objective function combines:
1. predictive fitting,
2. structural smoothness constraints from hierarchy topology,
3. sparsity regularization for feature selection.

Main entrypoint:
- `HFS_psrlianheDAG.m`

Quick end-to-end demo script:
- `patch/run_demo.m`

---

## Repository layout

- `HFS_psrlianheDAG.m`  
  Core optimization / feature selection routine.

- `patch/`  
  Utility scripts and runnable demo pipeline (`run_demo.m`).

- `evaluation/`  
  Hierarchical metrics and top-down evaluation helpers.

- `creatSubTable/`  
  Data splitting utilities based on hierarchy structure.

- `treeFunction/`  
  Tree/DAG topology helper functions.

- `DDTrain.mat`  
  Example dataset used by the demo pipeline.

---

## Quick start (MATLAB)

### Prerequisites
- MATLAB R2021a+ (older versions may work)
- A local checkout of this repository

### Run demo
From MATLAB, run:

```matlab
cd patch
run_demo
```

The demo performs:
1. load `DDTrain.mat`,
2. normalize hierarchy roots when needed,
3. build subtask tables,
4. construct structural matrix (`F1`),
5. run `HFS_psrlianheDAG` and print selected root features.

---

## Reproducibility notes

- The repository includes an example training matrix and hierarchy data.
- Some helper scripts are compatibility/adaptation utilities retained for reproducibility.
- If you plan to benchmark, keep MATLAB version and random seed configuration fixed.

---

## Current status

This is an actively maintained personal research codebase used for hierarchical classification experiments and feature selection studies.

Open issues are welcome for:
- numerical stability improvements,
- cleaner experiment configs,
- additional benchmark datasets,
- MATLAB-to-Python migration planning.

---

## Codex-for-OSS usage plan

This project is a strong candidate for Codex-assisted open-source maintenance, especially for:
- refactoring legacy MATLAB utilities,
- adding stronger tests around hierarchy invariants,
- producing reproducible experiment scripts,
- improving documentation and onboarding.

(See `OPENAI_CODEX_OSS_APPLICATION.md` for a ready-to-submit application draft.)
