**README — Xi Jinping AI Discourse Corpus (2012–2025)**

Dataset size (final): 247 unique, manually-validated correspondences. 297 total corpus size with slight reporting duplications. 
Corpus source: “Xi Jinping’s Series of Important Speeches” (People’s Daily / CCP News Website)
Crawl snapshot / cut-off date: 6 January 2026
Original site crawl: 10,911 unique links. 356 links matched AI keywords. 60 title duplicates removed. 297 total corpus size with 247 unique AI-relevant correspondences retained. 
Date range of retained correspondences: 6 September 2014 — 6 January 2026

⸻

**Purpose & scope**

This curated corpus supports mixed-methods inquiry (computational + close reading) into how Xi Jinping frames and projects AI domestically and internationally. It is designed to enable analyses of temporal trends, audience targeting, sociotechnical imaginaries, and the possible diffusion of Chinese AI norms through diplomatic and infrastructural channels across Asia and the Global Majority.

⸻

**Files included**
	•	Xi_AI_correspondence_labels.csv (labeled dataset). 
	•	README.md (this file).

⸻

**Variable / Field definitions**
	•	**Title_CN**
Original Chinese title of the correspondence (as published).
	•	**Title_EN**
Machine translation to English from original Chinese (for accessibility; not an official translation).
	•	**Date**
Publication or delivery date, where available. Hand validated. Format: YYYY-MM-DD. 
	•	**Domestic/International**
hand-coded label describing the primary delivery setting:
	•	Domestic — primarily addressed to domestic audiences (party meetings, domestic field visits, CCP/PRC bodies).
	•	International — primarily delivered in international/diplomatic contexts (foreign visits, foreign leaders, international conferences).
Classification is based on delivery setting indicated in the artefact, not on the outlet that published it.
	•**Audience**
Hand-coded primary audience type (examples): Other Heads of State/Foreign Leaders, Party Officials, Government Officials, Academics/Scientists, Business/Industry, Provincial/Municipal Officials, General Public/Citizens.
Notes: some correspondences address multiple audience types; the Audience field records the principal audience as assigned by the team.
	•	**Type**
Hand-coded correspondence type (e.g., Speech transcript, Meeting description, Visit description, Letter, Phone call).
	•	**AI_Term_Counts**
Integer count of occurrences of the predefined AI keyword set found in the title and main body (exact-match matching against the keyword list described in the paper: e.g., 人工智能, 深度学习, 机器学习, 基础模型, 大语言模型, 生成式人工智能, 算法, AI, etc.). This count is intended as a simple relevance indicator, not a semantic measure.
	•	**Duplicate? (Y/N)**
Y if this row was flagged as a duplicate version of the same correspondence published across platforms (e.g., People’s Daily + CCP News); N if unique. 
	•	**URL**
Original source URL where the artefact was found.
	•	**matched_text**
Full-text field to support further quantiative analysis.

⸻

**Data collection & processing summary (methods)**
	1.	Crawl & fetch: enumerated category pages on jhsjk.people.cn; retrieved pages using a robust HTTP client with retries (requests + urllib3 Retry). Initial crawl returned 10,911 links.
	2.	Keyword filtering: applied a validated Chinese-language AI keyword set (direct AI, governance, technical, and mechanism terms). 356 links matched at least one keyword.
	3.	Normalization & cleaning: converted Traditional → Simplified Chinese (OpenCC), removed non-Han characters where appropriate, tokenized (jieba; pkuseg available), discarded extremely short/malformed documents (< 200 characters).
	4.	Deduplication & manual review: manually reviewed matched links, removed 109 duplicates (same event across outlets), validated dates, and manually labeled delivery setting, audience type, and correspondence type. Final dataset: 247 unique correspondences.
	5.	Quality checks: manual validation of all matched links to ensure contextual relevance (i.e., keyword appears in an AI-related sense). Provenance and raw JSONL archive retained for reproducibility.

⸻

**Key corpus statistics (from processing)**
	•	Total crawled links: 10,911
	•	Links with AI keywords (initial): 356 (≈3.26% of site)
	•	Date coverage (final): 2014-09-06 — 2026-01-06
	Note: some documents address multiple audiences. 

⸻

**Major limitations & usage cautions**
	•	Curated source: the Xi Important Speeches site is a curated collection approved by CCP organs. It is not a complete dump of every Xi correspondence; it contains material the Party chooses to present. Treat findings as representative of public, curated rhetoric — not necessarily of behind-the-scenes decision-making.
	•	Translation & meaning drift: Chinese AI terms vary by context; some translations (e.g., 通用人工智能) can differ in meaning across texts and time. Always consult original Chinese when conducting fine-grained semantic analysis.
	•	Audience coding ambiguity: some correspondences target mixed audiences; we recorded the principal audience.

⸻

**Suggested citation**

If you use this dataset, please cite the paper and dataset as follows (forthcoming) 

⸻

**Contact & provenance**

For questions about coding decisions, variable construction, or collaboration: Sydney Reis; [Sydney.oxchinapolicy.org].
