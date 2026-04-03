<div align="center">

# Orion

**Repo intelligence for engineers who read code for a living.**

<br>

[![Status](https://img.shields.io/badge/status-early_access-blue)](#)
[![License](https://img.shields.io/badge/license-MIT-green)](#)

</div>

---

## What it is

Orion is a codebase analysis tool that builds a structured understanding of a repository — its architecture, data flow, module boundaries, and key logic — and surfaces that as queryable context.

It is designed for engineers dropped into unfamiliar code who need answers fast, without grep-and-pray or spending an afternoon reading call stacks.

---

## Core capabilities

| Capability | Description |
|---|---|
| **Structural mapping** | Identifies module boundaries, entry points, dependency graphs, and inter-service contracts |
| **Flow tracing** | Traces execution paths across files and packages from a named symbol or endpoint |
| **Architecture inference** | Detects architectural patterns (layered, hexagonal, event-driven, etc.) from structure alone |
| **Context extraction** | Produces a precise, token-efficient summary of what a repo does and how it is organised |
| **Change impact analysis** | Given a diff, identifies which components are affected and flags high-risk blast radius |

---

## Who it's for

- Engineers onboarding to a large or legacy codebase
- Reviewers who need full context before approving a diff
- Teams maintaining systems with poor or absent documentation
- Anyone who has spent time reverse-engineering code that should have been obvious

---

## Design decisions

**No LLM hallucination layer on top of vague embeddings.**
Analysis is grounded in static structure — ASTs, import graphs, call graphs — before any language model touches it. The model explains structure it can actually see.

**Deterministic outputs for structural queries.**
Module maps, dependency trees, and entry points are computed, not guessed. Language model involvement is scoped to explanation and summarisation, not inference of facts.

**Repo-local by default.**
Nothing leaves your machine unless you explicitly choose a hosted mode. The local path is first-class.

---

## Status

Active development. Core analysis pipeline is functional for TypeScript and Python repositories. Go, Rust, and Java support are in progress.

Not production-hardened yet. Breaking changes are expected.

---

## Get involved

Issues and technical feedback are open. If you work on tooling, developer experience, or spend time reasoning about large codebases, conversation is welcome.

---

<div align="center">
<sub>orionssh — building the layer between you and unfamiliar code</sub>
</div>
