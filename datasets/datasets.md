# Datasets

This file contains verified datasets relevant to **detecting citation drift in AI-generated literature summaries**. The selected datasets support scientific claim verification, citation-context analysis, and scientific-document summarization.

> **Selection principle:** The datasets below were selected because their official project pages/documentation clearly describe their data, research purpose, and access information.

---

## 1. SciFact

**Dataset:** SciFact  
**Creators:** David Wadden, Shanchuan Lin, Kyle Lo, Lucy Lu Wang, Madeleine van Zuylen, Arman Cohan, Hannaneh Hajishirzi  
**Year:** 2020  
**Associated paper:** *Fact or Fiction: Verifying Scientific Claims*  
**Venue:** EMNLP 2020  
**DOI:** 10.18653/v1/2020.emnlp-main.609

### Description

SciFact is a scientific claim-verification dataset containing approximately 1.4K expert-written scientific claims paired with evidence-containing research abstracts. Claims are annotated with **SUPPORT** or **CONTRADICT** labels and evidence rationales.

### Application to This Repository

SciFact is highly relevant to citation-drift research because citation verification requires determining whether evidence from a cited scientific source actually supports or contradicts a generated claim.

It can therefore be used to study:

- Claim verification
- Evidence retrieval
- Citation-claim alignment
- Scientific fact checking
- Evidence-grounded AI generation
- Support/contradiction classification

### Dataset Structure

The official project provides:

- Training claims
- Development claims
- Test claims
- Scientific evidence corpus
- Evidence rationales
- Citation-context / claim-generation data

### Official Resources

- [Official GitHub Repository](https://github.com/allenai/scifact)
- [ACL Anthology Paper](https://aclanthology.org/2020.emnlp-main.609/)
- [Dataset on Hugging Face](https://huggingface.co/datasets/allenai/scifact)

### License

The SciFact dataset is released under **CC BY-NC 2.0**. Check the dataset license before redistribution or commercial use.

### Why It Matters

A citation may look correct but still fail to support the claim attached to it. SciFact provides a useful foundation for modeling this evidence-verification problem.

---

## 2. SciFact-Open

**Dataset:** SciFact-Open  
**Creators:** David Wadden, Kyle Lo, Bailey Kuehl, Arman Cohan, Iz Beltagy, Lucy Lu Wang, Hannaneh Hajishirzi  
**Year:** 2022  
**Associated paper:** *SciFact-Open: Towards open-domain scientific claim verification*  
**Venue:** Findings of EMNLP 2022  
**DOI:** 10.18653/v1/2022.findings-emnlp.347

### Description

SciFact-Open extends scientific claim verification toward a much larger, open-domain evidence corpus. Its corpus contains approximately **500,000 research abstracts from S2ORC**, allowing systems to search a large scientific collection rather than relying on a small predefined evidence set.

### Application to This Repository

This dataset is especially relevant to citation drift because a practical citation-verification system needs to locate the correct source from a large scholarly corpus.

Potential applications include:

- Open-domain citation verification
- Scientific evidence retrieval
- Citation-source matching
- Claim-to-document retrieval
- Evidence ranking
- Automated research-assistant evaluation

### Dataset Components

The official project provides:

- `claims.jsonl`
- `claims_metadata.jsonl`
- `corpus.jsonl`
- `corpus_candidates.jsonl`
- Evidence annotations
- Model predictions used for evaluation

### Official Resources

- [Official GitHub Repository](https://github.com/dwadden/scifact-open)
- [ACL Anthology Paper](https://aclanthology.org/2022.findings-emnlp.347/)
- [Dataset Documentation](https://github.com/dwadden/scifact-open/blob/main/doc/data.md)

### Why It Matters

A major challenge in citation verification is not only checking whether a citation exists, but finding the correct evidence among a large collection of scientific documents. SciFact-Open directly supports this retrieval-and-verification problem.

---

## 3. SciTLDR

**Dataset:** SciTLDR  
**Creators:** Isabel Cachola, Kyle Lo, Arman Cohan, Daniel S. Weld  
**Year:** 2020  
**Associated paper:** *TLDR: Extreme Summarization of Scientific Documents*  
**Research area:** Scientific document summarization

### Description

SciTLDR is a dataset for **extreme summarization of scientific documents**. It provides scientific-paper source material together with short summaries, including author-written and peer-generated TLDR-style summaries.

The official project provides train, development, and test splits and includes source sentences, source labels, ROUGE scores, paper identifiers, titles, and target summaries.

### Application to This Repository

SciTLDR is relevant because citation drift can occur when AI systems compress scientific documents into short summaries and then associate citations with claims that are incomplete, altered, or unsupported.

Potential applications include:

- Scientific summarization
- Summary faithfulness evaluation
- Citation-aware summarization
- Information compression
- Evaluation of AI-generated research summaries
- Studying how information changes during summarization

### Dataset Structure

The official project describes a 60/20/20 train/dev/test split. Dataset records contain information such as:

- Source sentences
- Source labels
- ROUGE scores
- Paper ID
- Paper title
- Target summaries

### Official Resources

- [Official GitHub Repository](https://github.com/allenai/scitldr)
- [SciTLDR Dataset Project](https://scitldr.apps.allenai.org/)
- [Research Paper](https://aclanthology.org/2020.findings-emnlp.428/)

### Why It Matters

Citation drift is closely connected to information loss and transformation during summarization. SciTLDR provides a research setting for studying scientific summaries and evaluating how faithfully generated summaries represent their source papers.

---

# Dataset Comparison

| Dataset | Main Task | Main Evidence Type | Relevance to Citation Drift |
|---|---|---|---|
| **SciFact** | Scientific claim verification | Research abstracts + evidence rationales | Very High |
| **SciFact-Open** | Open-domain scientific claim verification | Large scientific abstract corpus | Very High |
| **SciTLDR** | Scientific document summarization | Scientific papers + summaries | High |

---

# How These Datasets Can Be Used Together

The three datasets cover complementary parts of a citation-drift detection pipeline:

```text
Scientific Papers
       |
       v
   SciTLDR
       |
Scientific Summarization
       |
       v
Generated Claims
       |
       v
   SciFact-Open
       |
Evidence Retrieval
       |
       v
    SciFact
       |
Claim / Evidence Verification
       |
       v
Citation Integrity Decision
```

A future research system could therefore combine:

1. **SciTLDR** for scientific summarization,
2. **SciFact-Open** for large-scale evidence retrieval, and
3. **SciFact** for claim/evidence verification.

This combination closely matches the research problem addressed by this repository: determining whether AI-generated scientific summaries remain faithful to their cited evidence.

---

# Verification Notes

Before using any dataset in a research project, verify:

- Official dataset/project page
- Associated research paper
- Dataset version
- License
- Data-access conditions
- Citation requirements
- Whether redistribution is permitted

The official SciFact repository provides data, code, evaluation information, and claim-generation data. citeturn0search0turn0search6

The SciFact paper confirms that the dataset contains expert-written scientific claims paired with evidence-containing abstracts and SUPPORT/CONTRADICT labels. citeturn0search8

The SciFact-Open documentation describes a corpus of approximately 500K research abstracts from S2ORC and its claim/evidence files. citeturn0search11

The official SciTLDR repository documents the dataset structure, including source sentences, source labels, ROUGE scores, paper IDs, titles, and target summaries. citeturn0search1
