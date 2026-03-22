# Swiss-Bench SBP-002

A trilingual benchmark for evaluating frontier language models on applied Swiss regulatory compliance tasks.

## Overview

Swiss-Bench SBP-002 evaluates ten frontier models (March 2026) on 395 expert-crafted items across three Swiss regulatory domains (FINMA, Legal-CH, EFK), seven task types, and three languages (German, French, Italian). Model responses are scored by a blind three-judge LLM panel using structured numeric scoring with deterministic grade computation.

Reference answers were independently validated by a Swiss legal expert (MLaw, University of Fribourg) on a 100-item subset: 100% Legal Accuracy, 0% rated Incorrect.

## Key Findings

- The benchmark is difficult: even the top-ranked model achieves only 38.2% correct.
- Three performance clusters emerge: Tier A (35-38%), Tier B (26-29%), Tier C (13-21%).
- Task type difficulty varies widely: case analysis and legal translation yield 69-72% correct, while regulatory Q&A and hallucination detection remain below 9%.
- Open-weight models are competitive: the top-ranked model is open-weight.

## Paper

**Swiss-Bench SBP-002: A Frontier Model Comparison on Swiss Legal and Regulatory Tasks**

Fatih Uenal, University of Colorado Boulder

ArXiv preprint: [link forthcoming]

## Benchmark Composition

| Domain | Items | Description |
|--------|-------|-------------|
| FINMA | 178 | Financial market regulation (circulars, Banking Act, AML) |
| Legal-CH | 169 | Swiss federal law (nDSG, OR, EU AI Act implications) |
| EFK | 48 | Federal Audit Office requirements and AI governance |

| Task Type | Items |
|-----------|-------|
| Regulatory Q&A | 104 |
| Hallucination detection | 63 |
| Regulatory gap analysis | 59 |
| Jurisdiction discrimination | 58 |
| Statutory interpretation | 46 |
| Case analysis | 35 |
| Legal translation | 30 |

Languages: German (150), French (148), Italian (97).

## Models Evaluated

| Rank | Model | Category | Correct % | Tier |
|------|-------|----------|-----------|------|
| 1 | Qwen 3.5 Plus | Open-weight | 38.2 | A |
| 2 | Gemini 2.5 Flash | Closed-source | 35.4 | A |
| 3 | GLM 5 | Open-weight | 28.6 | B |
| 4 | Claude Sonnet 4 | Closed-source | 26.1 | B |
| 5 | MiniMax M2.5 | Open-weight | 20.8 | C |
| 6 | MiMo-V2-Flash | Open-weight | 19.0 | C |
| 7 | DeepSeek V3.2 | Open-weight | 18.5 | C |
| 8 | GPT-4o | Closed-source | 16.5 | C |
| 9 | GPT-oss 120B | Open-weight | 15.7 | C |
| 10 | Mistral Large 3 | Open-weight | 12.9 | C |

## Scoring Framework

Each response is evaluated on three dimensions:
- **Legal Accuracy** (weight 0.5): Correctness of legal claims and statutory citations.
- **Citation Accuracy** (weight 0.3): Whether cited provisions exist and are correctly attributed.
- **Completeness** (weight 0.2): Coverage of all aspects raised in the prompt.

Grades: C (Correct, score >= 0.8), P (Partially correct, 0.5-0.8), I (Incorrect, < 0.5).

Judge panel: GPT-4o, Claude Sonnet 4, Qwen3-235B. Final grade by majority vote.

## Citation

```bibtex
@article{uenal2026swissbench,
  title={Swiss-Bench SBP-002: A Frontier Model Comparison on Swiss Legal and Regulatory Tasks},
  author={Uenal, Fatih},
  year={2026},
  note={ArXiv preprint}
}
```

## License

CC BY-NC-SA 4.0

## Contact

Fatih Uenal -- fatih.uenal@colorado.edu
