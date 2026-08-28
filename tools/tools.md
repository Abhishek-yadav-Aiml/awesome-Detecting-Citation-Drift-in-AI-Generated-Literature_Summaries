# Tools and Libraries

This file lists tools and libraries that can support research on **detecting citation drift in AI-generated literature summaries**.

The selected tools cover complementary stages of a citation-integrity workflow:

```text
AI-generated paper
       |
       v
Reference extraction
       |
     GROBID
       |
       v
Bibliographic lookup
       |
  Crossref / OpenAlex / Semantic Scholar
       |
       v
Metadata comparison
       |
       v
Citation verification
```

---

## 1. GROBID

**Full Name:** GeneRation Of BIbliographic Data  
**Type:** Open-source machine-learning library  
**Primary Use:** Scientific PDF parsing and bibliographic reference extraction

### Purpose

GROBID extracts and structures information from scholarly documents, especially scientific PDFs. It can identify:

- Paper titles
- Authors
- Abstracts
- Bibliographic metadata
- References
- Citation callouts
- DOI and PMID information
- Sections and paragraphs
- Figures and tables

It can also recognize citation contexts and associate citation callouts with bibliographic references.

### Relevance to Citation Drift

A citation-drift detection system first needs to reliably extract references and citation contexts from a research paper. GROBID can provide this structured input before the references are checked against scholarly databases.

### Official Resources

- [Official GitHub Repository](https://github.com/grobidOrg/grobid)
- [Official Documentation](https://grobid.readthedocs.io/)

### License

Apache License 2.0.

### Verification

The official GROBID repository describes it as a machine-learning software for extracting, parsing, and restructuring scientific documents, including bibliographic references and citation contexts. It also documents integration with Crossref for bibliographic resolution. citeturn0search2turn0search8

---

## 2. Semantic Scholar

**Type:** Scholarly literature search and research-discovery platform  
**Provider:** Allen Institute for AI

### Purpose

Semantic Scholar provides access to scholarly literature and research metadata. It can be used to search for papers and inspect information such as:

- Paper title
- Authors
- Publication year
- Venue
- Abstract
- Citations
- References
- Related papers
- Research topics

Semantic Scholar also provides an API for programmatic access to scholarly metadata.

### Relevance to Citation Drift

Semantic Scholar can be used as an independent scholarly source for checking whether an AI-generated citation exists and whether its bibliographic metadata matches the generated reference.

It can also help discover related research papers that belong in the curated repository.

### Official Resources

- [Semantic Scholar](https://www.semanticscholar.org/)
- [Semantic Scholar API](https://www.semanticscholar.org/product/api)

### Recommended Use

For each AI-generated citation:

1. Search the exact title.
2. Compare authors.
3. Compare publication year.
4. Compare venue.
5. Compare DOI where available.
6. Record discrepancies.

---

## 3. OpenAlex

**Type:** Open scholarly metadata and research-discovery infrastructure

### Purpose

OpenAlex provides a large, open catalog of scholarly works, authors, institutions, sources, topics, and citations.

It can be used to:

- Search scholarly works
- Resolve paper metadata
- Find authors
- Explore citation relationships
- Identify related papers
- Retrieve persistent identifiers
- Support bibliometric analysis

### Relevance to Citation Drift

OpenAlex is useful as an independent metadata source when checking AI-generated references. Comparing an AI-generated citation against OpenAlex can reveal incorrect titles, authors, years, venues, or identifiers.

Its citation graph can also help investigate whether references and related works are connected in the scholarly literature.

### Official Resources

- [OpenAlex](https://openalex.org/)
- [OpenAlex API Documentation](https://docs.openalex.org/)

### Recommended Use

Use OpenAlex as a secondary verification source alongside Crossref and Semantic Scholar rather than treating any single database as automatically authoritative.

---

## 4. Crossref

**Type:** Scholarly metadata and DOI infrastructure

### Purpose

Crossref provides metadata for scholarly publications and is one of the most useful sources for DOI-based reference verification.

It can help retrieve:

- DOI
- Title
- Authors
- Publication date
- Journal or conference information
- Volume
- Issue
- Page information
- Publisher
- Reference metadata where available

### Relevance to Citation Drift

A major problem in AI-generated research papers is incorrect or fabricated DOI information. Crossref can be used to resolve a DOI and determine whether it belongs to the claimed publication.

For a citation audit, Crossref is particularly useful for checking:

```text
AI-generated citation
        |
        v
      DOI
        |
        v
Crossref metadata
        |
        v
Compare:
Title + Authors + Year + Venue
```

### Official Resources

- [Crossref](https://www.crossref.org/)
- [Crossref REST API](https://api.crossref.org/)

### Recommended Use

When an AI-generated reference contains a DOI, resolve the DOI through Crossref and compare the returned metadata with the reference.

---

## 5. xRef

**Type:** Reference-verification tool  
**Developer:** kazilab

### Purpose

xRef is a lightweight reference-verification application designed to check bibliography metadata against multiple scholarly databases.

According to its project documentation, it can compare reference information against:

- DOI.org
- PubMed
- Europe PMC
- Crossref
- OpenAlex
- Semantic Scholar

It checks fields such as:

- Authors
- Title
- Journal
- Year
- Volume
- Issue
- Pages
- DOI
- PMID

### Relevance to Citation Drift

xRef is directly relevant to this repository because it automates several of the metadata checks required in the earlier citation-integrity audit.

It can help identify:

- Fabricated references
- Wrong authors
- Wrong titles
- Incorrect publication years
- Incorrect DOI values
- Metadata mismatches

### Official Resource

- [xRef GitHub Repository](https://github.com/kazilab/xRef)

### License

MIT License.

### Verification

The project's official GitHub documentation describes xRef as a reference-verification system that cross-checks bibliography metadata against multiple scholarly databases and compares nine bibliographic fields. citeturn0search3

---

# Tool Comparison

| Tool | Primary Function | Citation Verification | PDF Parsing | Metadata Search | Citation-Drift Relevance |
|---|---|---:|---:|---:|---:|
| **GROBID** | Scientific PDF/reference extraction | Yes | **Yes** | Limited | **Very High** |
| **Semantic Scholar** | Scholarly search and metadata | **Yes** | No | **Yes** | **Very High** |
| **OpenAlex** | Open scholarly metadata | **Yes** | No | **Yes** | **Very High** |
| **Crossref** | DOI and publication metadata | **Yes** | No | **Yes** | **Very High** |
| **xRef** | Automated reference verification | **Yes** | No | **Yes** | **Very High** |

---

# Suggested Verification Workflow

These tools can be combined into a practical citation-integrity workflow:

### Step 1 — Extract references

Use **GROBID** to extract references and citation contexts from the AI-generated paper.

### Step 2 — Search scholarly databases

Search the extracted reference using:

- Semantic Scholar
- OpenAlex
- Crossref

### Step 3 — Compare metadata

Compare:

- Title
- Authors
- Year
- Journal/conference
- Volume/issue/pages
- DOI or other persistent identifier

### Step 4 — Automate metadata checks

Use **xRef** to cross-check bibliography fields against several scholarly databases.

### Step 5 — Verify claim support

Metadata verification alone is not enough. A publication can exist while still failing to support the claim attached to it.

Therefore, the final stage should inspect the actual cited paper and determine whether its evidence supports the generated claim.

---

# Selection Criteria

Tools were selected using the following criteria:

1. Relevance to scholarly research.
2. Ability to support citation or metadata verification.
3. Official documentation or project page.
4. Clear research application.
5. Practical usefulness for the citation-drift problem.
6. Ability to complement the other tools in the repository.

---

# Important Limitation

No single tool should be treated as absolute proof that a citation is genuine.

A robust verification process should use multiple independent sources and, when necessary, inspect the original publisher or scholarly record.

This follows the central principle of the assignment:

> **AI may help discover a resource, but the researcher is responsible for verifying it.**

