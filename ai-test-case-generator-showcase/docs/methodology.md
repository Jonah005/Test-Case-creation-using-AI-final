# Methodology Overview

The project uses a multi-stage pipeline for automated unit-test generation across Python, JavaScript, and Rust.

## 1. Function Extraction

Source files are scanned to identify valid function definitions. The extracted functions are cleaned and grouped for downstream processing.

## 2. Control Flow Graph Generation

Each function is converted into a Control Flow Graph (CFG) that represents execution paths such as assignments, conditions, branches, and returns.

Language-specific tooling is used to generate the CFG representation.

## 3. Training Example Construction

Each training example combines:

- the source function
- its CFG representation
- a corresponding test case

These are stored in structured JSONL records for model training.

## 4. LoRA Fine-Tuning

The study fine-tunes `bigcode/starcoderbase-1b` using Low-Rank Adaptation (LoRA).

LoRA reduces the amount of trainable model parameters while adapting the model to the test-generation task.

## 5. Test Generation

The fine-tuned model receives source-code information together with structural context and generates candidate unit tests.

## 6. Evaluation

The published evaluation covers Python, JavaScript, and Rust using four function categories:

- Pure / Deterministic
- Data-Structure Heavy
- Numeric / Edge Cases
- String / Regex Parsing

Each language was evaluated on 28 functions in total.
