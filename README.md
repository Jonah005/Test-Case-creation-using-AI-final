# AI-Based Automated Test Case Generator

A research-driven automated test generation system for **Python, JavaScript, and Rust**.

The project combines source-code analysis with transformer-based models to generate unit tests across multiple programming languages. It uses **Control Flow Graphs (CFGs)** to represent execution paths and branching, then fine-tunes **StarCoderBase-1B** using **LoRA** for structure-aware test generation.

> **Source code, training data, and model artifacts are maintained privately.**  
> This public repository documents the published research, system design, and evaluation results.

## Why This Project

Traditional software testing can require significant manual effort and often relies on language-specific tooling. This project explores whether a single AI-assisted pipeline can generate useful unit tests across multiple programming languages while incorporating structural information from the source code.

## High-Level Workflow

1. Extract valid functions from source-code datasets.
2. Generate Control Flow Graphs to represent execution paths and branching.
3. Pair source functions, CFGs, and corresponding test cases into structured training examples.
4. Fine-tune StarCoderBase-1B using LoRA.
5. Generate test cases for unseen functions.
6. Evaluate generated tests across multiple function categories.

See the [architecture overview](docs/architecture.svg).

## Supported Languages

- Python
- JavaScript
- Rust

## Evaluation

The published evaluation used **28 functions per language**, split across four categories:

- Pure / Deterministic
- Data-Structure Heavy
- Numeric / Edge Cases
- String / Regex Parsing

| Language | Passed | Total | Success Rate |
|---|---:|---:|---:|
| Python | 26 | 28 | 92.9% |
| JavaScript | 25 | 28 | 89.3% |
| Rust | 23 | 28 | 82.1% |

See the [evaluation summary](results/evaluation-summary.md).

## Research Publication

**NLP-Powered Test Case Generation from Function Description – A Cross-Language Approach**

**Authors:** Jonah Varghese Kachirackal, Vijayakumar Balakrishnan

Published in the **2025 IEEE 3rd International Conference on Computational Intelligence and Network Systems (CINS)**.

ResearchGate:  
https://www.researchgate.net/publication/401529102_NLP-Powered_Test_Case_Generation_from_Function_Description_-_A_Cross-Language_Approach

## Award

🏆 **Best Paper Award — CINS 2025**  
Department of Computer Science, BITS Pilani Dubai Campus  
25–26 November 2025

## Technologies and Concepts

- Python
- JavaScript
- Rust
- StarCoderBase-1B
- LoRA fine-tuning
- Control Flow Graphs
- Abstract Syntax Trees
- Transformer-based code generation
- Automated software testing

## Repository Contents

- `docs/architecture.svg` — high-level pipeline diagram
- `docs/methodology.md` — concise explanation of the research pipeline
- `results/evaluation-summary.md` — evaluation setup, results, and limitations
- `research/publication.md` — publication and award information
- `CITATION.cff` — citation metadata

## Source Code

The full implementation, training pipeline, datasets, and model artifacts are maintained in a private repository.

This repository is intended as a public research and project showcase. Source access can be provided for technical review where appropriate.
