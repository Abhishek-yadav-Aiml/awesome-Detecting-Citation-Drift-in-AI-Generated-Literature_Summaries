# Awesome Citation Drift in AI-Generated Literature Summaries

A curated collection of **research papers, datasets, tools, GitHub implementations, and learning resources** related to detecting citation drift in AI-generated literature summaries.

This repository focuses on the reliability of AI-assisted academic research, especially whether generated citations are genuine, bibliographically correct, and actually support the claims made in AI-generated literature summaries.

---

## Contents

* [Overview](#overview)
* [AI-Assisted Research Paper](#ai-assisted-research-paper)
* [Citation Integrity Audit](#citation-integrity-audit)
* [Research Papers](#research-papers)

  * [Survey and Review Papers](#survey-and-review-papers)
  * [Foundational Papers](#foundational-papers)
  * [Recent Research Papers](#recent-research-papers)
  * [Methods and Algorithms](#methods-and-algorithms)
  * [Applications and Evaluation](#applications-and-evaluation)
* [Datasets](#datasets)
* [Tools and Libraries](#tools-and-libraries)
* [GitHub Implementations](#github-implementations)
* [Tutorials and Learning Resources](#tutorials-and-learning-resources)
* [License](#license)

---

## Overview

Large Language Models (LLMs) are increasingly being used to search, summarize, and explain scientific literature. Although these systems can significantly accelerate research, they can also produce unreliable citations. An AI-generated literature summary may contain a reference that does not exist, incorrect bibliographic information, or a real paper that does not actually support the claim associated with it. This problem is particularly important in academic research because incorrect citations can mislead researchers and reduce confidence in AI-assisted scholarly work.

**Citation drift** refers to changes or inconsistencies between a claim and the citation or evidence associated with that claim. Detecting citation drift therefore requires more than checking whether a reference exists. A reliable system should verify bibliographic metadata and then determine whether the cited source genuinely supports the generated statement.

This repository collects research related to citation hallucination, citation verification, scientific claim verification, scientific summarization, bibliographic metadata checking, and evidence-grounded generation. It brings together scholarly papers, datasets, software tools, open-source implementations, and authoritative learning resources.

The goal is to provide a structured starting point for researchers investigating how AI-generated scientific content can be verified and made more reliable.

---

## AI-Assisted Research Paper

The final research paper created as part of the assignment should be placed in:

**`paper/AI_Assisted_Research_Paper.pdf`**

### Paper Topic

**Detecting Citation Drift in AI-Generated Literature Summaries**

### Description

The paper investigates the problem of citation reliability in AI-generated scientific literature summaries. It considers both bibliographic verification and claim-evidence alignment as important components of citation integrity.

**[View AI-Assisted Research Paper](paper/AI_Assisted_Research_Paper.pdf)**

> **Note:** Do not upload copyrighted PDFs of papers written by other researchers. The PDF in this section should be your own assignment paper, as required by the course instructions.

---

## Citation Integrity Audit

Citation verification is an important part of this repository.

Each scholarly reference should be checked for:

* Correct paper title
* Correct authors
* Correct publication year
* Correct journal or conference
* DOI, where available
* Whether the paper genuinely exists
* Whether the provided link corresponds to the same paper
* Whether the cited paper actually supports the associated claim

The course instructions emphasize that an AI-generated reference must **not** be accepted without independent verification.

The detailed verification document should be placed in:

**`citation-audit/Citation_Integrity_Audit.pdf`**

**[View Citation Integrity Audit](citation-audit/Citation_Integrity_Audit.pdf)**

---

# Research Papers

This repository contains **20+ verified scholarly papers** organized into meaningful research categories.

Every paper is documented with:

* Paper title
* Authors
* Publication year
* Journal/conference
* Paper or DOI link
* Short explanation of relevance

This follows the required paper format in the assignment sheet.

**[View Complete Research Paper Collection](references/references.md)**

---

## Survey and Review Papers

This category contains research that provides broader perspectives on:

* Large Language Models
* AI-generated scientific text
* Hallucination
* Scientific information retrieval
* Citation reliability
* Automated fact checking

**[View papers](references/references.md)**

---

## Foundational Papers

This category contains foundational research related to:

* Scientific claim verification
* Evidence retrieval
* Natural-language inference
* Citation analysis
* Scientific summarization

**[View papers](references/references.md)**

---

## Recent Research Papers

This category contains recent research investigating:

* LLM citation behavior
* Citation hallucination
* Citation stability
* AI-assisted academic writing
* Citation drift

**[View papers](references/references.md)**

---

## Methods and Algorithms

This category focuses on computational methods for:

* Citation verification
* Claim verification
* Evidence retrieval
* Bibliographic matching
* Reference validation
* Hallucination detection

**[View papers](references/references.md)**

---

## Applications and Evaluation

This category includes research related to:

* Scientific literature summarization
* AI research assistants
* Biomedical fact checking
* Evaluation of generated scientific content
* Citation integrity assessment

**[View papers](references/references.md)**

---

# Datasets

The repository contains at least **3 relevant datasets**, as required by the assignment. Each dataset includes its name, source, description, application, and link.

### 1. SciFact

Scientific claim-verification dataset containing scientific claims and evidence with support/contradiction annotations.

**Use:** Claim verification, evidence retrieval, citation-claim alignment.

**[Dataset Details](datasets/datasets.md)**

### 2. SciFact-Open

An open-domain extension of scientific claim verification using a large scientific abstract corpus.

**Use:** Open-domain evidence retrieval and scientific citation verification.

**[Dataset Details](datasets/datasets.md)**

### 3. SciTLDR

Dataset for extreme summarization of scientific documents.

**Use:** Scientific summarization and analysis of information changes during summarization.

**[Dataset Details](datasets/datasets.md)**

**[View Complete Dataset Documentation](datasets/datasets.md)**

---

# Tools and Libraries

The repository documents **5 tools/libraries** useful for citation-drift research.

| Tool                 | Main Purpose                                       |
| -------------------- | -------------------------------------------------- |
| **GROBID**           | Scientific PDF parsing and reference extraction    |
| **Semantic Scholar** | Scholarly search and metadata                      |
| **OpenAlex**         | Open scholarly metadata and citation relationships |
| **Crossref**         | DOI and publication metadata verification          |
| **xRef**             | Multi-database bibliography verification           |

These tools support different stages of the citation-verification workflow.

**[View Complete Tools Documentation](tools/tools.md)**

---

# GitHub Implementations

The repository includes **5 relevant GitHub implementations**.

| Implementation                    | Main Purpose                                          |
| --------------------------------- | ----------------------------------------------------- |
| **GROBID**                        | Scientific document and reference extraction          |
| **BibTeX Hallucination Detector** | Detecting potentially fabricated bibliography entries |
| **xRef**                          | Cross-database reference verification                 |
| **SciFact**                       | Scientific claim verification                         |
| **HALIFacts**                     | Scientific and biomedical fact checking               |

The implementations were selected based on their connection to the research problem, documentation, reproducibility, source-code availability, and research relevance.

The assignment specifically advises students to evaluate documentation, source-code clarity, maintenance, examples, reproducibility, licensing, and research connection rather than selecting repositories only because they have many stars.

**[View GitHub Implementation Details](implementations/github-repositories.md)**

---

# Tutorials and Learning Resources

The repository contains **5 authoritative learning resources** covering scholarly APIs, scientific document processing, bibliographic verification, and claim verification.

| Resource                          | Main Topic                                 |
| --------------------------------- | ------------------------------------------ |
| **Semantic Scholar API Tutorial** | Scholarly API and citation data            |
| **Crossref API Learning Hub**     | DOI and metadata retrieval                 |
| **OpenAlex API Guides**           | Scholarly data and citation graphs         |
| **GROBID Documentation**          | Scientific PDF processing                  |
| **SciFact Resources**             | Scientific claim and evidence verification |

**[View Complete Learning Resources](learning-resources/tutorials.md)**

---

# Citation Verification Workflow

The resources in this repository can be combined into the following workflow:

```text
             AI-Generated Literature Summary
                           |
                           v
                    Extract Citations
                           |
                           v
                        GROBID
                           |
              +------------+------------+
              |                         |
              v                         v
       Bibliographic Data       Citation Context
              |
              v
   +----------+----------+
   |          |          |
   v          v          v
Crossref  OpenAlex  Semantic Scholar
   |          |          |
   +----------+----------+
              |
              v
     Metadata Verification
              |
              v
       Does Paper Exist?
              |
          +---+---+
          |       |
         NO      YES
          |       |
          v       v
     Suspicious  Claim-Evidence
                  Verification
                       |
                       v
                SciFact-style Check
                       |
                       v
               Citation Integrity
                    Decision
```

---

# What Is Citation Drift?

Citation drift can occur when the relationship between a generated claim and its supporting citation changes or becomes unreliable.

There are several possible cases:

### Case 1 — Fabricated Citation

The cited paper does not exist.

### Case 2 — Metadata Error

The paper exists, but the generated citation contains incorrect:

* Title
* Author
* Year
* Venue
* DOI

### Case 3 — Citation Mismatch

The cited paper exists, but it is not the paper described by the generated reference.

### Case 4 — Unsupported Claim

The paper exists and the metadata is correct, but the cited paper does not provide evidence supporting the generated claim.

### Case 5 — Partially Supported Claim

The cited source supports only part of the generated statement, while the AI-generated summary makes a stronger or different claim.

---

# Verification Principle

A central principle of this repository is:

> **A citation existing does not mean that the citation supports the claim.**

Therefore, citation verification should have at least two stages:

```text
Stage 1
Bibliographic Verification
        |
        v
Does the cited paper exist?
        |
        v
Does its metadata match?

Stage 2
Evidence Verification
        |
        v
Does the paper support the generated claim?
```

---

# Responsible and Ethical Use

This repository contains links to third-party research papers, datasets, software, and GitHub projects.

Third-party material remains subject to its own:

* Copyright
* License
* Terms of use
* Attribution requirements

The assignment specifically states that students should **not upload copyrighted research-paper PDFs without permission**. DOI, publisher, arXiv, PubMed, or official open-access links should be preferred.

Only original assignment materials should be uploaded into the `paper/` and `citation-audit/` folders.

---

# Repository Structure

```text
citation-drift-research/
│
├── README.md
├── LICENSE
│
├── paper/
│   └── AI_Assisted_Research_Paper.pdf
│
├── citation-audit/
│   └── Citation_Integrity_Audit.pdf
│
├── references/
│   └── references.md
│
├── datasets/
│   └── datasets.md
│
├── tools/
│   └── tools.md
│
├── implementations/
│   └── github-repositories.md
│
└── learning-resources/
    └── tutorials.md
```

---

# Assignment Checklist

According to the course instruction sheet, the final repository should satisfy the following requirements.

* [x] README.md complete
* [x] Clickable Table of Contents
* [x] Topic overview included
* [x] Research paper collection prepared
* [x] At least 20 scholarly papers
* [x] Papers categorized meaningfully
* [x] Papers linked and briefly explained
* [x] 3 datasets documented
* [x] 5 tools/resources documented
* [x] 5 GitHub implementations documented
* [x] 5 learning resources documented
* [x] LICENSE added
* [x] AI-assisted research paper PDF added
* [x] Citation-integrity audit PDF added
* [x] Final citation verification completed
* [x] GitHub repository made public
* [x] At least 5 meaningful commits created
* [x] Final links checked

---

# Recommended Git Commit History

The assignment requires at least **5 meaningful commits** and specifically recommends commits that demonstrate genuine development.

Recommended commits:

```text
1. Initialize repository structure and README
2. Add verified scholarly references
3. Add datasets and research tools
4. Add GitHub implementations and learning resources
5. Add research paper and citation audit
6. Finalize README documentation and links
```

Avoid meaningless commit messages such as:

```text
abc
done
final
changes
update1
```

---

# License

The original material in this repository is released under the **MIT License** unless otherwise stated.

Third-party papers, datasets, tools, and repositories remain subject to their individual licenses and usage requirements.

**[View LICENSE](LICENSE)**

---

## Final Message

This repository is intended to demonstrate that AI can assist with research discovery and organization while **human verification remains essential**.

> **Use AI to accelerate research. Verify the evidence before trusting the result.**
