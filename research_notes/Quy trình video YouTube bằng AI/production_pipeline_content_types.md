# YouTube production pipeline and content-type variants (as of 2026-10-09)

**Access caveat for the whole file.** Every page fetch failed: WebFetch returned DNS errors (getaddrinfo ENOTFOUND) and curl through the proxy returned 403. Everything cited below therefore comes from **search-result snippets and the search tool's summaries only**. No page was read in full. Quoted wording may be paraphrased by the search tool. Verify against the live page before quoting, especially YouTube Help pages. The numbers I could source are listed explicitly; I did not use any figure that lacked a URL.

**Incomplete sections (stated plainly):**
- Q2 (content-type variants): the per-type skeletons are mostly my own synthesis, not sourced. Only a few type-specific facts are sourced (Kurzgesagt, video essays, finance regulation, Shorts metrics, sponsorship disclosure). I found no sourced benchmark for typical length per type.
- Q4 (roles and AI vs human split): the roles are sourced from vendor blogs only. The AI/human split is my inference, built from YouTube's AI-disclosure and inauthentic-content policies.
- Q1 and Q3: I found no official YouTube Creator Academy workflow page and no primary-source retention study.

---

## Q1. Canonical stages of YouTube production, with deliverables and gates

### Takeaway
No official YouTube page defines a stage-by-stage workflow. I found only a 2012 YouTube workshop series organised as pre-production, production and post-production. The modern pipeline comes from agency and vendor guides, which agree on a sequence of ideation/validation, scripting, shooting or asset creation, editing with review rounds, packaging, publishing and measurement. The deliverables and gates below are therefore my synthesis, anchored to the cited sources.

### Cited Findings
- The only official YouTube material the search surfaced on production phases is a 2012 creator workshop series, structured as pre-production (storyboarding, equipment), production (cinematography, lighting) and post-production. It is a decade old and may not reflect the current Creator Academy. The search did not surface any current Creator Academy workflow page. — [YouTube Creator blog, 2012](https://youtube-creators.googleblog.com/2012/07/upcoming-educational-workshops-on.html); [YouTube blog, partner workshop on budgeting](https://blog.youtube/news-and-events/upcoming-partner-workshop-budgeting-101/) (snippet only)
- One agency guide describes an eight-stage YouTube pipeline whose Stage 1 is "Ideation and Topic Validation", described as data-driven rather than brainstorming, with every video passing through the stages in order. — [Tubecore / Xpand Digital pipeline guide](https://tubecore.xpanddigital.io/blog/youtube-production-pipeline-guide) (snippet only; the other seven stages were not visible)
- A four-stage model splits work into pre-production, production, post-production and promotion. Pre-production covers goal, narrative script, budget and timeline. — [Eklipse workflow guide](https://blog.eklipse.gg/beginner-guide-2/youtube-video-production-workflow.html) (snippet only)
- An agency-oriented guide adds business stages around the craft: an objective-and-metric phase at the start, and a final phase covering distribution, search visibility and review. — [Moon B guide](https://www.moonb.io/blog/video-production-for-youtube) (snippet only)
- Another guide frames pre-production as turning a rough idea into a production-ready brief that ties together title, thumbnail, hook, script and visuals before money is spent. — [Overseer OS pre-production guide](https://www.overseeros.com/blog/youtube-pre-production-workflow) (snippet only)
- A workflow guide describes scheduling shoot days once planning is done, gathering B-roll, music and overlays for the editor, tracking edits through review and sign-off, then finalising thumbnail, description and scheduling before release. — [Primal Video process](https://primalvideo.com/guides/video-content-creation-our-process-from-youtube-video-idea-to-release/) (snippet only)
- Agencies run review in widening rounds (client team first, then broader stakeholders), followed by finishing (colour grade, sound mix) and cutdown deliverables for A/B testing. — [C-I Studios](https://c-istudios.com/a-streamlined-video-production-process-for-youtube/) (snippet only)
- YouTube Studio has an "Inspiration" tab (the renamed Research tab) under Content. It shows nine AI-suggested ideas based on channel data, plus titles, thumbnails and outlines. Help says the suggestions may be inaccurate or inappropriate. Per the snippet it is desktop-only and English-only. — [YouTube Help: Inspiration tab](https://support.google.com/youtube/answer/15575509?hl=en)
- YouTube Studio's A/B test lets creators test up to 3 titles/thumbnails. The option with the highest watch time is shown to all viewers at the end. It is desktop only, excludes Shorts, scheduled Lives and Premieres (Premieres become eligible after converting to long-form), reports under the Reach tab, and defaults to the first uploaded option if the result is inconclusive. — [YouTube Help: A/B test titles & thumbnails](https://support.google.com/youtube/answer/16391400?hl=en)
- The older thumbnail test help page says a test may end with no winner if thumbnails differ little or the video has too few impressions. — [YouTube Help: Test & compare thumbnails](https://support.google.com/youtube/answer/13861714)
- Paid promotion: creators must tick the paid-promotion declaration in Studio. Creators and brands are responsible for complying with local disclosure law, and YouTube may act on content or the account otherwise. YouTube shows a disclosure at the start of the video. — [YouTube Help: paid product placements, sponsorships & endorsements](https://support.google.com/youtube/answer/154235?hl=en); [YouTube blog: paid promotion disclosure feature](https://blog.youtube/news-and-events/a-new-optional-feature-for-paid/)
- AI/synthetic disclosure: creators must disclose realistic content that could be mistaken for a real person, place or event made or altered with generative AI (examples: realistic likeness, altered real-event footage, realistic fictional major events). Disclosure is not required for clearly unrealistic/animated content, or for using AI for productivity such as scripts, ideas or automatic captions. For sensitive topics (the snippet lists elections, conflicts, disasters, health, finance) the label can appear on the player itself. YouTube may add the label itself if the creator does not. — [YouTube Help: altered or synthetic content](https://support.google.com/youtube/answer/14328491?hl=en-GB); [YouTube blog](https://blog.youtube/news-and-events/disclosing-ai-generated-content). One third-party guide references a May 2026 labelling update that I could not confirm; check Help.
- Chapters: third-party guides state the first timestamp must be 0:00, at least three timestamps are needed, each at least 10 seconds, and malformed timestamps are ignored. The YouTube Help page itself was not surfaced. A "max 50 chapters" claim appeared in only one source. — [Dickinson Media Center](https://blogs.dickinson.edu/mediacenter/2026/01/12/youtube-adding-video-chapters/); [Nymynet](https://nymynet.com/how-to-add-chapters-to-a-youtube-video-youtube-timestamp-mistakes-to-avoid/)
- Monetisation: YouTube renamed "repetitious content" to "inauthentic content" in the Partner Program from 15 July 2025. It frames this as a clarification of long-standing ineligibility. Cited examples are channels uploading "narrative stories with only superficial differences" and "slideshows that all have the same narration". The update does not ban AI tools; content needs "significant original commentary, modifications, or educational or entertainment value". — [Social Samosa](https://www.socialsamosa.com/news-2/youtube-clarifies-monetisation-policy-targeting-inauthentic-content-9493155); [Mediaweek](https://www.mediaweek.com.au/?p=242629); [Gulf News](https://gulfnews.com/technology/youtube-updates-monetisation-policies-ai-and-repetitive-content-ban-begins-july-15-1.500192660). Secondary coverage only; the YPP policy page was not read.
- Kurzgesagt's own page describes its process: research from books and primary sources, expert consultation, a source sheet per video, scripts rewritten about a dozen times, then sketching of visual metaphors, illustration, narration setting the animation timing, and a composed soundtrack. Scripting is the bottleneck, taking from "a few weeks" to much longer. — [Kurzgesagt: our video process](https://kurzgesagt.org/youtube/) (snippet/summary; the headcount and hours figures in the same results came from third-party pages and are not reproduced here)
- The MrBeast production handbook (leaked 2024; authenticity not officially confirmed, though two former producers reportedly confirmed it to Passionfruit) tracks CTR, AVD and AVP as core metrics. — [Passionfruit](https://passionfru.it/?p=81151); [Net Influencer](https://www.netinfluencer.com/mrbeast-productions-leaked-internal-document-rosanna-pansino/)

### Inferences
Proposed universal stage list with a deliverable and a gate per stage. This is my synthesis; the sources support the sequence, not the exact gates.

| # | Stage | Deliverable | Gate (go / no-go) |
|---|---|---|---|
| 0 | Objective and audience | One-line promise, target viewer, success metric (e.g. CTR, AVD, AVP) | Promise stated in one sentence |
| 1 | Idea and validation | Topic brief with title/thumbnail concept and evidence of demand (Studio Inspiration, search, outlier videos from comparable channels) | Title+thumbnail concept exists before scripting; demand evidence recorded |
| 2 | Research | Source sheet (claim, source URL, date, primary or secondary), data files, expert-review notes | Every factual claim and number has a source; unresolved items flagged |
| 3 | Script | Hook, beats, payoff, CTA; narration text | Hook proves the title in the opening; fact check passed; legal/policy check (finance, sponsorship, AI disclosure) |
| 4 | Storyboard / shot list | Scene table: narration line, visual, on-screen text, source | Every line has a visual or a deliberate "talking head" |
| 5 | Asset creation | Footage, charts, animation, B-roll, licensed music, rights log | Rights cleared; numbers on charts match the source sheet |
| 6 | Voiceover | Recorded or synthetic narration, clean audio | Pronunciation of terms and numbers checked; synthetic voice use assessed against disclosure rules |
| 7 | Edit | Rough cut, then fine cut, then locked picture | Retention review of rough cut; no unsourced numbers on screen |
| 8 | QA | Final export, captions, audio levels, chapter list | Checklist pass (facts, audio, captions, links) |
| 9 | Packaging | 1-3 titles and thumbnails, description, chapters, paid-promotion and altered-content declarations | Thumbnail/title do not overpromise relative to the video |
| 10 | Publish | Scheduled upload, pinned comment, end screens | Declarations set in Studio |
| 11 | Post-publish | Analytics review (retention curve, CTR, A/B result), corrections log, lessons fed back to stage 1 | Written learning per video |

### Gaps
- No current official YouTube production-workflow page found (Creator Academy content not reachable via search).
- Agency guides are vendor marketing; none provides data that a given gate improves outcomes.
- The other seven stages of the Tubecore pipeline were not visible in the snippet.

---

## Q2. How the process varies by content type

### Takeaway
Distinct variants are justified mainly by where research and fact-checking weigh most, by length and pacing norms, and by compliance exposure (finance, sponsorship, AI disclosure). The skeletons below are my synthesis; only a few type-specific facts are sourced, and no source gives typical length per type.

### Cited Findings
- Video essay / documentary: narration track plus illustrative visual track; the script carries the argument, and without a well-researched argument the visuals add little. Fact-checking is described as a basic requirement, and some creators put bibliographies in descriptions or on-screen citations. The source claims a 20-minute piece can take hundreds of hours; this is an SEO-grade source and the figure is unverified. — [Influencers-Time on video essays](https://www.influencers-time.com/the-2025-resurgence-of-the-long-form-youtube-video-essay/) (low-authority, snippet only)
- Explainer with heavy research (Kurzgesagt): research decides whether a topic becomes a video; expert review, source sheets per video, many script drafts; visuals created after the script is locked. — [Kurzgesagt](https://kurzgesagt.org/youtube/)
- Shorts: "Viewed vs swiped away" is a hook metric (share of feed impressions where viewers stayed), not completion. Average percentage viewed can exceed 100% due to looping. YouTube publishes no official threshold; compare against your own Shorts of similar length. Third-party guides suggest roughly 75-80% targets; these are rules of thumb, not official. One example channel's 90-day ratio was 26.6% viewed vs 73.4% swiped away (single anecdotal example). — [ContentStudio Shorts analytics guide](https://contentstudio.io/blog/youtube-shorts-analytics-guide); [Subscribr Shorts analytics](https://subscribr.ai/youtube-strategy/youtube-shorts-analytics-metrics-viral); [Shortimize](https://www.shortimize.com/blog/youtube-shorts-retention-rate) (all snippet only, vendor blogs)
- Faceless channels: YouTube's inauthentic-content clarification targets same-narration slideshows and superficially varied narrated stories, so a faceless pipeline needs original commentary, analysis or data per video. — [Social Samosa](https://www.socialsamosa.com/news-2/youtube-clarifies-monetisation-policy-targeting-inauthentic-content-9493155)
- Faceless guidance (third-party consultant): change what is on screen every 5 to 10 seconds; this is one consultant's advice, not evidence. — snippet attributed in search to a script-writing guide: [River Editor](https://rivereditor.com/guides/how-to-script-youtube-videos-2026)
- Product review / sponsored content: paid promotion must be declared in Studio and per local law. — [YouTube Help](https://support.google.com/youtube/answer/154235?hl=en). Affiliate-link rules were not found in YouTube's pages; the search suggested checking FTC endorsement guidance (not read).
- Finance: I found no dedicated YouTube Community Guidelines section on investment advice. The closest official hooks are deceptive-practices and impersonation rules. Regulators have acted: India's SEBI barred three individuals from securities markets for five years over misleading YouTube videos. — [Outlook Business](https://www.outlookbusiness.com/news/sebi-bans-three-individuals-from-market-for-5-years-for-misleading-investors-via-youtube-videos); South Korea's financial regulator referred unregistered "finfluencers" to law enforcement — [Asia Economy](https://view.asiae.co.kr/en/article/2026041215475771641). A third-party study reported 41.8% of sampled YouTube finance videos met its (broad) "misleading" threshold; advocacy-grade, snippet only — [PPC Land](https://ppc.land/youtube-carries-41-8-misleading-finance-videos-the-highest-of-four-platforms/).
- Vietnam: the State Securities Commission (UBCKNN) fined Dau tu ITP 225 million VND for providing licensed-type securities investment advice online without a licence (buy/sell/hold recommendations in posted stock analysis, 1 Dec 2025 to 1 Apr 2026), and warned that unlicensed parties issuing buy/sell/hold calls on social media breach the Securities Law (Article 12, clause 4; Article 4, clause 32 for the definition). — [Doanh nhan & Phap luat](https://doanhnhan.baophapluat.vn/dau-tu-itp-bi-phat-225-trieu-dong-va-cam-hoat-dong-chung-khoan-2-nam-do-tu-van-trai-phep.html); [Vietnamfinance](https://vietnamfinance.vn/dau-tu-itp-bi-phat-hang-tram-trieu-vi-tu-van-dau-tu-chung-khoan-chui-d143564.html). A headline-level report says KOLs/KOCs will be legally required to verify products before advertising from 2026; I did not verify the legal text — [LSVN](https://lsvn.vn/chinh-sach-quan-ly-hoat-dong-kol-cua-cac-nuoc-a161161.html) (summary only).
- Medical misinformation policy is detailed (prevention, treatment, denial) with educational/documentary exceptions; relevant to health-adjacent explainers. — [YouTube Help](https://support.google.com/youtube/answer/13813322?hl=en)

### Inferences
Variant table (skeleton and weighting are my synthesis; lengths are deliberately omitted because I found no sourced benchmark).

| Type | Skeleton | Research and fact-check weight | Main failure modes |
|---|---|---|---|
| Explainer / educational | Hook (the question or surprising claim) -> context -> 3-5 concept beats with an example each -> payoff/synthesis -> CTA | High: concept accuracy, source sheet, expert review | Jargon before motivation; unsupported claims; slow intro |
| Tutorial / how-to | Hook (the end result shown) -> prerequisites -> numbered steps -> result check -> troubleshooting -> CTA | Medium: step correctness, tested end to end | Steps that fail when followed; skipped prerequisites |
| News / commentary | Hook (what happened and why it matters) -> facts -> context -> take -> what next | Highest on speed: verification under deadline; separate fact from opinion | Errors from haste; stale information; missing corrections |
| Documentary / video essay | Hook/thesis -> chapters with escalating argument -> counterpoint -> resolution | Very high: primary sources, citations | Thesis drift; length without payoff; unattributed quotes |
| Storytelling / narrative | Hook (a story moment) -> setup -> escalation -> climax -> payoff | Medium: factual basis if true-story; rights for footage | Same-template stories at scale (monetisation risk per inauthentic-content policy) |
| Listicle / top-N | Hook -> N items with consistent mini-structure -> best-item payoff | Medium: each item verified | Padding; items with no distinct value |
| Product review | Hook (verdict teaser) -> context -> tests/evidence -> pros/cons -> verdict | High: first-hand testing; disclosure | Undisclosed sponsorship; no real testing |
| Finance / trading / data-driven | Hook (the question or data surprise) -> data and definition -> mechanism -> scenarios and risks -> takeaway (educational, not advice) | Very high: dated figures, primary data, chart-to-source match | Stale or wrong numbers; implied buy/sell advice (legal risk, esp. in Vietnam); guaranteed-return phrasing |
| Interview / podcast with visuals | Cold-open highlight -> intro -> topic segments -> close | Medium: guest background, pre-interview brief | Long dead stretches; no packaging promise |
| Shorts / vertical | Hook in the first second -> one point -> loop/payoff | Medium: single claim must be right | Weak hook (low viewed rate); content dropped from context |
| Faceless | As the underlying type, plus original angle per video | As underlying type | Template sameness; voice/visual repetition; synthetic-media disclosure when realistic |

### Gaps
- No sourced typical lengths per content type.
- No sourced skeletons for listicle, review, news, interview or tutorial; those rows are unsourced synthesis.
- The Vietnamese rules on finance KOLs: only one enforcement case and a headline-level summary found; a Vietnamese securities lawyer or the Securities Law text should confirm where educational explanation ends and regulated advice begins.

---

## Q3. Retention and structure principles: official vs folklore

### Takeaway
YouTube's official documentation explains how to read retention data (key moments, intro, spikes, dips, comparison to typical retention) but, in what I could see, sets no numeric target and no prescription for hooks. Hook length, open loops, pattern-interrupt cadence and similar rules are creator and vendor folklore with no published methodology.

### Cited Findings
**Official (YouTube documentation, via snippets)**
- The key moments for audience retention report shows how well different parts of a video held attention; it is available per video, data typically takes 1-2 days to process, and highlights need a video at least 60 seconds long with at least 100 views. Dips mark spots viewers skipped or left, and YouTube suggests reviewing them. — [YouTube Help: key moments for audience retention](https://support.google.com/youtube/answer/9314415?hl=en)
- The report's "Intro" metric is the share of viewers still watching after the first 30 seconds (as summarised by vidIQ from YouTube's definition; I did not see the Help text itself). — [vidIQ](https://vidiq.com/blog/post/increase-audience-retention-youtube/)
- Studio compares your retention with typical retention for similar videos ("typical audience retention" was introduced as a feature). — [Search Engine Journal](https://www.searchenginejournal.com/youtube-typical-audience-retention/421700/); [Search Engine Land](https://searchengineland.com/youtube-audience-retention-analytics-438837)
- The search found no YouTube-official "first 30 seconds" benchmark and no official "good retention" number. — snippet summary of [YouTube Help](https://support.google.com/youtube/answer/1715160?hl=en)

**Published data**
- Vidyard analysed 2022 data from over 1.7 million business videos and reported completion rates of 66% (under 1 minute), 56% (1-2 minutes), 50% (2-10 minutes), 39% (10-20 minutes) and 22% (over 20 minutes). This is business-video data, not a YouTube-wide measure, and I saw only the summary. — [MarketingProfs chart](https://www.marketingprofs.com/charts/2023/49949/business-video-benchmarks-retention-rates-by-length)
- A Tubecore guide lists median average-percentage-viewed by length bracket (for example 55% for 1-3 minutes, 38% for 8-15 minutes, 22% for 30-60 minutes) but cites no data source, so treat as a heuristic only. — [Tubecore AVD guide](https://tubecore.xpanddigital.io/blog/youtube-average-view-duration-guide)
- I found no public YouTube-wide retention dataset or peer-reviewed analysis.

**Creator practice (anecdotal; labelled as folklore)**
- The leaked MrBeast handbook (authenticity not officially confirmed) emphasises the first minute as the point of greatest viewer loss, treats it as proof the thumbnail promise is met, and plans re-engagement content at 3 and 6 minutes. It tracks CTR, AVD and AVP. — [Passionfruit](https://passionfru.it/?p=81151); [Zack Chewning summary](https://zackchewning.substack.com/p/content-lessons-from-the-1-youtubers) (secondary)
- Hook length of 10-15 seconds (GetResponse), "prove the title in the first 10 seconds, say why it matters in the next 10, tease periodically" (Gotranscript summary), and a sharp early drop signals a hook problem while a slow mid-video slide signals a retention problem (Outlier Kit). — [GetResponse](https://www.getresponse.com/blog/youtube-hacks); [Outlier Kit](https://outlierkit.com/resources/youtube-hooks-and-retention/); [Gotranscript](https://gotranscript.com/public/how-to-write-youtube-hooks-and-scripts-that-hold-attention). None cites methodology.
- Pattern interrupts such as B-roll are said to increase retention; hook-deliver-repeat loops are recommended. — [uppbeat](https://uppbeat.io/blog/youtube-growth/youtube-analytics/youtube-audience-retention) and similar vendor blogs. No evidence offered.
- Several sites quote precise stats (e.g. a 78% 30-second retention for "matched hooks", ranking multipliers at 50% retention). I found no methodology behind these and did not rely on them.

### Inferences
- Treat as evidence-backed: using the retention report, intro metric and typical-retention comparison to diagnose a specific video; the hook-vs-middle diagnosis logic is reasonable but still vendor-sourced.
- Treat as folklore until tested on the channel: 10-15 second hooks, open-loop cadence, re-engagement at fixed minutes, B-roll cadence of 5-10 seconds, chapters boosting retention.
- A practical framework gate: compare each rough cut against the channel's own prior videos of similar length, not against internet benchmarks.

### Gaps
- Could not read YouTube Help or Creator Insider pages directly; no Creator Insider quote verified (one article's attribution to Creator Insider could not be found).
- No independent, methodologically transparent retention study found.
- No evidence found on chapters' effect on retention.

---

## Q4. Roles, hand-offs, and AI vs human split

### Takeaway
Vendor guides list a consistent set of roles (producer, writer/researcher, editor, thumbnail designer, channel manager, creative director) and say the creator keeps final approval. No source gave a rigorous approval workflow, and none gave an evidence-based AI vs human split; the split below is my inference anchored to YouTube's policies.

### Cited Findings
- Roles listed: thumbnail designer (described as arguably the highest-leverage first hire), video editor (can take 40+ hours per video, per one vendor), writer/researcher, producer (central hub coordinating the pipeline), channel manager (admin and SEO), creative director (brand consistency), virtual assistant. — [Subscribr: building a team](https://subscribr.ai/youtube-strategy/youtube-video-production-team-hire); [vidIQ: YouTube jobs](https://vidiq.com/blog/post/youtube-jobs-content-creators); [Overseer OS: faceless team roles](https://www.overseeros.com/blog/faceless-youtube-team-roles). Vendor marketing; treat as practitioner opinion.
- The creator usually keeps final approval; team members can draft titles and descriptions. A common failure is isolated tasks handed over without title, thumbnail promise, audience, source material and examples; another is hiring an editor before the script has visual direction. — [Subscribr](https://subscribr.ai/youtube-strategy/youtube-video-production-team-hire)
- Kurzgesagt's editorial team was described as including a head of research, two fact checkers, two researcher-scriptwriters and a social media editor (third-party description, possibly dated). — [Kurzgesagt page and secondary summary](https://kurzgesagt.org/youtube/)
- YouTube's policy treats AI use for scripts, ideas and automatic captions as not requiring disclosure, but realistic synthetic likeness or altered real-event footage does. — [YouTube Help](https://support.google.com/youtube/answer/14328491?hl=en-GB)
- Studio's own AI (Inspiration tab) comes with a warning that output may be inaccurate. — [YouTube Help](https://support.google.com/youtube/answer/15575509?hl=en)
- Monetisation requires original value rather than mass-produced output, even when AI tools are used. — [Social Samosa](https://www.socialsamosa.com/news-2/youtube-clarifies-monetisation-policy-targeting-inauthentic-content-9493155)

### Inferences
Proposed decision-rights split (my synthesis, not sourced):

| Stage | AI can do | Human owns (approval gate) |
|---|---|---|
| Idea / validation | Generate and cluster candidate topics, summarise competitor outliers | Choosing the topic and promise; judging audience fit |
| Research | Gather and summarise sources, draft source sheet, extract data | Verifying each claim against a primary source; accepting the source sheet |
| Script | First draft, hook variants, rewriting for clarity and Vietnamese phrasing | Thesis, opinion, factual accuracy, compliance with advice/licensing limits; final script sign-off |
| Storyboard / shot list | Scene table, visual suggestions | Approving visual metaphors and any chart numbers |
| Assets | Draft charts, animation, B-roll candidates | Rights clearance; deciding when realistic synthetic imagery needs disclosure |
| Voiceover | Synthetic narration, pronunciation lists | Voice identity choice, disclosure decision, pronunciation of numbers |
| Edit | Rough assembly, caption generation, silence trimming | Fine cut and pacing, retention-based edits |
| QA | Automated checks (numbers vs source sheet, caption spelling, link checks) | Final pass and publish approval |
| Packaging | Title/thumbnail options | Choosing the winner; honesty of the promise; declarations in Studio |
| Post-publish | Report generation, retention-curve summaries | Interpreting the cause, deciding what changes |

Rule of thumb: AI proposes, a human approves at every gate that carries factual, legal or reputational risk (facts, finance claims, sponsorship and AI declarations, final publish). For a Vietnamese finance/economics creator, keep "no buy/sell/hold recommendation" as a hard script-gate check, given the UBCKNN enforcement example above.

### Gaps
- No sourced formal approval workflow (script, rough cut, final sign-offs) beyond vendor opinions.
- No evidence on AI quality or error rates at any stage.
- Hand-off templates (brief fields) are my suggestion; vendor sources only name the failure, not a template.
