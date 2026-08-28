# Awesome Recall Bias in AI Literature Curation

> A curated research repository on recall bias toward highly cited and English-language papers in AI literature curation.

## Table of Contents

* [Topic Overview](#topic-overview)
* [AI-Assisted Research Paper](#ai-assisted-research-paper)
* [Citation Integrity Audit](#citation-integrity-audit)
* [Curated Research Papers](#curated-research-papers)
* [Datasets](#datasets)
* [Tools and Libraries](#tools-and-libraries)
* [GitHub Implementations](#github-implementations)
* [Tutorials and Learning Resources](#tutorials-and-learning-resources)
* [License](#license)

---

## Topic Overview

The rapid growth of Artificial Intelligence (AI) research has made traditional manual literature review increasingly difficult. Researchers now rely on automated search systems, systematic-review software, and Large Language Models (LLMs) to discover and curate scientific literature. However, these systems can inherit and amplify biases present in the existing scientific publishing ecosystem.

This repository focuses on **recall bias toward highly cited and English-language papers in AI literature curation**. The research paper identifies two major dimensions of this problem: the **Matthew Effect**, where already highly cited and established papers receive greater visibility, and **English-language bias**, where research published in languages other than English may be underrepresented. Such biases can reduce the visibility of novel, niche, regional, and non-English research.

The paper also discusses how LLMs may reinforce citation inequalities through their parametric knowledge and how retrieval systems can inherit biases from the databases on which they depend. Multilingual LLM processing is presented as a potential way to reduce language-related exclusion.

Future directions include developing metrics for linguistic and demographic representation, creating more diverse scientific corpora, and designing citation-inflation-adjusted ranking methods that can improve the discoverability of underrepresented research.

---

## AI-Assisted Research Paper

### Paper Title

**Recall Bias Toward Highly Cited and English Language Papers in AI Literature Curation**

### Description

The research paper investigates how traditional algorithmic search engines and modern generative AI systems can exhibit recall bias toward highly cited and English-language scholarship. It discusses the Matthew Effect, English-language bias, LLM parametric memory, linguistic hegemony, multilingual processing, and citational justice.

The paper argues that automated literature-curation systems can reproduce historical citation inequalities and potentially narrow the scope of synthesized evidence. It also identifies future research directions including epistemic-parity metrics, diverse non-Western scientific corpora, and citation-inflation-adjusted ranking algorithms.

### Repository Link

**Paper:** `Ai_Assissted_Research_Paper.pdf`

> Add the GitHub-relative path to the paper here after uploading it to the repository, for example:
>
> `docs/Ai_Assissted_Research_Paper.pdf`

---

## Citation Integrity Audit

The AI-generated research paper was subjected to a systematic citation-integrity audit. The audit examined whether cited publications existed, whether their metadata and identifiers were correct, and whether the references could support the claims for which they were cited. The audit emphasizes that the presence of a citation does not itself guarantee that the publication exists or that it supports the associated claim.

A total of **14 references** appeared in the AI-generated paper, of which **10 references were systematically audited**. The audit classified:

* **8 references** as Verified (A)
* **2 references** as Wrong Metadata (B)
* **0 references** as Frankenstein (C)
* **0 references** as Fabricated (D)
* **0 references** as Identifier Mismatch (E)

The resulting **Authenticity Score was 95/100**, while the prediction accuracy before verification was **80%**.

The audit also concluded that professional-looking citations still require verification and highlighted the importance of keeping a **human in the loop** when evaluating AI-generated scholarly references.

### Audit Report

**Citation Integrity Audit:** `Citation_Integrity_Audit.pdf`

> Add the GitHub-relative path after uploading it, for example:
>
> `docs/Citation_Integrity_Audit.pdf`

---

## Curated Research Papers

The research paper identifies several important research directions related to recall bias, citation bias, language bias, systematic reviews, multilingual LLMs, and citation justice.

### 1. Citation Bias and the Matthew Effect

Research in this category concerns the cumulative advantage of highly cited and established scientific works. The paper describes how citation counts and algorithmic ranking can create a positive feedback loop in which already-visible papers become easier to discover and cite, while less-visible or newer research can remain obscured.

### 2. English-Language and Linguistic Bias

This category focuses on the exclusion or reduced visibility of research published in languages other than English. The paper discusses how English-language restrictions in systematic reviews can reduce geographical and cultural diversity in the evidence base.

### 3. LLMs and Literature Curation

This category covers the role of Large Language Models in literature discovery and recommendation. The paper discusses how LLMs relying on parametric knowledge may reproduce citation inequalities and favor highly cited research.

### 4. Multilingual Literature Screening

This category focuses on multilingual LLMs as a possible method for reducing language-related bias. The paper discusses direct multilingual processing as an alternative to translating non-English abstracts before screening.

### 5. Citational Justice

Citational justice focuses on deliberately increasing the visibility of research from marginalized scholars, non-English-speaking regions, and underrepresented institutions. The paper connects this idea to diversity-aware literature recommendation and curation systems.

### Papers Identified in the Research Paper

The original AI-assisted paper contains **14 references**. The repository should preserve these references as the initial research collection and organize them according to the categories above.

> **Curation note:** References should be added to this repository only after their authenticity and bibliographic details have been checked using the citation-integrity procedure.

---

## Datasets

The two provided documents do not identify a specific dataset dedicated to studying recall bias toward highly cited and English-language papers.

Therefore, no external dataset is listed here without additional source material.

Potential dataset requirements identified by the research topic include information that can be used to study:

* Citation counts
* Publication language
* Publication year
* Research venue
* Geographic representation
* Retrieval or recommendation frequency
* Representation of low-citation and non-English research

---

## Tools and Libraries

The provided documents discuss several types of tools and systems involved in AI literature curation, including:

* Large Language Models (LLMs)
* Automated search algorithms
* Systematic-review software
* Retrieval-Augmented Generation (RAG)
* Scholarly literature databases
* Citation-based ranking and recommendation systems

The research paper specifically notes that RAG can help anchor LLM outputs to external databases, although the databases themselves may contain structural biases.

> **Note:** Specific software libraries are not identified in the provided documents, so no external libraries are added to this README.

---

## GitHub Implementations

The provided research paper and citation audit do not identify specific GitHub repositories or implementations for this topic.

This section can be expanded later with verified implementations related to:

* AI literature retrieval
* Citation recommendation
* Multilingual information retrieval
* LLM-based literature screening
* Bias-aware recommendation
* Diversity-aware literature curation

> Only implementations that are directly relevant and verified should be added.

---

## Tutorials and Learning Resources

The provided documents identify several methodological areas that are useful for understanding this topic:

1. **Systematic Literature Reviews**
   Understanding how literature is searched, screened, and selected.

2. **Citation Analysis and Scientometrics**
   Understanding citation distributions, citation bias, and cumulative advantage.

3. **Large Language Models for Literature Curation**
   Understanding how LLMs can assist with literature discovery and synthesis.

4. **Multilingual Literature Screening**
   Understanding how multilingual processing can reduce translation-related sensitivity loss.

5. **Citation Integrity Verification**
   Checking publication existence, metadata, identifiers, and claim-citation relationships.

The citation audit recommends verification using persistent identifiers, publisher or official repository records, Google Scholar, Semantic Scholar/OpenAlex, Crossref, PubMed, exact-title searches, and author/title-keyword searches.

---

## Key Research Challenges

The research paper identifies several challenges that remain important for AI literature curation:

### Citation Noise vs. Citation Bias

Reducing the influence of highly cited papers may unintentionally increase citation noise and result in the retrieval of lower-quality or irrelevant research.

### Data Opacity and RLHF

The proprietary nature of many LLMs makes their training data difficult to examine. The paper also discusses how English-speaking annotators involved in RLHF may reinforce Standard English preferences.

### Retrieval Database Bias

RAG can reduce citation hallucination by connecting an LLM to external sources, but biased retrieval databases can still produce biased literature collections.

---

## Future Directions

The research paper proposes several directions for future research:

* Developing quantitative measures of **epistemic parity**
* Increasing representation of non-Western and non-English scientific literature
* Building diverse scientific corpora for AI training
* Developing **citation-inflation-adjusted ranking algorithms**
* Improving the discoverability of high-quality, low-citation research
* Developing bias-aware and diversity-aware literature-curation systems

---

## Citation Verification Policy

This repository follows a verification-first approach to scholarly references.

A citation should not be considered trustworthy simply because it looks professional or contains a DOI, arXiv ID, or other identifier. References should be checked for:

* Publication existence
* Correct title
* Correct authors
* Correct publication year
* Correct journal/conference/source
* Correct volume, issue, and pages where applicable
* Correct DOI, arXiv ID, or PMID

The citation audit classifies references using the following categories:

| Code  | Meaning             |
| ----- | ------------------- |
| **A** | Verified            |
| **B** | Wrong Metadata      |
| **C** | Frankenstein        |
| **D** | Fabricated          |
| **E** | Identifier Mismatch |

These categories are defined in the citation-integrity audit methodology.

---

## Repository Structure

```text
awesome-recall-bias-ai-literature/
│
├── README.md
│
├── papers/
│   └── Ai_Assissted_Research_Paper.pdf
│
├── audit/
│   └── Citation_Integrity_Audit.pdf
│
├── curated-papers/
│   ├── citation-bias/
│   ├── language-bias/
│   ├── multilingual-curation/
│   ├── llm-literature-curation/
│   └── citational-justice/
│
├── datasets/
│
├── tools/
│
├── implementations/
│
└── tutorials/
```

---

## License

This repository contains student-created curation and documentation based on the provided AI-assisted research paper and citation-integrity audit.

Unless another license is specified in the repository, the repository's original organizational material and documentation may be released under the **MIT License**.

The original scholarly works referenced by the research paper remain subject to their respective copyright and licensing terms.

---

## Acknowledgement

This repository was created as part of the **AI Tools for Research** laboratory activity. The assigned topic was:

**“Recall Bias Toward Highly Cited and English Language Papers in AI Literature Curation.”**

The accompanying citation audit used a systematic sampling and verification procedure and emphasizes the importance of human verification of AI-generated scholarly references.

---

## Central Idea

> **Does the source exist, and does the source actually support the claim?**

The citation-integrity workflow used in the audit can be summarized as:

**AI Generation → Reference Inventory → Systematic Sampling → Prediction → Authenticity Verification → Claim-Support Verification → Quantitative Scores → Submission**
