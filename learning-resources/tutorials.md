# Tutorials and Learning Resources

This file contains authoritative tutorials and learning resources that can help a researcher build the skills needed to detect citation drift in AI-generated literature summaries.

The resources cover scholarly APIs, bibliographic metadata, scientific claim verification, scientific document processing, and reproducible research workflows.

---

## 1. Semantic Scholar API Tutorial

**Provider:** Semantic Scholar / Allen Institute for AI  
**Type:** Scholarly API tutorial  
**Main Topic:** Searching and retrieving scholarly literature programmatically

### Description

The official Semantic Scholar API tutorial teaches users how to interact with the Semantic Scholar APIs using standard HTTP requests and Python examples.

It covers:

- Searching for papers
- Retrieving paper details
- Finding authors
- Getting recommendations
- Working with citations and references
- Pagination
- Downloading datasets
- Making API requests efficiently

### Relevance to Citation Drift

Semantic Scholar can be used to independently search AI-generated references and compare their bibliographic metadata.

A researcher can use the tutorial to build a verification script that checks:

```text
AI-generated citation
        |
        v
Semantic Scholar search
        |
        v
Matching paper
        |
        v
Compare title + authors + year + DOI
```

### Official Resource

[Semantic Scholar API Tutorial](https://www.semanticscholar.org/product/api/tutorial)

### Verification

The official tutorial describes the Academic Graph API as providing paper, author, citation, and reference information and includes Python examples for searching and retrieving papers. citeturn0search0

---

## 2. Crossref API Learning Hub

**Provider:** Crossref  
**Type:** API learning resource  
**Main Topic:** DOI and scholarly metadata retrieval

### Description

Crossref provides an official learning hub for researchers, publishers, and librarians who want to work with Crossref's scholarly metadata API.

The learning resources include:

- API fundamentals
- Postman examples
- Python tutorials
- R tutorials
- Metadata retrieval
- Query construction
- Data analysis
- Data visualization

### Relevance to Citation Drift

Crossref is particularly useful when an AI-generated paper provides a DOI.

A researcher can:

1. Extract the DOI.
2. Query Crossref.
3. Retrieve the official metadata.
4. Compare the result with the AI-generated citation.
5. Flag mismatches.

### Official Resources

- [Crossref API Learning Hub](https://www.crossref.org/learning)
- [Crossref REST API](https://api.crossref.org/)
- [Crossref REST API Documentation](https://www.crossref.org/documentation/retrieve-metadata/rest-api/)

### Verification

Crossref's official learning hub provides API 101 material, Postman resources, Python notebooks, and R notebooks for working with scholarly metadata. citeturn0search13

The official REST API documentation explains how to retrieve metadata for a DOI and search Crossref works. citeturn0search12

---

## 3. OpenAlex API Guides and Recipes

**Provider:** OpenAlex  
**Type:** Scholarly-data API tutorials  
**Main Topic:** Searching and analyzing scholarly works

### Description

OpenAlex provides official API documentation and practical API recipes for querying scholarly works, authors, institutions, sources, topics, and citation relationships.

The tutorials demonstrate operations such as:

- Searching for works
- Filtering by publication year
- Finding open-access papers
- Searching by author
- Sorting by citation count
- Fetching records by DOI
- Following citation relationships
- Batch-fetching records
- Paging through large result sets

### Relevance to Citation Drift

OpenAlex can be used as an independent scholarly metadata source when verifying AI-generated references.

For example:

```text
AI-generated DOI
      |
      v
OpenAlex API
      |
      v
Publication metadata
      |
      v
Compare with AI reference
```

The citation graph can also help investigate references, cited-by relationships, and related scholarly works.

### Official Resources

- [OpenAlex API Reference](https://help.openalex.org/api/)
- [OpenAlex API Recipes](https://help.openalex.org/how-to/api-recipes/)
- [OpenAlex Endpoints](https://help.openalex.org/api/endpoints/)

### Verification

The current OpenAlex API documentation states that the API provides access to works, authors, sources, institutions, topics, and other scholarly entities. It also provides examples for searching, filtering, sorting, and following citations. citeturn0search1turn0search5

---

## 4. GROBID Documentation

**Provider:** GROBID open-source project  
**Type:** Scientific document-processing tutorial/documentation  
**Main Topic:** Extracting structured information from scholarly PDFs

### Description

GROBID documentation explains how to use GROBID to process scientific documents and convert PDF content into structured information.

Relevant capabilities include:

- Scientific PDF parsing
- Bibliographic metadata extraction
- Reference extraction
- Citation extraction
- Citation-context processing
- Structured XML output

### Relevance to Citation Drift

Before a citation can be verified, it needs to be extracted from the AI-generated research paper.

GROBID can therefore be used at the beginning of the citation-integrity pipeline:

```text
PDF research paper
        |
        v
      GROBID
        |
        +--> Bibliography
        |
        +--> Citation callouts
        |
        +--> Citation contexts
        |
        v
Bibliographic verification
```

### Official Resources

- [GROBID GitHub Repository](https://github.com/kermitt2/grobid)
- [GROBID Documentation](https://grobid.readthedocs.io/)

### Learning Value

This resource is particularly useful for learning how unstructured scientific PDFs can be converted into machine-readable bibliographic information.

---

## 5. SciFact Repository and Verification Tutorial

**Provider:** Allen Institute for AI  
**Type:** Scientific claim-verification tutorial/reproducibility resource  
**Main Topic:** Evidence retrieval and scientific claim verification

### Description

The official SciFact repository contains data, models, scripts, evaluation procedures, and documentation for the scientific claim-verification task.

The repository provides instructions for:

- Creating the software environment
- Downloading the dataset
- Downloading pretrained models
- Running rationale-selection models
- Running label-prediction models
- Running complete retrieval-and-verification pipelines
- Reproducing development-set metrics
- Generating claim-verification predictions

### Relevance to Citation Drift

This resource teaches the key concept that is central to the repository:

> A citation should not only exist; its evidence should support the claim associated with it.

SciFact's data schema includes a claim, evidence, SUPPORT/CONTRADICT labels, evidence sentences, and cited document IDs. citeturn0search10

The repository also provides full-pipeline prediction scripts using retrieval and verification models. citeturn0search3turn0search14

### Official Resources

- [SciFact GitHub Repository](https://github.com/allenai/scifact)
- [SciFact Data Documentation](https://github.com/allenai/scifact/blob/master/doc/data.md)
- [SciFact Research Paper](https://aclanthology.org/2020.emnlp-main.609/)

### Learning Value

SciFact provides a practical introduction to:

- Scientific fact checking
- Evidence retrieval
- Claim classification
- Rationale selection
- Citation-context analysis
- Reproducible NLP experiments

---

# Resource Comparison

| Resource | Main Skill | Citation Metadata | PDF Processing | Evidence Verification | Difficulty |
|---|---|---:|---:|---:|---|
| **Semantic Scholar API Tutorial** | Scholarly API use | **Yes** | No | Indirect | Beginner |
| **Crossref API Learning Hub** | DOI/metadata verification | **Yes** | No | Indirect | Beginner–Intermediate |
| **OpenAlex API Guides** | Scholarly data querying | **Yes** | No | Indirect | Intermediate |
| **GROBID Documentation** | Scientific PDF parsing | **Yes** | **Yes** | Indirect | Intermediate |
| **SciFact Repository** | Scientific claim verification | Indirect | No | **Yes** | Intermediate–Advanced |

---

# Suggested Learning Path

A student beginning this research topic can follow these resources in order:

### Step 1 — Learn scholarly metadata APIs

Start with:

- Semantic Scholar API
- Crossref API

Learn how to search for papers and retrieve metadata.

### Step 2 — Learn open scholarly data

Study OpenAlex to understand:

- Works
- Authors
- Sources
- Citation relationships
- API filtering and search

### Step 3 — Learn scientific document extraction

Study GROBID to learn how references and citation contexts can be extracted from research PDFs.

### Step 4 — Learn evidence verification

Study the SciFact repository to understand how a claim can be compared with retrieved scientific evidence.

### Step 5 — Combine the concepts

A complete research workflow can then be designed as:

```text
AI-generated paper
        |
        v
GROBID
        |
        v
Extract citations
        |
        +-----------------------+
        |                       |
        v                       v
   Crossref              Semantic Scholar
        |                       |
        +-----------+-----------+
                    |
                    v
                OpenAlex
                    |
                    v
          Metadata verification
                    |
                    v
             SciFact-style
          claim/evidence check
                    |
                    v
          Citation integrity
               decision
```

---

# Why These Resources Were Selected

The assignment requires authoritative tutorials and learning resources rather than random blog posts or low-quality videos. fileciteturn2file0L62-L63

These five resources were selected because they are maintained by or directly associated with:

- Major scholarly infrastructure providers
- Established research organizations
- Official open-source projects
- Published research projects

They also collectively teach the technical stages required for citation-drift research.

---

# Verification Notes

The Semantic Scholar tutorial is an official API tutorial and includes Python examples, paper search, author lookup, recommendations, and citation/reference access. citeturn0search0

Crossref's official learning hub provides introductory API material, Postman collections, and Python/R tutorials. citeturn0search13

OpenAlex provides official API references and practical recipes for searching works, filtering records, and following citations. citeturn0search1turn0search5

SciFact's official repository provides executable scripts, dataset documentation, models, and instructions for reproducing experiments. citeturn0search3

---

# Responsible Use

Learning resources should be used to understand and reproduce research methods, not to copy research outputs without attribution.

When using external code or datasets:

- Read the license.
- Cite the associated research paper.
- Follow the project's usage requirements.
- Do not claim third-party implementations as original work.
- Keep verification results reproducible.
