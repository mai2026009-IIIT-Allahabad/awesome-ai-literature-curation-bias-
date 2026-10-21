# Evidence-Based Research Gap Matrix

**Topic from prior review:** Recall bias toward highly cited and English-language papers in AI literature curation.  
**Prepared:** 2026-10-21  
**Purpose:** Prompt 02 output for G1 scoping. Candidate gaps are not claims of novelty.

## Status rules

- **VERIFIED:** directly supported by the supplied review or a checked primary-source publication/dataset record.
- **INFERRED:** a candidate interpretation, research question, or proposed test derived from the evidence.
- **UNKNOWN:** a fact requiring more source review, access checks, or an actual experiment.

## Five candidate gaps

### Gap 1 — Interaction between citation visibility and document language in scholarly retrieval

**Prior-review evidence**

- **Section 3.1:** discusses parametric LLM memory and claims that LLM citation suggestions favor already highly cited work.
- **Section 3.2:** argues that English-language norms and geolinguistic differences may affect scholarly visibility and retrieval.
- **Section 4.1:** discusses language effects in LLM-assisted screening.
- **Section 5.3:** states that RAG inherits limitations from its retrieval corpus.

**Original-source evidence checked**

- **VERIFIED:** Algaba et al. (NAACL Findings 2025) report a stronger high-citation tendency for parametric LLM citation recommendations: https://aclanthology.org/2025.findings-naacl.381/
- **VERIFIED:** Tian et al. (2024 preprint) report that LLM paper recommendations tend toward higher citation counts, later publication dates, and larger author teams: https://arxiv.org/abs/2501.00367
- **VERIFIED:** Yang et al. (MRL 2024) explicitly study language fairness in multilingual IR and same-semantic queries: https://aclanthology.org/2024.mrl-1.23/
- **VERIFIED:** Wang et al. (ACL 2026) study language bias in multilingual RAG reranking: https://aclanthology.org/2026.acl-long.338/
- **VERIFIED:** Ki et al. (ICML 2026) hold relevance factors controlled while studying language preference across eight languages and six open-weight models: https://proceedings.mlr.press/v306/ki26a.html
- **VERIFIED:** Genovese et al. (European Burn Journal, 2025) compare high- and lower-citation source sets in one clinical RAG setting: https://pubmed.ncbi.nlm.nih.gov/40558623/

**Author-reported limitation versus inference**

- **Author-reported:** the above papers report citation recommendation bias, language bias in multilingual retrieval/RAG, and a domain-specific RAG comparison between high- and lower-citation sources.
- **INFERRED candidate gap:** there may be value in testing the *joint interaction* between citation status and language for scientific retrieval when relevance is controlled. The reviewed sources cover overlapping components, so this is not yet a novelty claim.
- **UNKNOWN:** whether a directly equivalent interaction study already exists; whether a valid matched mixed-language scientific candidate pool can be constructed with citation data and reliable relevance judgments.

**Possible research question**

When document relevance is held constant, do citation visibility and document language jointly affect top-k ranking/exposure in scientific retrieval or reranking, and can a relevance-constrained intervention reduce that effect without materially degrading Recall@k or nDCG@k?

**Evidence needed to test it**

1. A mixed-language scholarly corpus with trustworthy relevance labels and resolvable citation metadata.
2. A frozen candidate set and query set; paired/matched candidates where relevance and topicality are controlled.
3. At least two baselines, such as multilingual dense retrieval and BM25/translation, plus a reranking condition.
4. Controlled ablations for citation metadata visibility and language presentation; report Recall@k/nDCG@k alongside language/citation-stratified exposure and counterfactual rank shifts.
5. Error analysis of cases where a relevant lower-citation or non-English paper falls below an equally relevant alternative.

**Feasibility / risk**

- Significance: **High** if the interaction yields a clear, generalizable finding.
- Feasibility: **Medium–Low**; data construction and relevance control are the main risks.
- Novelty: **UNKNOWN / high overlap risk** because 2026 multilingual RAG work already evaluates language preference under controlled relevance, and 2025 work tests citation-count effects in a RAG setting.
- **Decision:** highest-ambition candidate for further novelty checking, not yet approved for implementation.

---

### Gap 2 — Citation-aware ranking and the recall–quality trade-off for low-visibility papers

**Prior-review evidence**

- **Section 3.1:** says that early citation advantage and existing citation counts can reinforce discoverability.
- **Section 5, item 1:** raises a trade-off between reducing citation bias and increasing citation noise.
- **Section 6, third bullet:** proposes “citation-inflation adjusted” ranking as a future direction.

**Original-source evidence checked**

- **VERIFIED:** Algaba et al. (2025) study high-citation bias in LLM citation recommendations: https://aclanthology.org/2025.findings-naacl.381/
- **VERIFIED:** Tian et al. (2024 preprint) study LLM paper recommendations and report associations with citation count, publication date, and author-team size: https://arxiv.org/abs/2501.00367
- **VERIFIED:** Genovese et al. (2025) compare high-cited vs lower-cited source collections in a clinical RAG use case, and report similar output metrics in that particular setup: https://pubmed.ncbi.nlm.nih.gov/40558623/
- **UNKNOWN:** the prior review’s reference [11] (“Citation accuracy, citation noise, and citation bias: A foundation of citation analysis”) was incomplete and was not verified as a primary source in this pass. Do not rely on it for a specific factual claim until the exact publication is located.

**Author-reported limitation versus inference**

- **Author-reported:** prior review Section 5 warns that down-weighting highly cited documents might increase noise, but the cited item supporting that sentence needs verification.
- **INFERRED candidate gap:** citation adjustment should be evaluated against a relevance-labelled benchmark with explicit long-tail recall and relevance-quality constraints, rather than treating lower citation exposure as success by itself.
- **UNKNOWN:** whether a practical normalization rule improves recall for relevant low-citation papers across datasets without harming overall retrieval relevance.

**Possible research question**

On a relevance-labelled scholarly retrieval benchmark enriched with reliable citation metadata, can a citation-aware reranking rule improve Recall@k for relevant low-citation papers while preserving overall nDCG@k and precision compared with relevance-only and naive popularity-aware rankings?

**Evidence needed to test it**

1. Match benchmark records to a credible citation source (e.g., OpenAlex or another official bibliographic API) and manually inspect a sample of title/DOI matches.
2. Compare relevance-only retrieval, naive citation-prioritized ranking, a simple age/field-normalized citation feature, and a constrained/debiased reranker if implementable.
3. Report overall Recall@k/nDCG@k/Precision@k plus recall/exposure by citation percentile and publication-age strata.
4. Perform an ablation for citation feature, age normalization, and field normalization; inspect harmful cases as well as gains.

**Feasibility / risk**

- Significance: **High**; directly tests the prior review’s proposed citation-adjusted ranking idea.
- Feasibility: **Medium** if document identifiers can be mapped reliably; citation-data linkage is the primary bottleneck.
- Novelty: **UNKNOWN / medium-to-high overlap risk** because popularity-bias correction is a mature recommender-systems topic and citation-aware RAG has already been studied in a clinical domain. A paper must distinguish itself by task, method, evaluation, or generalization.
- **Decision:** a plausible technical-extension path if Gap 1’s data requirements prove impractical.

---

### Gap 3 — Do multilingual screening gains generalize across languages and affect the final included evidence set?

**Prior-review evidence**

- **Section 4.1:** compares translation-mediated and direct multilingual LLM screening and reports sensitivity ranges of 0.47–0.54 for some translation-mediated settings versus 0.71–1.00 for direct processing.
- **Section 6, first bullet:** calls for better evaluation of linguistic representation and “epistemic parity.”

**Original-source evidence checked**

- **VERIFIED:** Ikeguchi, Ueshima, and Tamura (2026) evaluated six LLMs with an English benchmark of 2,911 records and 483 non-English abstracts. The article abstract reports that translation-mediated screening reduced sensitivity for some models to 0.47–0.54 while direct multilingual screening achieved 0.71–1.00; it explicitly says downstream effects on meta-analytic bias require further investigation. https://pubmed.ncbi.nlm.nih.gov/42393975/

**Author-reported limitation versus inference**

- **Author-reported:** the paper itself names downstream meta-analytic effects as unresolved.
- **INFERRED candidate gap:** beyond sensitivity metrics, different screening approaches may lead to different final included-study sets or synthesis conclusions. A multi-language or multi-domain external validation could test generalizability.
- **UNKNOWN:** dataset availability, exact language/domain coverage, and whether the authors’ complete data/prompts are accessible under a usable license.

**Possible research question**

Across more than one language/domain setting with gold inclusion labels, does direct multilingual LLM screening preserve higher sensitivity than translate-then-screen under a fixed workload, and do differences in false negatives change the composition of the final evidence set?

**Evidence needed to test it**

1. Obtain public, legally usable gold-labelled review screening data in multiple languages or domains.
2. Reproduce a simple baseline (human/recorded screening labels or a documented rule/prompt) before adding a new condition.
3. Compare translated versus direct screening with the same models, fixed criteria, and locked thresholds.
4. Report sensitivity, specificity, F1, balanced accuracy, workload, language-stratified false negatives, and disagreement/error examples.
5. If source labels permit it, compare whether the inclusion set differs and whether any downstream synthesis changes; do not infer meta-analysis impact from sensitivity alone.

**Feasibility / risk**

- Significance: **High**, particularly for evidence synthesis.
- Feasibility: **Medium–Low** because suitable gold-labelled multilingual datasets and data permissions may be hard to obtain.
- Novelty: **UNKNOWN**; the direct-versus-translation comparison has been published, so the contribution must be external validation, new languages/domains, or downstream evidence-set impact—not a simple replication.
- **Decision:** strong scientific question if usable multi-language labels are found.

---

### Gap 4 — Query-formulation robustness in English-to-French scholarly retrieval

**Prior-review evidence**

- **Introduction and Section 4.1:** discuss the role of automated search and language barriers, but do not evaluate the effect of different query formulations on the retrieval of scholarly records.
- **Section 6:** calls for more equitable, measurable retrieval/evaluation frameworks.

**Original-source and dataset evidence checked**

- **VERIFIED:** CLIRudit is a public English-query/French-document academic retrieval benchmark. Its queries are combinations of author-provided English keywords, and qrels are derived from matching keyword metadata. Dataset page: https://huggingface.co/datasets/ftvalentini/clirudit; paper: https://aclanthology.org/2025.mrl-main.16/
- **VERIFIED:** Macmillan-Scott et al. (2025) already compare multilingual LLM query-expansion strategies across languages and query lengths, reporting that query length and script/language conditions affect performance. https://arxiv.org/abs/2511.19325
- **VERIFIED:** Yang et al. (2024) study multilingual retrieval fairness for semantically equivalent queries across languages. https://aclanthology.org/2024.mrl-1.23/

**Author-reported limitation versus inference**

- **Author-reported by benchmark design:** CLIRudit’s primary query form is keyword-combination queries, with metadata-derived relevance judgments; it is not a general benchmark of natural-language user questions.
- **INFERRED candidate gap:** the stability of scholarly cross-language retrieval under meaning-preserving natural-language reformulations remains a plausible academic-domain extension, but query expansion and multilingual query fairness have substantial existing literature.
- **UNKNOWN:** whether a controlled natural-language reformulation study on CLIRudit has already been published; the dataset’s automatic qrels may not be sufficient for every paraphrase unless intent preservation is validated.

**Possible research question**

When English keyword queries are converted into meaning-preserving natural-language or paraphrased requests, how much does retrieval quality on French academic documents change for lexical, multilingual dense, and hybrid retrievers, and does the change depend on lexical overlap or query length?

**Evidence needed to test it**

1. Establish baseline results on the official CLIRudit test split before modifying queries.
2. Generate two reformulation types under a frozen prompt/rule and manually validate a stratified sample for concept preservation.
3. Reuse the same documents, relevance labels, and retrieval settings for every query version.
4. Compare Recall@k, nDCG@k, MRR, paired query-level changes, and degradation by query length/lexical overlap.
5. State clearly that CLIRudit is English-to-French; do not generalize results to all languages.

**Feasibility / risk**

- Significance: **Medium**; useful for scholarly search robustness.
- Feasibility: **High relative to other candidates**; public benchmark, established qrels, modest corpus size, and retrieval baselines exist.
- Novelty: **Low-to-Unknown** because multilingual query expansion has already been studied; the academic-specific reformulation protocol must be differentiated carefully.
- **Decision:** best low-cost fallback for the course milestone, but not the strongest publication claim without a more distinct contribution.

---

### Gap 5 — Measuring the effect of skewed corpus coverage on long-tail evidence retrieval

**Prior-review evidence**

- **Section 5, item 3:** says RAG inherits limitations of the retrieval database/corpus.
- **Section 6, second bullet:** calls for more diverse corpora and non-English repositories.
- **Section 6, first bullet:** proposes measuring representation rather than relying only on overall system performance.

**Original-source evidence checked**

- **VERIFIED:** Wang et al. (ACL 2026) find language preference in multilingual RAG reranking and propose LAURA; therefore generic multilingual reranking bias is already studied. https://aclanthology.org/2026.acl-long.338/
- **VERIFIED:** CLIRudit provides an academic cross-lingual retrieval benchmark, but the basic English-query/French-document setup alone is not sufficient to measure relative ranking among multiple target-document languages. https://aclanthology.org/2025.mrl-main.16/
- **VERIFIED:** the 2025 burn-management RAG study assembles high- and lower-citation source sets and compares downstream answer quality in a domain-specific setting. https://pubmed.ncbi.nlm.nih.gov/40558623/

**Author-reported limitation versus inference**

- **Author-reported in prior review:** RAG relies on external corpora and therefore cannot recover documents that are absent from the candidate corpus. The prior review did not cite a primary source directly at this sentence; it is a plausible system property but should be supported in the eventual paper.
- **INFERRED candidate gap:** systematic, controlled removals of language/citation strata can quantify how collection composition affects evidence recall and long-tail exposure in scholarly RAG.
- **UNKNOWN:** a dataset with both valid relevance labels and enough language/citation metadata is not yet selected; related corpus-composition studies may already cover aspects of this question.

**Possible research question**

Under controlled reductions in corpus coverage, how do retrieval recall and the citation/language profile of retrieved evidence change, and can multi-source retrieval or corpus expansion recover relevant low-visibility evidence without a large loss in precision?

**Evidence needed to test it**

1. Select a relevance-labelled scholarly corpus and validate language/citation metadata.
2. Run a full-corpus baseline; then create predetermined skew conditions, for example removing defined shares of lower-citation or non-English records while keeping queries/qrels fixed.
3. Compare full corpus, skewed corpus, and a recovery strategy (e.g., second-source or targeted expansion).
4. Measure Recall@k, nDCG@k, language/citation-stratified recall, corpus composition, latency, and additional screening cost.
5. Describe this as a controlled stress test; do not imply that the artificial removals exactly reproduce real-world indexing.

**Feasibility / risk**

- Significance: **Medium–High**, especially for evidence-based retrieval.
- Feasibility: **Medium** after dataset/metadata linkage; high if a suitable benchmark already exposes needed metadata.
- Novelty: **UNKNOWN / high overlap risk** with corpus-bias and multilingual RAG research. Novelty would require a carefully defined scholarly corpus intervention and a recovery method or causal analysis.
- **Decision:** candidate for a robustness/failure analysis within a stronger primary study rather than necessarily a standalone paper.

---

## Provisional ranking of the top three

This ranking balances significance, novelty risk, implementation feasibility, and likely resource burden. It is **provisional** because compute access and the exact datasets have not yet been confirmed.

| Rank | Candidate | Significance | Implementation feasibility | Novelty / overlap status | Reason for ranking |
|---|---|---|---|---|---|
| **1** | Gap 1: citation visibility × language interaction under relevance control | High | Medium–Low | Unknown; substantial adjacent work | Closest to the review’s two core axes and has the greatest potential to create a distinct empirical finding, but needs strong dataset construction and a more complete novelty audit. |
| **2** | Gap 3: multilingual screening generalization and downstream evidence-set effect | High | Medium–Low | Unknown; direct/translation comparison itself is already published | Builds on a verified recent result and targets an author-identified open question about downstream meta-analytic effects. The main barrier is usable multilingual gold-labelled data. |
| **3** | Gap 4: query-formulation robustness on scholarly CLIR | Medium | High | Lower novelty potential due existing query-expansion work | Most feasible to implement with public data and standard baselines; safest fallback to meet the course gates if the higher-ambition candidates fail data or novelty checks. |

Gap 2 (citation-aware reranking) is a plausible technical path that could be combined with Gap 1, but its evaluation would need to separate the effect of a popularity feature from the language interaction and compare against the existing clinical RAG citation study. Gap 5 is a useful deeper-analysis/ablation candidate but needs a credible corpus and metadata source.

## Go/no-go criteria before implementation

Proceed with a candidate only if all the following are true:

1. The original papers and their limitations are read, not just their abstracts.
2. A search for closely related work does not reveal that the exact question and proposed method have already been answered.
3. The benchmark, relevance labels, metadata and license are accessible and fit the research question.
4. The comparison includes a runnable baseline and at least one meaningful comparator.
5. The primary metric, test split, controls and deeper analysis are decided before looking at final results.
6. The first executable milestone is small enough to verify immediately; no results are assumed in advance.
