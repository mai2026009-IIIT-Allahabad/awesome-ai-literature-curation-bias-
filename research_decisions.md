# Research Decisions Log

**Project:** AI Tools for Research — Post-Mid-Semester Experimental Paper  
**Student:** Rohit Mahali (MAI2026009)  
**Date opened:** 2026-10-21  
**Status:** G1 scoping; no experiment has been run yet.

## 1. Workspace purpose

This is the accountable workspace for turning the prior review into a focused implementation study. It follows the assigned research sequence: review evidence → verified gap → question → baseline → validation → experiment → evidence → paper → reproduction. No result, metric, plot, or execution is claimed until it is generated and checked from an actual run.

## 2. Topic and review scope

**[VERIFIED — from the submitted review]** The previous paper is titled *Recall Bias Toward Highly Cited and English Language Papers in AI Literature Curation*. It argues that AI-assisted literature discovery, screening, and synthesis may under-retrieve relevant research through two broad mechanisms:

1. **Citation visibility / cumulative advantage:** widely cited papers can be easier to discover or more likely to be recommended.
2. **Language-related exclusion:** database coverage, language restrictions, translation, linguistic representation, and model processing can reduce the visibility or inclusion of non-English research.

The review's structure covers:

- **Section 2:** the Matthew Effect and language restrictions in systematic reviews.
- **Section 3.1:** parametric LLM memory and citation-pattern amplification.
- **Section 3.2:** linguistic hegemony and Standard Language Ideology.
- **Section 4.1:** direct multilingual LLM screening versus translation-mediated screening.
- **Section 4.2:** citational justice.
- **Section 5:** citation noise versus citation bias, model/data opacity, and RAG's dependence on its retrieval corpus.
- **Section 6:** representation metrics, non-Western corpora, and citation-adjusted ranking.

**[VERIFIED — scope limitation]** The previous paper is a narrative review. It does not document a reproducible database search, search dates, inclusion/exclusion criteria, a screened-record count, or a systematic evidence-extraction table. It is useful for identifying candidate questions, but it is not itself enough to substantiate novelty or all factual claims.

## 3. Initial evidence ledger

Use the following statuses throughout this project:

- **VERIFIED:** confirmed in the supplied review, checked against a primary publication/official dataset page, or observed in a genuine execution log.
- **INFERRED:** a reasoned candidate interpretation or proposed experiment that still needs testing.
- **UNKNOWN:** not established by the available evidence.

### Verified source-level anchors checked on 2026-10-21

1. **Algaba et al. (2025), “Large Language Models Reflect Human Citation Patterns with a Heightened Citation Bias.”** The official ACL Anthology record confirms a Findings of NAACL 2025 paper. Its abstract reports stronger high-citation bias in parametric LLM citation recommendations, remaining after controls for year, title length, author count, and venue. This supports the prior review's citation-visibility theme, but the experiment is about citation recommendation from parametric knowledge, not a general proof about every retrieval pipeline. https://aclanthology.org/2025.findings-naacl.381/
2. **Tian et al. (2024 preprint), “Who Gets Recommended? Investigating Gender, Race, and Country Disparities in Paper Recommendations from Large Language Models.”** The arXiv record reports tendencies toward recommending papers with higher citation counts, later dates, and larger author teams; it also reports no evidence of a corresponding disproportionate recommendation of male, white, or developed-country authors in its scholar-recommendation task. This result cautions against treating all forms of bias as interchangeable. https://arxiv.org/abs/2501.00367
3. **Ridley et al. (2023), “Addressing Linguistic Bias through a Contrastive Analysis of Academic Writing in the NLP Domain.”** The official ACL Anthology record confirms an EMNLP 2023 paper analyzing measurable linguistic differences in NLP paper abstracts across author linguistic backgrounds. It supports studying linguistic variation in scholarly communication, but it does not, by itself, establish that a retrieval model misses those abstracts. https://aclanthology.org/2023.emnlp-main.1042/
4. **Stern and Kleijnen (2020), “Language bias in systematic reviews: you only get out what you put in.”** PubMed confirms authors, venue, year, and DOI. https://pubmed.ncbi.nlm.nih.gov/32925418/
5. **Neimann Rasmussen and Montgomery (2018), “The prevalence of and factors associated with inclusion of non-English language studies in Campbell systematic reviews.”** The journal page identifies a survey/meta-epidemiological study of 123 Campbell Collaboration reviews. https://doi.org/10.1186/s13643-018-0786-6
6. **Ikeguchi, Ueshima, and Tamura (2026), “Exploratory Evaluation of Large Language Models for Reducing Language Bias in Systematic Review Screening.”** PubMed confirms a study with 2,911 English records and 483 non-English abstracts, evaluating six LLMs. The abstract reports translation-mediated sensitivity of 0.47–0.54 for some models versus 0.71–1.00 with direct multilingual processing and says downstream meta-analytic effects require further investigation. https://pubmed.ncbi.nlm.nih.gov/42393975/
7. **Valentini, Kozlowski, and Lariviere (2025), “CLIRudit: Cross-Lingual Information Retrieval of Scientific Documents.”** The ACL Anthology confirms an English-query/French-document scholarly retrieval dataset and a comparison of sparse/dense retrieval and translation. The dataset card says queries are combinations of English author keywords; relevance judgments derive from article keyword metadata. The dataset is public under CC BY-NC 4.0. This is useful infrastructure, but its query/qrel design limits the claims it can support without an extension. https://aclanthology.org/2025.mrl-main.16/ and https://huggingface.co/datasets/ftvalentini/clirudit
8. **Yang, Jiang, and Baldwin (2024), “Language Bias in Multilingual Information Retrieval: The Nature of the Beast and Mitigation Methods.”** The official ACL Anthology record describes same-semantic queries in different languages, ranking consistency, and a mitigation loss (LaKDA). Therefore, language fairness in multilingual IR is already an established research area. https://aclanthology.org/2024.mrl-1.23/
9. **Wang et al. (2026), “All Languages Matter: Understanding and Mitigating Language Bias in Multilingual RAG.”** The official ACL record studies language bias at reranking in multilingual RAG and proposes LAURA. Thus, a generic “language bias in mRAG” claim would not be a defensible novelty statement. https://aclanthology.org/2026.acl-long.338/
10. **Ki et al. (2026), “Linguistic Nepotism: Trading-off Quality for Language Preference in Multilingual RAG.”** The ICML/PMLR record describes a controlled methodology holding document relevance constant and tests eight languages and six open-weight models. It reports language preference and cases where relevance is traded off for language preference. This is close prior work that must be read carefully before claiming a new counterfactual language-bias method. https://proceedings.mlr.press/v306/ki26a.html
11. **Macmillan-Scott, Goworek, and Özyiğit (2025), “Generative Query Expansion with Multilingual LLMs for Cross-Lingual Information Retrieval.”** The arXiv record already compares multilingual query-expansion approaches, query lengths, and language pairs. A broad query-expansion study would therefore overlap with existing work. https://arxiv.org/abs/2511.19325
12. **Genovese et al. (2025), “From Data to Decisions: Leveraging Retrieval-Augmented Generation to Balance Citation Bias in Burn Management Literature.”** PubMed identifies a study comparing RAG with high- versus lower-citation clinical source sets. It reports similar performance on its accuracy, readability, and response-time measures in that specific burn-management setting. This means citation count in RAG is not entirely unexplored; our study would need a distinct domain, mechanism, evaluation, or method. https://pubmed.ncbi.nlm.nih.gov/40558623/

## 4. Bibliography and claim audit from the prior review

The reference list in the prior review must not be copied forward without repair. During this initial check:

- **[1] Algaba et al.:** the source record is verified, but the prior bibliography's 2024 year and placeholder/incomplete arXiv identifier should be replaced with the official NAACL 2025 record if this source is used.
- **[5] multilingual screening:** verified as Ikeguchi, Ueshima, and Tamura (2026); cite these original authors rather than institutional names.
- **[7] attribution mismatch:** the text calls the result “Petiska’s study,” while the bibliography describes Petiska as “Discussed in” *Who Gets Recommended?*; the primary paper's authors are Tian, Liu, Bu, and Liu. This needs correction before reuse.
- **[8] Ridley et al.:** verified record is EMNLP 2023, pages 16765–16779, DOI 10.18653/v1/2023.emnlp-main.1042. Its measured topic is writing variation/linguistic bias, not direct search recall.
- **[9] and [14]:** verified sources for language bias and non-English review inclusion, respectively. The prior manuscript's Section 2.2 makes related claims without visible inline citation markers; those claims should be cited directly if retained.
- **[2], [3], [4], [6], [10], [11], [12], [13]:** the prior bibliography information is incomplete, secondary, placeholder-based, or not yet verified against a primary source in this pass. In particular, [3] and [4] contain `XXXXX` placeholders, [11] has incomplete bibliographic information, and [12] is incomplete. Treat claims depending on these entries as **UNKNOWN / NEEDS VERIFICATION**, not as established evidence.
- The prior claim that there are no standardized reporting guidelines for algorithmic language constraints also needs a targeted literature search before being stated as fact.

## 5. Current candidate direction

**[INFERRED — not yet selected]** The most ambitious candidate is to test whether citation visibility and document language interact to affect the ranking/exposure of relevant scientific evidence when relevance is controlled. This connects the prior review's two central bias axes. However, recent papers already investigate citation bias in LLM paper recommendation, language bias in multilingual retrieval/RAG, and citation-count effects in a clinical RAG setup. The combined hypothesis is therefore only a candidate gap. It is **not** yet a verified novelty claim.

## 6. Open feasibility questions

- **[UNKNOWN]** Current compute: Google Colab/T4, Colab without guaranteed GPU, or local CPU has not been confirmed in this project turn.
- **[UNKNOWN]** Whether we can build or access a mixed-language scholarly candidate pool with trustworthy relevance judgments and linked citation metadata at manageable cost.
- **[UNKNOWN]** Whether the proposed citation-by-language interaction has already been directly evaluated in a paper not yet reviewed here.
- **[UNKNOWN]** Whether the needed datasets permit the proposed redistribution or only use under specific license conditions. CLIRudit is CC BY-NC 4.0, which must be considered for use and redistribution.
- **[UNKNOWN]** Whether any retrieval intervention improves long-tail recall without unacceptable loss in relevance/quality.

## 7. Next actions

1. Read the original methods/limitations sections of the 2026 multilingual RAG papers and the 2025 clinical RAG citation-bias study, not just abstracts.
2. Complete the five-gap matrix in `gap_matrix.md`; make a go/no-go decision only after its novelty and data dependencies are checked.
3. Confirm compute availability and the amount of time available for experiments.
4. Choose one research question, define the primary metric and comparator(s), verify dataset license/access, and freeze the protocol before looking at experimental results.
5. Only after the above, run a small data/environment sanity check and record actual output. Do not draft results or imply experiments have run before that happens.

## 8. Decision log

| Date | Decision / question | Status | Reason / evidence | Next action |
|---|---|---|---|---|
| 2026-10-21 | Use the previous paper as evidence base rather than recycling its prose | VERIFIED | New assignment requires review → gap → executable experiment → real results | Map review sections to testable gaps |
| 2026-10-21 | Keep citation visibility and language bias as core topic axes | VERIFIED as review scope | Abstract; Sections 3.1–3.2; Sections 5–6 | Compare them against latest primary studies |
| 2026-10-21 | Do not yet claim a novel joint citation-language gap | UNKNOWN | Recent work covers each axis separately and some controlled reranking/RAG effects | Inspect related methods and search more broadly |
| 2026-10-21 | Prepare five candidate gaps and rank the top three provisionally | INFERRED | Required by Prompt 02 | Use `gap_matrix.md`; revisit after source audit |
| 2026-10-21 | No experiment has been run | VERIFIED | No executed code, dataset output, or metrics have been submitted in this project stage | First executable milestone only after G1 approval |
