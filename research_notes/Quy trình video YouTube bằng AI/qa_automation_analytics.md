# QA, Human-in-the-Loop Governance, Automation and Analytics Feedback Loop for AI-Assisted YouTube Production

Research date: 2026-10-09. Audience: Vietnamese creator, prefers free/open-source tooling.

IMPORTANT METHOD NOTE FOR THE REPORT WRITER: WebFetch could not resolve any hostname in this environment (getaddrinfo ENOTFOUND for support.google.com, ncbi.nlm.nih.gov, ffmpeg.org, mental.jmir.org), and Bash network access was denied. Every finding below therefore comes from WebSearch result summaries (snippets), not from reading the full primary pages. Where a source is a vendor blog or aggregator, or where the primary page was only visible as a snippet, it is flagged. Items marked "(snippet only)" should be re-verified against the primary page before being quoted as exact wording. Items under "Inferences" are my own design proposals or reasoning, not sourced facts.

---

## 1. Fact-checking and sourcing for AI-written scripts (claim ledger, approval gate, LLM error rates)

### Takeaway
Newsroom and fact-checker practice converges on: treat AI output as unvetted material, verify every checkable claim against primary or independent sources, read laterally (leave the page and check who is behind a source), and keep a public correction path. Peer-reviewed studies show LLMs fabricated roughly 18-20% of GPT-4-class citations in 2023-2025 test setups, with higher error on niche topics, so a claim-by-claim ledger with a human approval gate before visuals is justified.

### Cited Findings
- AP's original 2023 AI standards: staff may experiment with tools like ChatGPT but may not use them to create publishable content; AI output is treated as unvetted material to which AP's sourcing standards and editorial judgment apply; the guidance flagged hallucination and misinformation risk (via secondary coverage, Poynter) — [Poynter (snippet only)](https://poynter.org/?p=1067636)
- AP's 2026 update (secondary coverage only, AP's own text not seen): AI allowed for narrower tasks (early research, document summaries, transcription, translation, headline and shot-list suggestions); reporting, sourcing and verification remain with humans; output is reviewed/edited by journalists before publication; disclosure required when generative AI materially contributes to published work; "material" is not defined — [WNA News](https://wnanews.com/2026/07/26/ap-updates-ai-newsroom-standards/); [MediaCopilot](https://mediacopilot.ai/ap-ai-newsroom-standards-update/)
- AP still bars generative AI to create, alter or enhance news photography (same secondary coverage) — [WNA News](https://wnanews.com/2026/07/26/ap-updates-ai-newsroom-standards/)
- IFCN Code of Principles (fact-checker standard): one standard applied to all fact checks, same process every time, "let the evidence dictate the conclusions"; transparency of sources so readers can verify findings themselves; a published corrections policy applied strictly with clear, visible corrections; applicants assessed against 31 criteria by independent assessors (summary via signatory pages and search summary, official wording not read) — [IFCN commitments](https://ifcncodeofprinciples.poynter.org/the-commitments); [IFCN about](https://ifcncodeofprinciples.poynter.org/about)
- Lateral reading: in the Stanford History Education Group study (Wineburg and McGrew, 2017, Working Paper 2017-A1) 10 professional fact checkers, 10 PhD historians and 25 Stanford undergraduates evaluated live websites. Fact checkers left the page quickly and opened other tabs to find context; historians and students stayed on the page ("vertical reading") and were swayed by professional logos, domain names and scholarly-looking references — [Stanford News](https://news.stanford.edu/2017/10/24/fact-checkers-outperform-historians-evaluating-online-information/); [Stanford Daily](https://stanforddaily.com/2017/10/26/fact-checkers-more-likely-than-peer-expert-groups-to-identify-credible-information-determine-gse-researchers/) (full paper not read; SSRN abstract 3048994 cited by the news pieces)
- Walters and Wilder (Scientific Reports, 7 Sep 2023, DOI 10.1038/s41598-023-41032-5): GPT-3.5 and GPT-4 wrote short literature reviews on 42 topics (84 papers, 636 citations). 55% of GPT-3.5 and 18% of GPT-4 citations were fabricated; among non-fabricated citations, 43% (GPT-3.5) and 24% (GPT-4) contained substantive errors — [PMC10484980](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10484980/) (figures from search summary, page not opened)
- Buchanan, Hill and Shapoval (The American Economist, 2024), as summarized by search: fabrication over 20% for GPT-4 vs over 30% for GPT-3.5 in economics prompts; accuracy dropped on very narrow topics (only 57% real at the most specific level) — [CUNY Academic Works listing (snippet only)](https://academicworks.cuny.edu/gc_pubs/1119) (the exact paper page was not confirmed; treat as indicative)
- Linardon et al. (JMIR Mental Health, 2025): GPT-4o literature reviews on mental-health topics; 35 of 176 citations (19.9%) fabricated; 45.4% of real citations had errors (often wrong/invalid DOIs); fabrication was 28-29% for less-studied topics (binge eating, body dysmorphic disorder) vs 6% for major depression — [JMIR Mental Health](https://mental.jmir.org/2025/1/e80371/PDF) (snippet-level summary only)
- Fabricated citations often pair real author names with fictitious titles, making surface checks insufficient (per search summary of a 2026 arXiv audit) — [arXiv 2603.03299](https://arxiv.org/pdf/2603.03299) (snippet only, I did not read the paper)
- OpenAI, "Why language models hallucinate" (5 Sep 2025): hallucinations persist partly because evaluations reward confident guessing over abstaining; example from GPT-5 system card on SimpleQA: o4-mini 24% accuracy / 75% error / 1% abstention vs GPT-5-thinking-mini 22% accuracy / 26% error / 52% abstention — [OpenAI](https://openai.com/index/why-language-models-hallucinate/) (blog text via search summary)
- Caveat from the search summary: these studies are small (dozens of prompts), differ in domain, prompt and verification method, and are mostly on non-search-augmented models; later or search-grounded models may differ. Percentages are indicative, not universal rates.
- Reuters Institute context (older, 2024 edition, secondary write-up): 52% of US and 63% of UK respondents were uncomfortable with news produced mainly by AI; no 2026 comfort/labelling figures were found — [Gizchina summary (snippet only, low authority)](https://www.gizchina.com/tech/news-by-ai)

### Inferences
- A creator-grade claim ledger can be a CSV/Google Sheet with columns: claim_id, script_line/timecode, claim text (atomic, one fact), claim type (number, date, quote, attribution, causal, opinion), source URL, source tier (primary / reputable secondary / unverified), retrieval date, verifier (human/LLM-assisted), status (verified / corrected / unverifiable-cut / opinion-flagged), confidence (high/med/low), notes on discrepancy. The IFCN "readers can verify" principle maps to publishing the source list in the description.
- Rules adapted from the sources: (1) no claim enters the final script with only an LLM as its source; (2) every number, date, quote and name must resolve to a primary document (paper DOI, official statistic, filing) opened by a human; (3) verify that a DOI/URL resolves AND matches the claimed title/author (the studies show real-looking but wrong DOIs are the main error); (4) lateral-read any unfamiliar source before trusting it; (5) niche or low-resource topics, and Vietnam-specific topics where English-language training data is thinner, deserve extra scrutiny (the niche-topic effect is shown in Buchanan and Linardon; Vietnam-specific data was not found).
- Approval gate: no storyboard, image generation, TTS or render spend until the ledger has zero "unverified" rows and a human signs off. This is cheap insurance because errors found after render cost re-generation of voice and visuals.
- Treat LLM self-reported "confidence" as unreliable given the OpenAI finding that models are rewarded for guessing; confidence in the ledger should be set by the human verifier based on source quality.

### Gaps
- No Vietnamese-language or Vietnam-specific measurement of LLM factual error rates was found.
- No study found measuring hallucination rates specifically for video-script-style (not citation) generation; the evidence is for citation fabrication and short-form QA.
- Primary AP 2026 text, IFCN full commitment text and the full Stanford paper were not read (fetch unavailable).
- No 2026 figures on audience tolerance of AI-narrated videos were found.

---

## 2. Video QA checklist and what can be automated with free tools

### Takeaway
Loudness, true peak, duration, contrast and subtitle timing can be checked automatically with ffmpeg/ffprobe and standards-based thresholds; factual accuracy, visual-voice meaning, thumbnail honesty and licensing need a human. The one standard I can source for loudness is EBU R128 (-23 LUFS, -1 dBTP); YouTube's "-14 LUFS" target is widely repeated but unconfirmed by YouTube documentation in my results.

### Cited Findings
Loudness and audio
- EBU R128: programme loudness normalized to -23.0 LUFS; tolerance +/-0.5 LU (v3, 2014) with +/-1.0 LU permitted where the target is not practical (e.g., live); true peak must not exceed -1 dBTP; measurement per ITU-R BS.1770 / EBU Tech 3341. Sources disagree on tolerance by version — [EBU R128 v4 PDF](https://tech.ebu.ch/docs/r/r128v4_0.pdf); [Wikipedia EBU R 128](https://en.wikipedia.org/wiki/EBU_R_128) (figures from search summary; check the current R128 text)
- YouTube "-14 LUFS": widely repeated by third-party blogs and tool vendors, not confirmed by YouTube documentation in my results; one reverse-engineering analysis estimated YouTube's target between about -13.7 and -16.2 LUFS depending on method — [AI Mastering blog (third party)](https://aimastering.com/blog/en/?p=426); [Opus.pro (vendor)](https://opus.pro/blog/best-loudness-normalizers)
- ffmpeg loudnorm two-pass workflow: pass 1 `loudnorm=I=-16:TP=-1.5:LRA=11:print_format=json` with `-f null -`, pass 2 feeds `measured_I/measured_TP/measured_LRA/measured_thresh/offset` and `linear=true`; linear mode needs reachable targets, otherwise it falls back to dynamic (check `normalization_type` in the output); loudnorm may resample to 192 kHz so add `aresample=48000`; `-c:v copy` leaves video untouched — [DEV Community loudnorm guide](https://dev.to/javidjamae/ffmpeg-loudnorm-filter-ebu-r128-loudness-normalization-guide-15d4); [FFmpeg-devel doc patch](https://ffmpeg.org/pipermail/ffmpeg-devel/2018-August/233372.html)
- ebur128 with true peak: `ffmpeg -nostats -i FILE -filter_complex ebur128=peak=true -f null -`; a 2022 bug about broken output channels with peak=true was closed, and a June 2025 commit fixed true-peak propagation across channels — [FFmpeg-user thread](https://ffmpeg.org/pipermail/ffmpeg-user/2014-June/021850.html); [FFmpeg-trac #9723](https://trac.ffmpeg.org/ticket/9723); [FFmpeg-devel 2025 patch](https://ffmpeg.org/pipermail/ffmpeg-devel/2025-June/345764.html)
- Clipping: no dedicated "clipped sample count" in astats was identified in my results; astats reports per-channel min/max levels. Counting samples at +/-1.0 may need a short script — [FFmpeg-trac #2759](https://trac.ffmpeg.org/ticket/2759) (indirect evidence only)
- Duration/metadata: `ffprobe -v quiet -print_format json -show_format FILE` and read `format.duration`; or `-show_entries format=duration -of default=noprint_wrappers=1:nokey=1` — [TechOverflow](https://techoverflow.net/2022/10/21/how-to-get-length-duration-of-video-file-in-python-using-ffprobe/)

On-screen text and subtitles
- WCAG 2.2 SC 1.4.3 (AA): contrast ratio at least 4.5:1 for text and images of text, 3:1 for large text; large text = 18 pt (~24 px) or 14 pt bold (~18.7 px); logotypes and pure decoration exempt (pixel equivalents are from a secondary source). Note WCAG is written for web content; applying it to video frames is an adaptation — [W3C Understanding SC 1.4.3](https://w3c.github.io/wcag/understanding/contrast-minimum)
- Netflix timed-text style guides (language-specific): 42 characters per line is common; reading speed limits are language-specific (Indonesian: 17 CPS adults, 13 CPS children; Telugu: 22 / 18). No Vietnamese guide was found in my results — [Netflix Indonesian guide](https://backlothelp.netflix.com/hc/en-us/articles/216009727); [Netflix Telugu guide](https://backlothelp.netflix.com/hc/en-us/articles/4482320288787-Telugu-Timed-Text-Style-Guide)

Timing and narration speed
- Cross-language speech study (Science Advances 2019, Lyon group, 17 languages, 170 speakers): reading speed ranged from 4.3 to 9.1 syllables/second across speakers; one secondary table value puts Vietnamese near 5.3 syllables/second (not verified in the paper) — [CNRS news](https://news.cnrs.fr/ZwS)
- No Vietnamese voice-over standard (words per minute or syllables per second for narration) was found in my results.

HyperFrames tooling
- HyperFrames CLI (heygen-com/hyperframes): `npx hyperframes lint` catches structural problems (missing data-composition-id, overlapping tracks, unregistered timelines); `check` reportedly replaces the older `validate` (WCAG contrast audit) and `inspect` (headless-Chrome layout check for text overflow); typical order scaffold, write, lint, check, preview, render; requires Node.js 22+ and FFmpeg. Sources disagree (some pages still list validate/inspect separately), and none described `check` in detail — [skills.sh HyperFrames CLI (snippet only)](https://www.skills.sh/heygen-com/hyperframes/hyperframes-cli); [SkillsCat listing](https://skills.cat/skills/heygen-com/hyperframes/hyperframes-cli)

Compliance
- YouTube altered/synthetic content disclosure: announced Nov 2023, Studio toggle live Mar 2024 (per third-party summaries); required for realistic content a viewer could mistake for real people/places/events (e.g., cloned voice, altered real footage); not required for obviously artificial content such as animation or for AI used as behind-the-scenes production support (scripts, titles, thumbnails assistance); label appears in description, more prominently for sensitive topics; repeated non-disclosure can lead to penalties including YPP removal. One source gave a conflicting "May 2025" effective date and another mentioned a May 2026 labeling update that I could not verify — [Android Central](https://www.androidcentral.com/apps-software/youtube-ai-synthetic-content-disclosure); [AIR Media-Tech](https://air.io/en/youtube-glossary/what-is-youtubes-ai-content-disclosure-policy); [PPC Land](https://ppc.land/youtube-introduces-mandatory-disclosure-for-ai-content/) (YouTube Help page not opened)
- Vietnam: Luat Tri tue nhan tao (Law 134/2025/QH15), passed 10 Dec 2025, effective 1 Mar 2026; imposes marking/labeling duties for AI-generated or edited audio/image/video, especially where it could mislead about real events or real people; labeling detail in Decree 142/2026/ND-CP (effective 1 May 2026, Article 18 per the source). Obligations in the text appear aimed at AI providers, so how they apply to an individual creator is unclear. Source did not check the official gazette — [VnEconomy](https://vneconomy.vn/luat-tri-tue-nhan-tao-se-co-hieu-luc-tu-ngay-132026.htm); [Bao Lao Cai](https://baolaocai.vn/diem-moi-cua-luat-tri-tue-nhan-tao-co-hieu-luc-tu-nam-2026-post894207.html); [LSVN on Decree 142/2026](https://lsvn.vn/tag/nghi-dinh-1422026ndcp.html)
- EU AI Act Article 50 deepfake and chatbot disclosure duties apply from 2 Aug 2026; machine-readable marking duty for pre-existing systems deferred to 2 Dec 2027 per one law-firm summary (digital omnibus; legal status unconfirmed); relevant only if the channel targets EU audiences — [Cooley](https://www.cooley.com/news/insight/2026/2026-08-03-eu-ai-act-transparency-obligations-take-effect-2-august-2026); [Sidley](https://datamatters.sidley.com/2026/06/24/eu-ai-act-transparency-obligations-preparing-for-compliance-by-2-august-2026/)

### Inferences
Suggested QA matrix (my design built on the sourced facts above):

| Check | Automated (free) | Human |
|---|---|---|
| Duration vs planned runtime | ffprobe duration, compare to script word/syllable budget | - |
| Narration pace | Count syllables in script divided by audio duration (script in Vietnamese: count words since Vietnamese is syllable-per-word), flag outliers vs your own calibrated baseline | Listen for rushed or dragging sections |
| Loudness | ffmpeg ebur128 / loudnorm two-pass; assert integrated LUFS in target band and true peak at or below -1 dBTP | Spot-listen on phone speaker and headphones |
| Clipping | Script over decoded samples or astats peak level near 0 dBFS | - |
| Caption accuracy | Whisper or similar transcript diff vs script (WER); SRT lint: max chars/line, CPS, overlaps, min/max duration | Read all Vietnamese diacritics, names, numbers |
| On-screen text | HyperFrames check (contrast/overflow); own script computing WCAG contrast ratio of text vs background color tokens; minimum font-size assertion | Check legibility on a phone-sized preview |
| Visual-voice sync | Scene start/end timestamps vs audio cue timestamps (tolerance) | Watch full cut once at 1x |
| Claims | Ledger completeness check (no unverified rows) | Verify sources |
| Thumbnail/title honesty | Optional: length checks | Human judges whether the video delivers on the promise |
| AI disclosure | Checklist boolean in render manifest | Decide on Studio toggle answers |
| Music/asset license | Manifest requires license field per asset | Verify license terms and attribution |
- Thresholds above (CPS, WPM, syllable pace) are not sourced for Vietnamese; the creator should calibrate on their own best-performing episode rather than adopt foreign numbers.

### Gaps
- YouTube's official Help text for AI disclosure and for loudness was not opened; no first-party source for the "-14 LUFS" figure.
- No Vietnamese subtitle reading-speed standard found.
- HyperFrames `check` exact checks and flags not verified; run `npx hyperframes check --help` locally.
- No sourced free tool specifically for subtitle validation (e.g., SRT linters) or for automated contrast checks of video frames was verified; only the generic ffmpeg and WCAG facts.
- Music license rules (YouTube Audio Library, Content ID claim behaviour) were not researched in this pass.

---

## 3. Human-in-the-loop design (editorial gates, cadence, decision logs)

### Takeaway
Media-industry guidance (AP) and the EU transparency regime both keep a human accountable for verification and disclosure, with AI permitted for drafting-style tasks. For a one-person channel the practical design is a small number of hard gates (facts, script, final cut, publish metadata) with a written decision log.

### Cited Findings
- AP 2026: AI allowed for research support, summaries, transcription, translation and headline/shot-list suggestions, but reporting, sourcing and verification remain human; output reviewed by a journalist before publication; disclosure when AI materially contributes — [WNA News](https://wnanews.com/2026/07/26/ap-updates-ai-newsroom-standards/); [MediaCopilot](https://mediacopilot.ai/ap-ai-newsroom-standards-update/) (secondary)
- AP 2023: AI output is unvetted material; even AI summaries must be edited like any other copy — [Poynter (snippet only)](https://poynter.org/?p=1067636)
- EU AI Act Article 14 (human oversight) is a high-risk-system requirement and, after the digital omnibus, is tied to 2 Dec 2027 / 2 Aug 2028 dates, so it is not the relevant provision for a YouTube channel; Article 50 transparency duties (deepfake disclosure) apply from 2 Aug 2026 — [Cooley](https://www.cooley.com/news/insight/2026/2026-08-03-eu-ai-act-transparency-obligations-take-effect-2-august-2026) (law-firm summary; omnibus legal status unconfirmed by me)
- n8n supports pausing a workflow with the Wait node, which stores state until resumed; approvals commonly use "On Webhook Call" resume URLs, and approval channels include email, Slack, Telegram, etc. Evidence is third-party guides, not n8n docs — [Kirim.email guide (vendor)](https://en.kirim.email/blog/email-approval-workflow-n8n-human-in-the-loop/); [Growwstacks guide](https://growwstacks.com/blog/human-in-the-loop-n8n-guide)
- YouTube Studio's AI disclosure is a self-declaration made by the creator at upload, so the legal and platform accountability sits with the human publisher — [Android Central](https://www.androidcentral.com/apps-software/youtube-ai-synthetic-content-disclosure)

### Inferences
- Recommended gates (my design): G1 Brief and angle approved (human); G2 Claim ledger signed off (human, hard stop before any paid generation); G3 Script and storyboard approved (human reads aloud once); G4 Automated QA green plus human full watch of the rendered file; G5 Publish metadata (title, thumbnail, disclosure toggle, music licenses) approved. Everything between gates can be automated.
- Cadence for a solo creator: gates are per-episode; add a weekly 30-minute batch review of the decision log and QA failure counts, and a monthly review of policy pages (YouTube YPP, disclosure rules) because the 2025-2026 sources show rules and enforcement changing quickly.
- Decision log format: date, episode id, gate, decision (approve / revise / kill), who decided, what changed, link to ledger version and Git commit. Keeps an audit trail useful if a video is flagged or a correction is needed (IFCN corrections principle).
- Do not auto-publish. Every sourced governance reference keeps a human accountable at the point of publication.

### Gaps
- No NIST AI RMF, ISO or BBC/Reuters-specific document on human-in-the-loop for small creators was retrieved.
- No evidence on optimal review cadence; the cadence above is my design, not sourced.
- n8n official docs were not reached; Wait node behaviour comes from third-party guides.

---

## 4. Automation and project management (orchestration, repo structure, versioning, budgets)

### Takeaway
Keep text, prompts, configs and ledgers in plain Git; keep large binaries (audio, renders, stock footage) outside Git or in LFS/DVC-style storage; orchestrate with a Makefile or shell for reproducible local steps and add n8n or GitHub Actions only where scheduling or approvals are needed. Sourced evidence in this area is thin, so most of this section is design inference.

### Cited Findings
- Git LFS replaces large files (audio, video, graphics) with text pointers inside Git and stores content on a remote; hosts apply quotas, and a 2019 forum thread cited a 2 GB per-file limit on GitHub LFS (unconfirmed as current) — [DVC forum thread](https://discuss.dvc.org/t/dvc-compared-with-gitlfs-for-storage-and-versioning-only/241)
- DVC keeps small `.dvc` metadata files in Git with data in external storage (S3, GCS, Azure), uses content-addressed caching with deduplication, and adds pipeline stages (`dvc.yaml`) that record dependencies and outputs; one source says DVC has been acquired by lakeFS, so check current direction — [DVC forum thread](https://discuss.dvc.org/t/dvc-compared-with-gitlfs-for-storage-and-versioning-only/241); [Parse comparison (low-authority, AI-generated claims)](https://parse.gl/vs/dvc-ai-vs-lakefs-io)
- HyperFrames project loop: scaffold, write, lint, check, preview, render; needs Node.js 22+ and FFmpeg (CLI-friendly, therefore scriptable in Make/Actions) — [skills.sh HyperFrames CLI (snippet only)](https://www.skills.sh/heygen-com/hyperframes/hyperframes-cli)
- ffmpeg two-pass loudnorm is deterministic given measured values, so it can be a pure Makefile target — [DEV Community](https://dev.to/javidjamae/ffmpeg-loudnorm-filter-ebu-r128-loudness-normalization-guide-15d4)
- n8n Wait node enables approval pauses (see section 3) — [Growwstacks](https://growwstacks.com/blog/human-in-the-loop-n8n-guide)

### Inferences
- Suggested episode folder (my design):
  ```
  channel/
    series/           # series bible: style guide, voice, brand tokens
    prompts/          # versioned prompt files (v1, v2...) with changelog
    episodes/EP012-slug/
      brief.md
      claims.csv            # claim ledger
      sources/              # saved PDFs/screenshots of primary sources
      script.md
      storyboard.md
      scenes/               # HyperFrames HTML compositions
      audio/                # TTS output (LFS or ignored)
      render/               # outputs (ignored; keep manifest only)
      qa_report.json        # loudness, duration, lint results
      manifest.json         # tool versions, seeds, prompt version hashes, asset licenses, AI-disclosure answers
      decision_log.md
      postmortem.md
    Makefile
  ```
- Reproducible render: pin Node/HyperFrames/FFmpeg versions in manifest, record prompt-file hash and model name/version, store TTS seeds/settings, and commit the manifest. Generative output is not bit-reproducible, so freeze the approved audio and image files (LFS/DVC or backups) rather than regenerating them.
- Orchestration: Makefile targets `make ledger-check`, `make audio`, `make qa`, `make render`, `make package`; GitHub Actions to run lint and ledger-check on pull requests (cheap, no GPU); n8n for scheduling, notifications and approval pauses via Wait node. Prefer the lightest tool that works for a solo creator.
- Batching: do research and claim ledgers for 3-4 episodes in one block, then scripts, then TTS, then renders, so context switching and API warm-up cost less. Unsourced operational heuristic.
- Cost/time budget template per episode (blank fields to fill with real data, no sourced benchmarks): research hours, verification hours, LLM tokens/cost, TTS characters/cost, image/video generation cost, render minutes, review hours, total, versus target. Track actuals in `manifest.json` or a sheet and review monthly.

### Gaps
- No sourced benchmarks for cost or time per AI-assisted video were found.
- No official n8n, GitHub Actions or Git LFS documentation was retrieved (fetch unavailable); n8n Execute Command node availability/restrictions were not verified.
- Whether Git LFS or DVC is better for this exact use case is a judgment; only generic comparisons were found.

---

## 5. Analytics feedback loop (metrics, A/B testing, post-publish review)

### Takeaway
Read reach (impressions, CTR) first, then engagement (average view duration, retention graph), then loyalty (returning viewers). YouTube's native "A/B test titles and thumbnails" (formerly "Test & compare") exists in 2026, supports up to 3 variants, picks a winner by watch time, and excludes Shorts and Premieres. YouTube changed public view counting on 24 Aug 2026, which affects before/after comparisons.

### Cited Findings
- Native testing: YouTube Help "A/B test titles & thumbnails" says creators can test up to 3 titles and thumbnails; the option with the highest watch time is shown to all viewers at the end; available on desktop in YouTube Studio only; requires advanced features enabled; Shorts, scheduled Lives and Premieres excluded (Live Archives can be tested); outcomes can include "Winner", "Performed Same" or "Inconclusive"; results in the Reach tab of YouTube Analytics — [YouTube Help 16391400 (snippet only)](https://support.google.com/youtube/answer/16391400?hl=en)
- Winner selected by "watch time per impression" and tests run up to 14 days per RouteNote (third party); YouTube Help does not publish the statistical method, thresholds or minimum sample sizes in what I could see — [RouteNote](https://routenote.com/blog/?p=105347)
- Rollout history: title testing began as an experiment for a small percentage of creators; later coverage says it expanded to all YPP creators (a 2026 article dates the expansion to Dec 2025). Older third-party guides claiming titles cannot be tested are outdated — [Social Media Today](https://www.socialmediatoday.com/news/youtube-adds-title-testing-youtube-studio/753015/); [Tubefilter](https://www.tubefilter.com/?p=187324); [Gyre](https://gyre.pro/blog/youtubes-new-title-ab-testing-tool-everything-creators-need-to-know)
- In the current Studio interface the control may appear as "A/B Testing" while Help calls it "A/B test titles & thumbnails" — [vidIQ](https://vidiq.com/blog/post/youtube-launches-new-thumbnail-testing-tool/) (third party)
- Metric definitions (third-party guides): impressions are logged when a thumbnail is shown; CTR = clicks / impressions x 100; average view duration is best read as a percentage of video length; the retention graph shows drop-off points; high CTR with weak retention indicates packaging overpromised. Benchmark ranges (e.g., CTR 2-10%, 4-6% typical; AVD 40-50%+) vary by source and are rough guides, not YouTube-official — [Artlist](https://artlist.io/blog/youtube-analytics/); [vidIQ](https://vidiq.com/blog/post/youtube-analytics-for-brands/)
- Retention report segments (official Help): audience retention segments let you compare new vs returning viewers, subscribers vs non-subscribers, organic vs paid; returning viewers are people who watched the channel before and came back; the detailed activity view shows absolute view counts per segment that can exceed total views because a viewer may rewatch parts — [YouTube Help 1715160 (snippet only)](https://support.google.com/youtube/answer/1715160?hl=en); [YouTube Help 9314415](https://support.google.com/youtube/answer/9314415)
- Absolute vs relative retention (third-party definitions): absolute = share of viewers still watching at each moment; relative = compared with other videos of similar length — [Teleprompter.com](https://www.teleprompter.com/blog/youtube-audience-retention); [CData docs](https://cdn.cdata.com/help/BYN/py/pg_table-audienceretention.htm). Official wording for relative retention was not visible.
- View counting change: from 24 Aug 2026 a public view registers when playback starts (no minimum watch time) across long-form, Shorts and live; the previous method continues as "Engaged Views" and "Engaged Watch Hours"; YouTube said earnings and YPP eligibility are unaffected; no retroactive restatement; CTR, AVD, retention and earnings still use engaged views (per secondary summaries of YouTube's blog post). Source dates for the announcement differ (17 vs 19 Aug) — [YouTube blog on engaged views](https://blog.youtube/inside-youtube/engaged-views-youtube-explained/); [Business Today](https://www.businesstoday.in/amp/technology/news/story/youtube-changes-how-video-views-are-counted-heres-whats-changed-549761-2026-08-18); [vidIQ](https://vidiq.com/blog/post/youtube-view-count-update/)

### Inferences
- Interpretation matrix (my reasoning from the definitions): low impressions = topic/keyword/packaging not distributed or channel authority low; normal impressions + low CTR = fix title/thumbnail; high CTR + steep early drop = hook or promise mismatch (also an honesty signal); steady decline with sharp cliff at a minute mark = a specific scene or section problem; low returning viewers = series identity or topic drift problem.
- Because native tests exclude Shorts and Premieres and use watch time per impression as the criterion, test one variable at a time, include a title+thumbnail pair that is honest to the video, and treat "Performed Same/Inconclusive" as a valid result (do not force a winner). Run tests on videos with enough impressions; no official minimum was found, so decide your own minimum and log it.
- Post-publish review template (my design): at 48 h, 7 days and 28 days record impressions, CTR, AVD (% and minutes), retention at 30 s and at the lowest point, returning-viewer share, traffic sources, comments themes, corrections needed, A/B test result and decision. Then fill "Brief changes for next episode": hook change, topic cut/extend, length change, thumbnail/title pattern kept or dropped, one fact-check process failure and fix.
- Mark 24 Aug 2026 on any dashboard; compare engaged views, not public views, across that date.

### Gaps
- No official YouTube statement on minimum sample sizes or the statistical test in A/B tests.
- YouTube Help pages were only seen as snippets; no first-party definitions of relative retention or exact CTR benchmark guidance (benchmarks come from third-party blogs).
- No Vietnam-market-specific benchmarks (CTR, retention) found.
- Whether Test & compare is available to non-YPP channels in 2026 is unclear: Help says "enable advanced features" while news coverage says YPP creators.

---

## 6. Risk register for AI-produced channels

### Takeaway
YouTube's July 2025 "inauthentic content" rename and 2026 enforcement actions target mass-produced, repetitive, low-value channels, not AI use as such; the main sourced risks are monetization loss from templated repetition, factual errors, and undisclosed realistic synthetic media. Several widely repeated "strike count" rules were unverifiable.

### Cited Findings
- On 15 Jul 2025 YouTube renamed "repetitious content" to "inauthentic content" in YPP policy; TeamYouTube called it a minor update to a longstanding guideline and said no new policies were added; YouTube said it is not banning reused or AI-generated videos that add original value such as commentary, editing or narration; templated, highly repetitive formats (notably Shorts) and cosmetic changes (music, speed, cropping) are cited as at risk — [Mediaweek](https://mediaweek.com.au/platforms-push-back-youtube-and-meta-crack-down-on-authentic-content); [Gulf News](https://gulfnews.com/technology/youtube-updates-monetisation-policies-ai-and-repetitive-content-ban-begins-july-15-1.500192660); [Plagiarism Today](https://www.plagiarismtoday.com/2025/07/08/youtube-targets-inauthentic-content/) (YouTube policy page itself not opened)
- 2026 enforcement (secondary reporting): a January 2026 action reportedly terminated 16 channels totalling about 35 million subscribers and 4.7 billion lifetime views; a July 2026 report describes categories (repetitive AI videos, distressing or emotionally manipulative clips, synthetic personas on health/finance) which I could not confirm against YouTube text — [AIR Media-Tech timeline](https://air.io/en/monetization/youtube-monetization-policy-changes-2026-a-complete-dated-timeline); [Android Headlines](https://www.androidheadlines.com/2026/07/youtube-monetization-rules-ai-slop-inauthentic-content.html)
- Unverified claims flagged by the same research: a "three-strike" AI-disclosure demonetization ladder (immediate, 90 days, YPP removal), stock-footage percentage thresholds, and an Aug 2026 YPP overhaul effective Feb 2027 with doubled thresholds appeared in single low-authority sources and are NOT confirmed by YouTube — [YT Growth](https://ytgrowth.io/blog/youtube-ai-policy); [AIR Media-Tech timeline](https://air.io/en/monetization/youtube-monetization-policy-changes-2026-a-complete-dated-timeline)
- Disclosure non-compliance: label may be applied by YouTube without the option to remove; repeated failures can lead to removal of content or YPP suspension — [AIR Media-Tech glossary](https://air.io/en/youtube-glossary/what-is-youtubes-ai-content-disclosure-policy)
- Factual error base rates: 18-20% fabricated citations for GPT-4-class models in studies (section 1) — [PMC10484980](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10484980/); [JMIR Mental Health](https://mental.jmir.org/2025/1/e80371/PDF)
- Audience distrust: older Reuters Institute data show majorities in US/UK uncomfortable with mainly-AI news (2024 edition, secondary) — [Gizchina (low authority)](https://www.gizchina.com/tech/news-by-ai)
- Legal: Vietnam AI Law (effective 1 Mar 2026) and Decree 142/2026 (1 May 2026) include labeling duties for AI-generated realistic media — [VnEconomy](https://vneconomy.vn/luat-tri-tue-nhan-tao-se-co-hieu-luc-tu-ngay-132026.htm)

### Inferences
Risk register (my synthesis; likelihood/impact are judgments, not measured):

| Risk | Early signal | Mitigation |
|---|---|---|
| Factual error published | Ledger rows with only LLM source; corrections in comments | Claim ledger gate, primary-source rule, pinned correction + description edit policy (IFCN-style) |
| Repetitive/templated output flagged as inauthentic | Same intro, structure, B-roll, voice across episodes; low original commentary | Add original analysis, human-chosen angle and on-camera/voice identity; vary structure; document what is original in each brief; cap output volume to what you can review |
| Undisclosed realistic synthetic media | Cloned voice, realistic synthetic people/places | Use Studio disclosure toggle when realistic; avoid realistic fabrications of real people; keep a disclosure line in the manifest; consider Vietnam labeling rules |
| Copyright/music claims | Content ID claims, third-party stock without license | Per-asset license field in manifest; use only licensed or original assets; keep receipts (music licensing not researched in this pass) |
| Audience distrust | Comments questioning accuracy or "AI slop"; falling returning-viewer share | Visible sources in description, corrections policy, a consistent human editorial voice |
| Style inconsistency | Visual drift between episodes | Brand tokens and series bible; HyperFrames check; golden-episode comparison |
| Creator burnout / over-production | Gates skipped, QA backlog | Batching, fewer episodes, automated checks for mechanical items, weekly cap, decision log review |
| Policy drift | Rule changes on YouTube/VN law | Monthly policy review; confirm claims on YouTube primary pages, not blogs |

### Gaps
- YouTube's primary YPP policy text, Creator Insider posts and the Help page on inauthentic content were not opened.
- No sourced data on copyright strike rates for AI-assisted channels, nor on burnout; the burnout row is general reasoning.
- No peer-reviewed study of AI-channel failure modes found; sources are trade press.
- Music license and Content ID guidance not researched.
