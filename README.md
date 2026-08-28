# Awesome Recall Bias in AI Literature Curation

> 🧭 **New here?** Read [Quick Start](#quick-start) → [Topic Overview](#topic-overview) → [Repository Map](#repository-map)

---

## 👋 Welcome — What Is This Repo?

This repository studies a hidden problem in AI research: **automated literature-curation systems tend to over-retrieve highly cited and English-language papers**, while newer, niche, regional, and non-English research gets overlooked.

We provide:
- The original AI-assisted research paper
- A systematic citation-integrity audit (14 references checked)
- Verified scholarly papers organized by theme
- Dataset guides (OpenAlex, Semantic Scholar, S2ORC, OpenCitations, SciFact)
- Tools and libraries for citation analysis
- Verified GitHub implementations
- Beginner tutorials

---

## 🚀 Quick Start (Read This First)

| Step | Action | File / Folder |
|---|---|---|
| 1 | Understand the problem | [Topic Overview](#topic-overview) |
| 2 | Read the original paper | `paper/Ai_Assissted_Research_Paper.pdf` |
| 3 | See how citations were audited | `citation-audit/Citation_Integrity_Audit.pdf` |
| 4 | Browse verified papers by theme | `paper/verified-scholary-papers/` |
| 5 | Learn the basics | `Tutorial/learning resources.md` |
| 6 | Explore datasets | `datasets/` |
| 7 | Check code implementations | `implementations/github-implementations.md` |

---

## 📑 Table of Contents

- [Quick Start](#quick-start-read-this-first)
- [Topic Overview](#topic-overview)
- [AI-Assisted Research Paper](#ai-assisted-research-paper)
- [Citation Integrity Audit](#citation-integrity-audit)
- [Verified Scholarly Papers](#verified-scholarly-papers)
- [Datasets](#datasets)
- [Tools and Libraries](#tools-and-libraries)
- [GitHub Implementations](#github-implementations)
- [Tutorials and Learning Resources](#tutorials-and-learning-resources)
- [Key Research Challenges](#key-research-challenges)
- [Future Directions](#future-directions)
- [Citation Verification Policy](#citation-verification-policy)
- [Repository Map](#repository-map)
- [License](#license)
- [Acknowledgement](#acknowledgement)

---

## 🧠 Topic Overview

### The Problem

AI research is growing faster than any human can read. Researchers rely on:
- Automated search engines
- Systematic-review software
- Large Language Models (LLMs)

These systems inherit biases from the scientific publishing ecosystem:

**Matthew Effect (Citation Bias)**
Already highly cited papers receive greater visibility. Citation counts and algorithmic ranking create a positive feedback loop: visible papers become easier to discover and cite, while less-visible or newer research remains obscured.

**English-Language Bias**
Research published in languages other than English is often underrepresented. English-language restrictions in systematic reviews reduce geographical and cultural diversity in the evidence base.

**LLM Parametric Memory**
LLMs rely on training data that reflects historical citation patterns. This can reproduce citation inequalities and favor highly cited, English-language scholarship.

**Retrieval Database Bias**
Retrieval-Augmented Generation (RAG) can reduce citation hallucination by connecting LLMs to external sources, but the retrieval databases themselves may contain structural biases.

### Why It Matters

If AI curation systems consistently favor the same highly cited, English-language papers, they can:
- Narrow the scope of synthesized evidence
- Hide novel, niche, and regional research
- Reinforce existing academic inequalities
- Reduce the diversity of scientific perspectives

---

## 📄 AI-Assisted Research Paper

**File:** `paper/Ai_Assissted_Research_Paper.pdf`

**Title:** Recall Bias Toward Highly Cited and English Language Papers in AI Literature Curation

**What it covers:**
- How algorithmic search and generative AI exhibit recall bias
- The Matthew Effect in citation networks
- English-language exclusion in systematic reviews
- LLM parametric memory and linguistic hegemony
- Multilingual LLM processing as a potential solution
- Citational justice: increasing visibility of marginalized scholarship

**Key argument:** Automated literature-curation systems can reproduce historical citation inequalities and potentially narrow the scope of synthesized evidence.

**Future directions proposed:**
- Epistemic-parity metrics
- Diverse non-Western scientific corpora
- Citation-inflation-adjusted ranking algorithms

---

## 🔍 Citation Integrity Audit

**File:** `citation-audit/Citation_Integrity_Audit.pdf`

### Why We Audited

The AI-generated research paper contained 14 references. We systematically audited 10 of them to verify:
- Does the publication exist?
- Are the title, authors, year, venue correct?
- Does the citation actually support the claim?

### Audit Results

| Category | Code | Meaning | Count |
|---|---|---|---|
| Verified | A | Source exists, metadata correct, supports claim | 8 |
| Wrong Metadata | B | Source exists but details are wrong | 2 |
| Frankenstein | C | Mixed real and fabricated elements | 0 |
| Fabricated | D | Source does not exist | 0 |
| Identifier Mismatch | E | DOI/arXiv/PMID points to wrong source | 0 |

- **References audited:** 10 of 14
- **Authenticity Score:** 95 / 100
- **Prediction accuracy (before verification):** 80%

### Key Lesson

> Professional-looking citations with DOIs and arXiv IDs still require verification. The presence of a citation does not guarantee the publication exists or supports the associated claim.

---

## 📚 Verified Scholarly Papers

**Location:** `paper/verified-scholary-papers/`

Every paper listed here has been verified for existence, correct metadata, and relevance. Papers are organized into 4 categories:

### 1. Citation Bias (`citation-bias-paper-list.md`)

Papers studying how citation counts, citation patterns, and LLM-based recommendations reproduce or amplify citation inequalities.

**Verified papers include:**

- **Who Gets Recommended? Investigating Gender, Race, and Country Disparities in Paper Recommendations from Large Language Models** (Tian et al., 2025) — LLM recommendations favor higher-citation papers, later publication dates, and larger author teams. [arXiv:2501.00367](https://arxiv.org/abs/2501.00367)
- **Large Language Models Reflect Human Citation Patterns with a Heightened Citation Bias** (Algaba et al., 2024) — LLM-generated citations reproduce human patterns with amplified bias. [arXiv:2405.15739](https://arxiv.org/abs/2405.15739)
- **Citation Accuracy, Citation Noise, and Citation Bias: A Foundation of Citation Analysis** (Bornmann & Leibel, 2025) — Citation counts contain noise and should not be treated as pure quality measures. [arXiv:2508.12735](https://arxiv.org/abs/2508.12735)
- **Viewing Citation Analysis Through the Lens of Citation Justice** (Smith, 2026) — Questions whether citation-based evaluation fairly represents scholarly contributions. [KULA](https://kula.uvic.ca/index.php/kula/article/view/305)
- **Matthew Effects in Science and the Serial Diffusion of Ideas** (Farys & Wolbring, 2021) — Evidence for cumulative citation advantage. [DOI:10.1162/qss_a_00129](https://doi.org/10.1162/qss_a_00129)

### 2. Language Bias (`language-bias-paper-list.md`)

Papers exploring how English-language dominance and exclusion of non-English research affect scientific knowledge and AI systems.

**Verified papers include:**

- **Exploratory Evaluation of Large Language Models for Reducing Language Bias in Systematic Review Screening** (Ikeguchi et al., 2026) — Multilingual LLMs can reduce language-related screening bias. [PubMed](https://pubmed.ncbi.nlm.nih.gov/42393975/)
- **Linguistic Bias in ChatGPT: Language Models Reinforce Dialect Discrimination** (Fleisig et al., 2024) — ChatGPT favors standard English and produces problematic responses for non-standard dialects. [ACL Anthology](https://aclanthology.org/2024.emnlp-main.750/)
- **Addressing Linguistic Bias through a Contrastive Analysis of Academic Writing in the NLP Domain** (Ridley et al., 2023) — Linguistic differences in NLP writing relate to scientific publishing bias. [ACL Anthology](https://aclanthology.org/2023.emnlp-main.1042/)
- **Language Bias in Systematic Reviews: You Only Get Out What You Put In** (Stern & Kleijnen, 2020) — Language restrictions during searching affect which evidence is included. [PubMed](https://pubmed.ncbi.nlm.nih.gov/32925418/)
- **The Prevalence of and Factors Associated with Inclusion of Non-English Language Studies in Campbell Systematic Reviews** (Rasmussen & Montgomery, 2018) — Non-English studies are often underrepresented. [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC6107944/)
- **Cultural Bias and Linguistic Representation in AI Curriculum Design** (Usman et al., 2025) — Cultural and linguistic representation challenges in AI education. [ResearchGate](https://www.researchgate.net/publication/394011793_Cultural_Bias_and_Linguistic_Representation_in_AI_Curriculum_Design_Implications_for_Society_50)

### 3. Methods & Tools (`methods-and-tools-paper-list.md`)

Tools and methods for investigating, evaluating, or reproducing citation behavior in LLM-based systems.

**Verified papers include:**

- **CiteLab: Developing and Diagnosing LLM Citation Generation Workflows via the Human-LLM Interaction** (Shen et al., ACL 2025) — Open-source framework for building and evaluating LLM citation-generation workflows. [ACL Anthology](https://aclanthology.org/2025.acl-demo.47/)

### 4. Surveys & Background (`surveys-and-background-paper-list.md`)

Broader reviews and conceptual papers for understanding bias in AI and LLMs.

**Verified papers include:**

- **Bias in Large Language Models: Origin, Evaluation, and Mitigation** (Guo et al., 2024) — Overview of LLM bias origins, evaluation, and mitigation. [arXiv:2411.10915](https://arxiv.org/abs/2411.10915)
- **Bias Is a Math Problem, AI Bias Is a Technical Problem: 10-Year Literature Review of AI/LLM Bias Research** (Ghosh & Wilson, 2025) — A decade of AI/LLM bias research and remaining gaps. [AAAI AIES](https://ojs.aaai.org/index.php/AIES/article/view/36613)

---

## 📊 Datasets

**Location:** `datasets/`

This directory does not redistribute full datasets (due to size and licensing). Instead, it provides guides, descriptions, and official access links.

### Dataset Guide (`datasets/README.MD`)

| Dataset | Source | What It Contains | Why It Matters for This Repo | Access |
|---|---|---|---|---|
| **OpenAlex** | OpenAlex | Works, authors, sources, institutions, topics, citation connections | Analyze citation counts, highly cited vs. low-citation papers, publication patterns | https://openalex.org/ |
| **Semantic Scholar Academic Graph** | Semantic Scholar | Papers, authors, abstracts, citations, recommendations | Study citation networks and recommendation patterns | https://www.semanticscholar.org/ |
| **S2ORC** | Allen Institute for AI | Scientific-paper corpus with metadata, references, structured text | Citation-context analysis, literature retrieval experiments | https://github.com/allenai/s2orc |
| **OpenCitations** | OpenCitations | Open citation data and citation relationships | Study citation networks and the Matthew Effect | https://opencitations.net/ |
| **SciFact** | Allen Institute for AI | Scientific claims with evidence-containing abstracts and verification labels | Study whether cited/retrieved papers actually support claims | https://github.com/allenai/scifact |

### Subfolder Details

- `datasets/openalex/` — Guide to using OpenAlex for citation-bias analysis (citation count distribution, highly cited vs. low-citation papers, publication year, venues, authors, institutions, topics, citation relationships)
- `datasets/s2orc/` — Guide to S2ORC for citation-context analysis, reference analysis, scientific text mining, and literature retrieval experiments. Note: S2ORC should not be treated as the only dataset for measuring English-language bias; multilingual comparison requires additional sources.
- `datasets/semantic-scholar/` — Guide to Semantic Scholar Academic Graph for citation networks, highly cited vs. less-cited comparisons, paper visibility, recommendation patterns, and author relationships.

---

## 🛠️ Tools and Libraries

**Location:** `tools/tools-and-libraries.md`

### 1. OpenAlex
- **Type:** Scholarly Data API
- **Use:** Find papers, collect citation counts, explore authors/institutions, build citation datasets
- **Link:** https://openalex.mintlify.app/

### 2. Semantic Scholar API
- **Type:** Scholarly Search & Citation API
- **Use:** Search papers, retrieve metadata, explore citations/references, study recommendations
- **Link:** https://www.semanticscholar.org/product/api

### 3. OpenCitations
- **Type:** Open Citation Database & API
- **Use:** Citation counts, citation networks, finding citing/cited papers
- **Link:** https://opencitations.net/

### 4. Bibliometrix / Biblioshiny
- **Type:** Bibliometric Analysis Tool (R package + GUI)
- **Use:** Citation analysis, co-citation, bibliographic coupling, co-authorship networks, keyword analysis, science mapping
- **Link:** https://www.bibliometrix.org/

### 5. CiteLab
- **Type:** LLM Citation Research Toolkit
- **Use:** Build, evaluate, and diagnose LLM citation-generation workflows
- **Link:** See `implementations/github-implementations.md`

---

## 💻 GitHub Implementations

**Location:** `implementations/github-implementations.md`

These repositories were selected based on quality, documentation, maintenance, reproducibility, and direct relevance to this topic — not just star count.

### Selection Criteria
- Documentation quality
- Source code clarity
- Recent maintenance
- Examples / notebooks / tutorials
- Reproducibility
- Clear open-source license
- Connection to a research paper or recognized project

### Verified Implementations

| # | Project | Focus | Why It Matters | Link |
|---|---|---|---|---|
| 1 | **LLMScholarBench** | LLM scholar recommendation auditing | Audits whether LLM recommendations show systematic bias | https://github.com/CSHVienna/LLMScholarBench |
| 2 | **LitSearch** | Scientific literature retrieval | Retrieval bias affects which papers are considered | https://github.com/princeton-nlp/LitSearch |
| 3 | **CiteGen** | Context-aware citation recommendation | Citation recommendations influence visibility | https://github.com/Marcomurgia97/CiteGen-An-LLM-Based-System-for-Context-Aware-Citation-Recommendation |
| 4 | **ScholarLoop** | Evidence-grounded academic search | Combines retrieval, ranking, evidence, and verification | https://github.com/124-creator/ScholarLoop |
| 5 | **LOBSTER** | Language-of-study bias in peer review | Studies language-related bias in scientific workflows | https://github.com/GGLAB-KU/LOBSTER |
| 6 | **LLM Review Bias** | Bias in LLM-assisted peer review | Shows how researcher/paper characteristics influence AI evaluation | https://github.com/ivaxi0s/llm-review-bias |
| 7 | **LLMRanker** | LLM-based ranking | Ranking bias determines which papers appear at the top | https://github.com/shangeth/llmranker |

### How They Fit Together

A simplified AI literature-curation pipeline:

```
User / Research Question
         │
         ▼
  Literature Retrieval  →  LitSearch, OpenAlex
         │
         ▼
      Ranking  →  LLMRanker
         │
         ▼
  Citation Recommendation  →  CiteGen
         │
         ▼
  Scholar Recommendation  →  LLMScholarBench
         │
         ▼
  Bias Evaluation  →  LOBSTER (language), Citation Bias studies
```

---

## 📖 Tutorials and Learning Resources

**Location:** `Tutorial/learning resources.md`

### For Complete Beginners

**Suggested learning path:**

1. **Bibliometrics** (NIH Library) — What citation analysis is and why it matters
2. **Leiden Manifesto** — 10 principles for responsible use of research metrics
3. **Cochrane Handbook** — Systematic literature searching and selection (includes language/publication bias)
4. **DORA** — Responsible use of quantitative indicators (citation counts, h-index, journal metrics)
5. **OpenAlex** — How to use open scholarly data for exploration

### Why These Resources?

- They explain the concepts behind this repository without requiring advanced statistics.
- They emphasize that citation counts are not pure quality measures.
- They show how language restrictions can change which evidence is included.
- They provide practical guides for using open scholarly data.

---

## ⚠️ Key Research Challenges

### Citation Noise vs. Citation Bias
Reducing the influence of highly cited papers may unintentionally increase citation noise — retrieving lower-quality or irrelevant research. The challenge is to improve diversity without sacrificing quality.

### Data Opacity and RLHF
Many LLMs are proprietary. Their training data is difficult to examine. Additionally, Reinforcement Learning from Human Feedback (RLHF) often involves English-speaking annotators, which may reinforce Standard English preferences.

### Retrieval Database Bias
RAG connects LLMs to external sources, reducing hallucination. But if the retrieval database itself is biased (e.g., over-represents English-language, highly cited papers), the output will still be biased.

---

## 🚀 Future Directions

Based on the research paper and audit findings:

- **Quantitative measures of epistemic parity** — How fairly does a curation system represent different research communities?
- **Non-Western and non-English scientific literature** — Increasing representation in AI training and retrieval corpora.
- **Diverse scientific corpora** — Building training and retrieval datasets that include underrepresented regions and languages.
- **Citation-inflation-adjusted ranking algorithms** — Ranking methods that account for cumulative citation advantage.
- **Discoverability of high-quality, low-citation research** — Improving visibility without relying solely on citation counts.
- **Bias-aware and diversity-aware curation systems** — Designing systems that actively measure and mitigate bias.

---

## ✅ Citation Verification Policy

This repository follows a **verification-first** approach.

### Before Adding Any Reference

Check:
- [ ] Publication exists (search publisher, official repository, or persistent identifier)
- [ ] Title is correct
- [ ] Authors are correct
- [ ] Publication year is correct
- [ ] Journal / conference / source is correct
- [ ] Volume, issue, pages (if applicable) are correct
- [ ] DOI, arXiv ID, or PMID is correct and points to the right source
- [ ] The source actually supports the claim for which it is cited

### Verification Sources (Preferred Order)

1. Publisher or official repository records
2. Persistent identifiers (DOI, arXiv, PMID)
3. Google Scholar
4. Semantic Scholar / OpenAlex
5. Crossref / PubMed
6. Exact-title searches
7. Author / title-keyword searches

> ⚠️ **Important:** A ResearchGate page can help discover a paper, but an official publisher, journal, conference, DOI, or repository record should be preferred for verification.

---

## 🗺️ Repository Map

```
awesome-ai-literature-curation-bias/
│
├── README.md                          # This file — start here!
├── LICENSE
│
├── Tutorial/                          # Beginner learning guides
│   └── learning resources.md
│
├── citation-audit/                    # Citation audit files
│   └── Citation_Integrity_Audit.pdf
│
├── datasets/                          # Dataset guides (not full data)
│   ├── README.MD                      # Overview of all datasets
│   ├── openalex/                      # OpenAlex guide
│   ├── s2orc/                         # S2ORC guide
│   └── semantic-scholar/              # Semantic Scholar guide
│
├── implementations/                   # Verified code implementations
│   └── github-implementations.md
│
├── paper/                             # Original research paper
│   ├── Ai_Assissted_Research_Paper.pdf
│   └── verified-scholary-papers/      # Verified papers by theme
│       ├── citation-bias-paper-list.md
│       ├── language-bias-paper-list.md
│       ├── methods-and-tools-paper-list.md
│       ├── surveys-and-background-paper-list.md
│       └── VERIFICATION-REQUIREMENTS.md
│
├── references/                        # Reference tracking (empty — add verified refs)
│   └── .gitkeep
│
└── tools/                             # Tools and libraries notes
    └── tools-and-libraries.md
```

---

## 📜 License

This repository contains student-created curation and documentation based on the AI-assisted research paper and citation-integrity audit.

Unless another license is specified, the repository's original organizational material and documentation may be released under the **MIT License**.

The original scholarly works referenced by the research paper remain subject to their respective copyright and licensing terms.

---

## 🙏 Acknowledgement

This repository was created as part of the **AI Tools for Research** laboratory activity. The assigned topic was:

> "Recall Bias Toward Highly Cited and English Language Papers in AI Literature Curation."

The citation audit used a systematic sampling and verification procedure and emphasizes the importance of **human verification** of AI-generated scholarly references.

---

*Questions? Open an Issue or check the [Tutorials](Tutorial/) first!*
