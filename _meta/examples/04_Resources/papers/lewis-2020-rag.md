---
type: reading
status: done
created: 2027-11-10
source: "Lewis et al. — Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks (NeurIPS 2020)"
authors: [Patrick Lewis, Ethan Perez, Aleksandra Piktus, et al.]
year: 2020
tags: [rag, nlp, retrieval]
moc: ["[[machine-learning]]"]
rating: 5
due: 
---

# Lewis et al. — RAG for Knowledge-Intensive NLP

**Core claim (1 sentence):** Combining a parametric seq2seq model with a non-parametric dense retriever (DPR) yields strong, factually grounded generation on open-domain QA and fact-verification tasks.

## Method
- Two variants: **RAG-Sequence** (same retrieved doc for whole output) and **RAG-Token** (per-token retrieval marginalisation).
- Retriever: DPR (dense passage retrieval), retriever + generator jointly fine-tuned.
- Generator: BART-large. Non-parametric memory: Wikipedia dumps encoded with DPR.

## Results
- SOTA on Natural Questions, TriviaQA, WebQuestions at time of publication.
- Beats extractive QA baselines despite generating free-form answers.
- More factually accurate than parametric-only seq2seq (Jeopardy generation study).

## Critique / open questions
- Retriever is frozen during downstream tasks after initial training — later work (REPLUG, Atlas) shows online updates help.
- Evaluation is dominated by *exact match* — misses semantic correctness.
- Wikipedia as the corpus limits real-world applicability; my thesis targets legal texts, where the retrieval quality problem is worse.

## Connections
- [[thesis-proposal-rag]] — foundational reference for §2.
- [[machine-learning]]
