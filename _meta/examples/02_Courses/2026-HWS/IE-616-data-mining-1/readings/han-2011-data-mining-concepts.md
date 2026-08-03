---
type: reading
status: done
created: 2026-09-10
course: IE-616
semester: 2026-HWS
source: "Han, Kamber, Pei — Data Mining: Concepts and Techniques, 3rd ed."
authors: [Jiawei Han, Micheline Kamber, Jian Pei]
year: 2011
tags: [textbook, data-mining]
moc: ["[[machine-learning]]"]
rating: 4
due: 
---

# Han et al. — Data Mining: Concepts and Techniques (ch. 1)

**Core claim (1 sentence):** Data mining is a step within the broader KDD process focused on extracting non-trivial, previously unknown, and potentially useful patterns from data.

## Method
- Textbook survey chapter — defines the KDD phases, contrasts data mining with statistics, DBs, and ML.
- Uses the "iceberg" metaphor: data mining is the visible tip, preprocessing the bulk beneath.

## Results
- Formal taxonomy of DM tasks: *characterization, discrimination, association, classification, clustering, outlier analysis, evolution analysis*.
- Introduces the notion of **interestingness measures** — a pattern is interesting if it is (1) understandable, (2) valid on new data, (3) potentially useful, (4) novel.
- Emphasises that raw statistical significance alone is not sufficient for a pattern to be "interesting".

## Critique / open questions
- The taxonomy is comprehensive but pre-deep-learning; representation learning and self-supervised approaches are absent.
- The interestingness definition is philosophical rather than operational — hard to encode as an algorithmic criterion.

## Connections
- [[2026-09-09-intro-kdd]] — KDD-process walkthrough matches this chapter's framing.
- [[2026-09-16-frequent-itemsets-apriori]] — this chapter motivates why we need Apriori in the first place.
- [[machine-learning]] — general area MOC.
