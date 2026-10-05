# Evaluation Summary

The published evaluation tested the system across **Python, JavaScript, and Rust**.

Each language was evaluated on **28 functions**, with **7 functions per category** across four categories:

- Pure / Deterministic
- Data-Structure Heavy
- Numeric / Edge Cases
- String / Regex Parsing

## Results

| Language | Passed | Total | Failed | Success Rate |
|---|---:|---:|---:|---:|
| Python | 26 | 28 | 2 | 92.9% |
| JavaScript | 25 | 28 | 3 | 89.3% |
| Rust | 23 | 28 | 5 | 82.1% |

The evaluation considered a generated test successful when it was produced and followed the correct logic for the target function.

## Reported Limitations

The paper identifies several limitations:

- the evaluation focused on four deterministic categories
- exception/validator cases were excluded
- stateful classes or objects were excluded
- difficult edge cases showed weaker generalization
- dataset diversity was constrained by hardware and environment limits
- parts of the CFG preprocessing required manual handling

These results are presented as a proof of concept for cross-language, structure-aware AI test generation.
