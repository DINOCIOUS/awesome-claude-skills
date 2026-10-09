# Style systems and consistency for AI-produced YouTube videos (as of 2026-10-09)

Method and source-quality note for the report writer:
- The WebFetch tool and direct curl could not reach most hosts in this environment (w3.org, wikipedia, material.io, support.google.com, businesswire, huggingface, arxiv were all blocked or unresolvable). Only github.com / raw.githubusercontent.com was reachable. So: items marked **[primary, read in full]** were read from raw GitHub files; items marked **[search snippet only]** are taken from WebSearch result summaries and were NOT opened. Please treat snippet-only numbers as "reported by", and re-verify before publishing.
- Many audience-reception sources are vendor-funded or trade press; this is flagged inline.
- Nothing here is from the end user's own channel data. Local context file in the repo: `/home/user/awesome-claude-skills/reports/skill-tests/03-hyperframes.md` (an earlier in-repo test of HyperFrames; it states Apache-2.0, deterministic local MP4 render, built-in WCAG-contrast check, font and CDN pitfalls, and that MusicGen weights are CC-BY-NC so unsuitable for monetized channels). That file cites its own sources; I did not re-verify them except the HyperFrames README below.

---

## 1. Style archetypes in YouTube production: cost, AI-friendliness, content types, pitfalls, references

### Takeaway
Archetypes split into two families by how reliable they are with AI: (A) "rendered in code or from deterministic assets" (kinetic type / data motion graphics, screen recording, whiteboard/hand-drawn via vector assets, Manim-style explainers) where style can be locked exactly; and (B) "generated pixels" (cinematic AI scenes, photoreal avatars, AI b-roll) where consistency and viewer trust are weakest. YouTube's July 2025 "inauthentic content" policy and the 2026 anti-"AI slop" push make family B, especially mass-produced faceless variants, the highest-risk for reach and monetization.

### Cited Findings

**Platform and policy context that shapes which archetypes are safe**
- YouTube renamed its "repetitious content" rule to "inauthentic content" effective July 15, 2025; it targets mass-produced/repetitive uploads (named examples: near-identical narrated slideshows, minimally altered story variations); YouTube said creators can still use AI as part of production if the final content is original and adds value; reaction and clip-based content said to be unaffected. **[search snippet only]** — [Plagiarism Today](https://www.plagiarismtoday.com/2025/07/08/youtube-targets-inauthentic-content/), [AlternativeTo](https://alternativeto.net/news/2025/7/youtube-updates-its-policy-to-demonetize-inauthentic-mass-produced-ai-generated-content), [eWeek](https://www.eweek.com/news/youtube-responds-to-ai-concerns/). The snippet itself notes that the full policy text should be checked on YouTube's YPP policy page (not reachable here).
- Neal Mohan's January 2026 annual letter listed managing low-quality AI content ("AI slop"), deepfake/likeness detection and AI creation tools as 2026 priorities; YouTube said it will reduce visibility of low-quality AI content by strengthening existing spam/clickbait/repetition systems, and keep requiring disclosure of realistic altered/synthetic media. **[search snippet only; the snippet says the primary letter was not opened]** — [Bloomberg](https://www.bloomberg.com/news/articles/2026-01-21/youtube-ceo-says-battling-ai-slop-a-top-priority-in-2026), [Engadget](https://engadget.com/entertainment/youtube/youtube-ceo-promises-more-ai-features-in-2026-162409452.html), [Gigazine](https://gigazine.net/gsc_news/en/20260122-youtube-ai-slop).
- Kapwing study (Dec 2025): on a fresh account, 104 of the first 500 YouTube Shorts (21%) were AI "slop" and 33% were "brainrot". **[search snippet only]** — [The Decoder](https://the-decoder.com/one-in-five-youtube-shorts-shown-to-new-users-is-ai-generated-slop-study-finds/), [Kapwing research page](https://www.kapwing.com/de/research).
- Late July 2026: Kurzgesagt said YouTube's automated detection misclassified its hand-made animation as AI slop and throttled a video (reported as the channel's worst-performing upload since 2013 despite above-average CTR/watch time); YouTube staff reportedly confirmed the misclassification. Reported harm was reduced reach, not confirmed demonetization. **[search snippet only]** — [Dexerto](https://www.dexerto.com/youtube/youtubes-ai-slop-detector-incorrectly-targets-kurzgesagt-as-other-creators-fear-same-fate-3395930/), [Creator Handbook](https://www.creatorhandbook.net/kurzgesagt-says-youtube-mistook-its-animation-for-ai-slop/). One secondary source claims faceless human-made channels report broad demonetization — [Kompozy](https://kompozy.io/news/youtube-ai-detection-backlash) (low-reliability aggregator; unverified).
- YouTube requires creators to disclose realistic content (that a viewer could mistake for a real person/place/event) made with altered or synthetic media; clearly unrealistic, animated, special-effects content and "production assistance" uses do not need the label. **[search snippet only]** — [9to5Google](https://9to5google.com/2024/03/18/youtube-altered-content-disclosure/), [Search Engine Journal](https://searchenginejournal.com/youtube-introduces-mandatory-disclosure-for-ai-generated-content/511392). The SEJ-linked snippet says sensitive topics (health, news, elections, finance) can get a more prominent on-video label; the same snippet notes labels alone do not affect recommendation/monetization per YouTube's head of editorial (secondary report).

**Cost / complexity benchmarks by style (human-studio pricing, vendor estimates, wide ranges) — all [search snippet only]**
- Kinetic typography 60-second video: about $1,000-$5,000 in one guide, $1,200-$2,200 in another B2B price list. Whiteboard: about $500-$2,000 per minute for classic styles up to $2,000-$5,000 for character-heavy; "usually among the cheapest". 2D motion graphics: wide ($1,000-$15,000+ per 60s in one source). 2D character animation about $2,000-$4,000 per minute in one guide. 3D animation the most expensive ($4,000-$10,000 per minute in one guide, higher in others). First minute carries most cost (script, storyboard, style development are fixed costs). — [Advids](https://advids.co/pricing/how-much-explanation-animation-video-creation-cost), [Pixune](https://pixune.com/blog/animated-explainer-video-cost/), [MoonB](https://www.moonb.io/blog/how-much-does-animation-cost). No source found for documentary-style per-minute cost.
- Reference for the "gold standard" cost of hand-crafted 2D: a Kurzgesagt-style video of about 9 minutes reportedly takes about 1,200 hours; about 200 illustrated panels, 2-3 illustrators for 8-12 weeks plus animators for 8-10 weeks (sources disagree on whether stages overlap). — [Gigazine summary of the team's talk](https://gigazine.net/gsc_news/en/20200217-science-animation-making), [VideoExplainers](https://videoexplainers.com/?p=9432) **[search snippet only]**.

**Code-rendered / deterministic toolchains (AI-friendly, free) — [primary, read in full]**
- HyperFrames (HeyGen, Apache-2.0): "open-source framework for turning HTML, CSS, media, and seekable animations into deterministic MP4 videos"; animation via GSAP, CSS, Lottie, Three.js, Anime.js, WAAPI; renderer "seeks each frame in headless Chrome and encodes with FFmpeg, so the same input produces the same video"; Node >= 22 badge; ships agent skills for Claude Code etc. — [HyperFrames README](https://raw.githubusercontent.com/heygen-com/hyperframes/main/README.md). (README example loads GSAP from a CDN; the in-repo test report notes CDN access can be blocked and recommends local copies.)
- Manim (Community Edition): "animation engine for explanatory math videos", used for 3Blue1Brown-style videos; MIT-licensed (with 3b1b copyright and community copyright). — [ManimCE README](https://raw.githubusercontent.com/ManimCommunity/manim/main/README.md).
- Remotion (React-based programmatic video): free licence for individuals, for-profit organizations with up to 3 employees, and non-profits (commercial use allowed); larger for-profit orgs need a Company License; copying/modifying to sell your own derivative is disallowed. Note: licence text says it will change in Remotion 5.0. — [Remotion LICENSE.md](https://raw.githubusercontent.com/remotion-dev/remotion/main/LICENSE.md). Not OSI open source ("non-standard"/source-available per [licenses.dev listing, snippet only](https://licenses.dev/npm/remotion/4.0.93)).

**Open-weight generated-video tools (for archetype B) — [primary, read in full]**
- Wan 2.2 (Apache 2.0): includes a 5B TI2V model producing 720P@24fps that "can also run on consumer-grade graphics cards like 4090"; the 14B T2V/I2V commands in the README require at least 80GB VRAM unless offloading variants are used (one 14B variant states 24GB, e.g. RTX 4090); also offers Speech-to-Video (S2V-14B) and Animate-14B (character animation/replacement). — [Wan2.2 README](https://raw.githubusercontent.com/Wan-Video/Wan2.2/main/README.md).
- LTX-Video/LTX-2 (Lightricks): supports image-to-video, multi-keyframe conditioning, video extension, standard LoRA for "style customization", IC-LoRA control models (depth, pose, canny), and says LTX-2 adds synchronized audio+video generation. — [LTX-Video README](https://raw.githubusercontent.com/Lightricks/LTX-Video/main/README.md). (Licence for LTX weights not checked.)

**Viewer-side pitfalls for realistic generated people**
- 2025 EEG experiment (reported): deepfake clips produced a larger N400 response than real footage even though participants rated them similarly to real clips (i.e. the brain flags "wrong" before viewers can say why). **[search snippet only]** — [PRST Media summary](https://prst.media/en/how-do-people-perceive-and-respond-to-ai-videos/). A McDonald's Netherlands AI holiday ad was reported pulled in December 2025 after "creepy" criticism (same snippet). A non-peer-reviewed 2026 CESCG paper tested eight consumer avatar tools and reports even AI-familiar users were fooled by high-fidelity avatars, and cites a 13-study/2,343-participant meta-analysis finding more realistic avatars rated more trustworthy — [CESCG paper](https://cescg.org/wp-content/uploads/2026/04/Halilović-Real-or-Rendered-A-Comparative-Study-of-Fidelity-in-AI-Generated-Avatars.pdf) **[search snippet only]**. Evidence on the uncanny valley is therefore mixed and partly vendor/non-peer-reviewed.

### Inferences
(These are the researcher's synthesis; archetype names/examples not backed by a fetched source are marked "unverified example".)

Suggested catalog for the framework (AI-friendliness = how reliably a free/open pipeline can reproduce the same look; cost = human effort for a solo creator using free tools; risk = platform/audience risk):

| Archetype | AI-friendliness and locking method | Typical content | Main pitfalls | Unverified reference examples |
|---|---|---|---|---|
| Kinetic typography + data-driven motion graphics (code-rendered: HyperFrames/Remotion/Manim/D3) | Very high; 100% tokenized (CSS variables, JSON data); no generated pixels | Finance, economics, news explainers, stats, listicles, shorts | Looks "template-y"; needs real data and sourcing; many scenes become monotone | 3Blue1Brown (Manim, confirmed by Manim README); finance data channels (unverified) |
| Whiteboard / hand-drawn explainer | High if built from a fixed vector asset kit + stroke-reveal animation; medium if AI-generated illustrations with LoRA/style reference | Concept explainers, education, process, "how X works" | Inconsistent line weight with raw image generation; text must be overlaid, not generated | RSA Animate style (unverified) |
| 2D flat/character animation (Kurzgesagt-like) | Medium: AI can draft assets, but a palette-locked vector kit + code animation works better than generated video; hand-crafting is extremely costly (Kurzgesagt ~1,200 h/9 min) | Science, history, philosophy, health | Style-copying/copyright (do not clone a specific channel); false-positive "AI slop" detection risk even for human work | Kurzgesagt (cost figures above) |
| Documentary with b-roll/archival | Medium: depends on licensed/public-domain archival; AI b-roll is the weak link and may need disclosure if realistic | History, geopolitics, finance history, biographies | Rights clearance; AI-generated "archival" can mislead and triggers the realistic-synthetic disclosure rule | Vox/Johnny Harris-type (unverified) |
| Faceless stock-footage narration | High automation but highest "inauthentic content" risk when templated at volume | Listicles, motivation, generic news | Directly resembles YouTube's named "near-identical narrated slideshow" example (snippet) | n/a |
| Cinematic AI-generated scenes | Low-medium: identity drift, flicker, hands; short clips only; heavy compute | Storytelling, fiction, history reenactment, trailers | Uncanny valley, slop perception, disclosure requirement when realistic | n/a |
| 3D animation | Low for a solo free pipeline (Blender-class effort); AI helps with textures/concepts only | Product/space/engineering explainers | Cost | n/a |
| Talking-head with overlays | High for overlays (code-rendered), but requires a real person; the human face is the trust anchor | Finance commentary, education, opinion | Needs camera/lighting/audio craft | n/a |
| Screen-recording tutorial | High: real capture + code-rendered callouts | Software, trading platforms, Excel, AI tools | Privacy of on-screen data; UI drift between versions | n/a |
| Avatar presenter (HeyGen-like or open-weight S2V) | Medium-low; paid services are out of scope; open-weight talking-head quality varies | Corporate training, multilingual repurposing | Trust penalty for synthetic presenters in finance (see section 5); YouTube likeness rules | n/a |
| Retro/film-grain documentary | High if the look is a post-process (LUT, grain, vignette, fonts) over any footage; hides some AI artifacts | History, nostalgia, true-crime-style, finance history | Grain over AI artifacts can look like deliberate concealment; keep disclosure honest | The in-repo DTT skill list mentions a "belgesel-16mm" locked style (user's own, not verified here) |

- For a Vietnamese solo creator avoiding paid services, the most reliable "lockable" archetypes are the code-rendered ones (kinetic/data motion graphics, whiteboard-from-asset-kit, screen recording with overlays, retro post-process look). Reserve generated pixels (cinematic AI, avatars) for short, non-realistic inserts, which also stay outside the "realistic" disclosure trigger.
- Mixing: a robust default is one "primary archetype" (code-rendered, 80-90% of runtime) plus one "accent" (generated or stock inserts) so the channel identity does not depend on the least stable layer.

### Gaps
- No fetched, primary source for the archetype taxonomy itself, per-archetype retention data, or cost/time for documentary or retro styles.
- No verified current text of YouTube's YPP "inauthentic content" policy (support.google.com unreachable); only press coverage.
- No source on whether AI narration over non-realistic visuals triggers the label (a snippet explicitly says sources do not address voice-only narration).
- Licence terms of LTX weights and exact VRAM requirements for quantized variants not checked.
- Reference examples (Vox, Johnny Harris, RSA Animate, specific finance channels) not sourced.

---

## 2. Recommended structure of a video style guide / brand board, with authoritative references

### Takeaway
A video style guide can be built from existing authoritative pieces: W3C Design Tokens format (stable 2025.10) for the token file; WCAG 2.x contrast thresholds (4.5:1 text, 3:1 large text and non-text) for color; SMPTE/EBU safe-area percentages (93%/90%) for TV-style title safety plus platform-specific UI margins for Shorts; Material 3 easing/duration tokens as a ready-made motion vocabulary; EBU R128 and YouTube's -14 LUFS reference for audio; and YouTube's official thumbnail spec and Test & Compare for the thumbnail system.

### Cited Findings

**Token format**
- The Design Tokens Community Group published the first stable Design Tokens Format Module (2025.10) on October 28, 2025; it is a Community Group report, not a W3C Standard; it supports Display P3/Oklch color, aliases/inheritance, theming. **[search snippet only]** — [W3C DTCG announcement](https://www.w3.org/community/design-tokens/2025/10/28/design-tokens-specification-reaches-first-stable-version/), [Format Module](https://www.w3.org/community/reports/design-tokens/CG-FINAL-format-20251028/).

**Color and contrast (WCAG) — [primary, read in full from the w3c/wcag repo]**
- SC 1.4.3 Contrast (Minimum), Level AA: text needs 4.5:1 (large text 3:1). "18 point text or 14 point bold text is judged to be large". Ratios must not be rounded (4.499:1 fails). Logos/logotypes and purely decorative text are exempt; but "text that has insufficient contrast due to corporate identity or brand guidelines is not exempted". Incidental text in photos is excluded. The rationale cites 3:1 from ISO-9241-3/ANSI and 4.5:1 to compensate for roughly 20/40 vision. — [WCAG 1.4.3 Understanding source](https://raw.githubusercontent.com/w3c/wcag/main/understanding/20/contrast-minimum.html)
- SC 1.4.11 Non-text Contrast: 3:1 for visual information needed to identify UI components and states (relevant for chart marks/lines and icons on video). — [WCAG 1.4.11 Understanding source](https://raw.githubusercontent.com/w3c/wcag/main/understanding/21/non-text-contrast.html)
- 1.4.6 (Enhanced, AAA): 7:1 normal / 4.5:1 large text. **[search snippet only]** — [Tabnav summary](https://tabnav.com/academy/wcag/success-criterion-1.4.3).
- Note: WCAG is written for web content; applying it to video frames is a convention (the in-repo HyperFrames test reports an automatic WCAG-AA contrast check of 33/33 text items) — [in-repo report](/home/user/awesome-claude-skills/reports/skill-tests/03-hyperframes.md).

**Motion (Material 3 token values) — [primary, read in full from the material-components-android docs]**
- Easing tokens: standard `cubic-bezier(0.2, 0, 0, 1)`; standard decelerate (enter) `(0, 0, 0, 1)`; standard accelerate (exit) `(0.3, 0, 1, 1)`; emphasized-decelerate `(0.05, 0.7, 0.1, 1)`; emphasized-accelerate `(0.3, 0, 0.8, 0.15)`; linear `(0, 0, 1, 1)`; emphasized is a path-based curve. Duration tokens: Short1-4 = 50/100/150/200 ms; Medium1-4 = 250/300/350/400 ms; Long1-4 = 450/500/550/600 ms; ExtraLong1-4 = 700/800/900/1000 ms. — [Material Components Android Motion.md](https://raw.githubusercontent.com/material-components/material-components-android/master/docs/theming/Motion.md)
- Material guidance (legacy M1/M2 docs, snippet only): scale duration to distance/size of surface change; exiting elements can be quicker; legacy benchmarks around 300 ms for mobile with entering about 225 ms and leaving about 195 ms; over 400 ms feels slow. These are UI timings for interactive apps; no source found that translates them to video pacing. — [Material 1 motion page](https://m1.material.io/motion/duration-easing.html), [Material 2 easing](https://m2.material.io/go/design-easing).

**Safe areas**
- SMPTE ST 2046-1 (2009): safe action area = 93% of width and height of the production aperture; safe title area = 90% of width and height (RP 2046-2 reportedly 90%/90%). Older 1960s values were 90% action / 80% title. Wikipedia lists EBU R95 (Sept 2008, "Safe areas for 16:9 television production") as a reference; its numbers were not seen. **[search snippet only]** — [Wikipedia: Safe area (television)](https://en.wikipedia.org/wiki/Safe_area_(television)), [NAB note](https://www.nab.org/xert/scitech/pdfs/tv031510.pdf).
- YouTube Shorts: no official safe-zone spec found; third-party guides disagree. Examples: centered usable area about 984x1500 px on a 1080x1920 canvas; or top about 100-120 px, bottom about 180-300 px, right about 48-80 px to avoid; ad-placement margins larger (about 241 px top, 381 px bottom, 201 px right). A cross-platform caption box of 900x1400 px centered is suggested. **[search snippet only; third-party, treat as heuristics]** — [Reap](https://reap.video/blog/short-form-video-safe-zones), [Adaptly](https://adaptlypost.com/en/blog/social-media-safe-zones-2026-complete-guide), [AdKit](https://adkit.so/tools/safe-zones/youtube).

**Audio identity and loudness**
- YouTube normalizes playback toward about -14 LUFS (reference moved to -14 LUFS in 2019); quiet videos are not boosted; one guide recommends true peaks at or below -1 dBTP. **[search snippet only; third-party]** — [Frame.io loudness guide](https://workflow.frame.io/guide/loudness-for-youtube), [Production Advice](https://productionadvice.co.uk/stats-for-nerds/), [Meterplugs](https://www.meterplugs.com/blog/2019/09/18/youtube-changes-loudness-reference-to-14-lufs.html).
- EBU R128: programme loudness -23 LUFS, tolerance +/-0.5 LU (v3 2014; v5.0 dated Nov 2023), measured per ITU-R BS.1770; supplement R128 s2 covers streaming. One EBU page snippet says +/-0.2 LU, conflicting. ATSC (USA) -24 LKFS. **[search snippet only]** — [EBU R128](https://tech.ebu.ch/publications/r128), [R128 s2](https://knowledgehub.ebu.ch/files/live/sites/tech/files/shared/r/r128s2v2_0.pdf).
- Open-source Vietnamese TTS candidates (for voice persona without paid services): VieNeu-TTS (listed as Apache-2.0, CPU-friendly, voice cloning from a short reference clip, northern/southern preset voices, per blog/aggregator pages) and VietTTS (dangvansam/viet-tts, Apache-2.0); Kokoro-Vietnamese licence unclear. **[search snippet only; aggregator pages, verify on GitHub/Hugging Face model cards]** — [SonuSahani blog](https://sonusahani.com/blogs/vieneu-tts), [oosmetrics: viet-tts](https://oosmetrics.com/repo/dangvansam/viet-tts), [AI Indigo: Kokoro-Vietnamese](https://aiindigo.com/tool/kokoro-vietnamese). Voice cloning raises likeness/consent questions; YouTube's likeness-detection push is noted in section 1.
- In-repo note: MusicGen weights are CC-BY-NC and flagged as unsuitable for monetized channels (secondary claim by the in-repo report; verify) — [in-repo report](/home/user/awesome-claude-skills/reports/skill-tests/03-hyperframes.md).

**Thumbnail system**
- Google's help page (via search snippet): recommended 1280x720 (minimum width 640 px), under 2 MB for videos (10 MB for podcasts), 16:9 preferred, JPG/GIF/PNG; vertical videos with 16:9 custom thumbnails get an auto-generated 4:5 thumbnail on some surfaces. **[search snippet only]** — [YouTube Help: Add video thumbnails](https://support.google.com/youtube/answer/72431), [TechSmith guide](https://www.techsmith.com/blog/youtube-thumbnail-sizes/).
- Test & Compare: up to 3 thumbnails per video; desktop Studio only; advanced features must be on; public long-form videos only; winner chosen by watch time share (not CTR); results take days up to about 2 weeks; more different thumbnails finish faster. **[search snippet only]** — [YouTube Help: Test & compare](https://support.google.com/youtube/answer/13861714), [Android Central](https://www.androidcentral.com/apps-software/youtube-details-test-compare-thumbnail-experiment).

### Inferences
- A video brand board needs these modules (proposed structure; each should be a token file plus a one-page rule sheet):
  1. Identity: logo variants, clear-space, min size, watermark position, channel name lockup.
  2. Color tokens (DTCG JSON): semantic roles (bg, surface, text-primary, text-muted, accent, positive, negative, chart-1..n), each with a computed WCAG ratio against its intended background; text roles >= 4.5:1, large titles and chart marks >= 3:1; avoid red/green-only encoding (add shape/label).
  3. Typography tokens: font families with Vietnamese diacritic coverage verified (in-repo test confirms embedding the font file is needed or the renderer substitutes a default), size scale for 1080p and 9:16, line-height, weight, number style (tabular figures for data).
  4. Layout: 16:9 and 9:16 grids, safe margins (use at least 90% title-safe for 16:9; Shorts margins from the third-party heuristics, then verify in the mobile app), caption zone, lower-third and chart regions.
  5. Motion tokens: adopt the M3 duration/easing set as a vocabulary (for example fast = Short3/Medium1, normal = Medium2, scene transitions = Long1-2; enter = decelerate, exit = accelerate); max simultaneous animations; no motion that cannot be seeked deterministically for code rendering. Video pacing values are my adaptation; Material's numbers target UI, not video.
  6. Component conventions: lower-third (name/role/source), chart templates (axis, units, source line, label size, highlight rules), citation/source chip on screen, disclaimer card for finance.
  7. Audio identity: loudness target (-14 LUFS integrated with true peak <= -1 dBTP for YouTube, cross-check at -23 LUFS if ever delivered to broadcast), music bed level under voice, sting/transition SFX set, licensing log.
  8. Voice persona: language/accent (northern vs southern Vietnamese), pace (syllables per second target), pronunciation dictionary for tickers/jargon, consent/licence record of the voice model.
  9. Thumbnail system: 3 reusable templates, fixed color roles, max words, face/no-face rule, naming, Test & Compare variants.
  10. Disclosure policy: when AI/synthetic content is labeled and how.
- The in-repo DTT brand skill (listed in the environment) already follows a similar "locked palette + two scene families + review gates" structure; this research could reuse its naming (not re-verified here).

### Gaps
- Official EBU R95 and SMPTE ST 2046-1 documents were not opened; percentages come from Wikipedia/NAB snippets.
- No official YouTube Shorts or long-form safe-zone specification found.
- No authoritative source for video-specific motion durations (frame counts, scene transition lengths) or lower-third conventions; Material tokens are UI motion.
- YouTube Help pages (thumbnails, Test & Compare, loudness) were seen only as snippets.
- No source for chart-in-video conventions (label sizes, color-blind-safe palettes) beyond WCAG non-text contrast.

---

## 3. Keeping AI-generated imagery/video consistent: techniques, reliability by archetype, failure modes, mitigations

### Takeaway
Reliability ranks as: code-rendered tokens (deterministic, exact) > fixed vector/asset kits > image-model style locking (style reference/IP-Adapter, LoRA) > image-to-video with reference frame > text-to-video with prompt-only consistency. Text and numbers should be rendered in code/HTML, because diffusion models do not spell reliably; identity drift in video is a known unsolved problem as of mid-2026 per cautious sources.

### Cited Findings

**Technique documentation**
- LoRA (Microsoft, Hu et al.): freezes pretrained weights and trains low-rank matrices, drastically fewer trainable parameters; you still need the original checkpoint. **[primary, read]** — [microsoft/LoRA README](https://raw.githubusercontent.com/microsoft/LoRA/main/README.md). (The README concerns language models; the same technique is what community image/video LoRAs use, which is general knowledge, not sourced here.)
- ControlNet: "neural network structure to control diffusion models by adding extra conditions", with a locked copy and a trainable copy of weights and zero convolutions. **[primary, read]** — [lllyasviel/ControlNet README](https://raw.githubusercontent.com/lllyasviel/ControlNet/main/README.md).
- IP-Adapter: image-prompt adapter; `scale=1.0` conditions on the image only; lowering scale gives more diverse outputs less aligned to the reference; `scale=0.5` suggested for multimodal prompts; InstantStyle is a related IP-Adapter-based style transfer project. **[primary, read]** — [tencent-ailab/IP-Adapter README](https://raw.githubusercontent.com/tencent-ailab/IP-Adapter/main/README.md). Diffusers docs (snippet only) show restricting the adapter to specific UNet blocks (a "style-only" scale dict) to copy look without composition, and reusing one reference image across prompts. — [Diffusers IP-Adapter docs](https://huggingface.co/docs/diffusers/v0.39.0/api/loaders/ip_adapter).
- Open video models with consistency features: LTX supports multi-keyframe conditioning, IC-LoRA (depth/pose/canny) and standard LoRA "for style customization" ([LTX README](https://raw.githubusercontent.com/Lightricks/LTX-Video/main/README.md), primary). Wan 2.2 offers I2V, S2V and an Animate model for character animation/replacement ([Wan2.2 README](https://raw.githubusercontent.com/Wan-Video/Wan2.2/main/README.md), primary).
- Practitioner guidance (vendor blogs, **[search snippet only]**): each clip starts from noise, so text-to-video has no identity anchor; cuts and camera moves reset attention; anchoring to a reference image at frame 0 is the most accessible fix; combining reference frame + character LoRA + a fixed 50-80 word character prompt block across scenes; faces show drift first; one cautious source states no model in mid-2026 achieves perfect multi-clip character consistency; a vendor claim of "<5% visual variance" was unverified. — [LTX blog](https://ltx.io/blog/how-to-maintain-character-consistency-in-ai-video), [Magic Hour](https://magichour.ai/blog/ai-video-consistency-character-face-tools), [Artlist](https://artlist.io/blog/consistent-character-ai). A Wan 2.1-based studio experiment reported improved identity but unconvincing lip movement and weak motion consistency (older model version).
- Text in generated images: causes given by blogs/press (**[search snippet only]**): models learn letter shapes not spelling, text is a tiny part of training pixels, diffusion refines fine strokes late, older CLIP encoders tokenize at word level, no spell check. — [UX Collective](https://uxdesign.cc/lost-for-words-why-text-in-ai-images-still-goes-wrong-b5232c39bd11), [TechCrunch](https://techcrunch.com/?p=2681821), [DEV Community](https://dev.to/klement_gunndu_e16216829c/ai-image-generators-cant-render-text-heres-why-and-4-fixes-that-actually-work-3i8o). Newer models are improving; one comparison blog says text is still "the hardest content category" for video generators, hands remain a weak point, and generating several takes is standard practice — [PixVerse comparison (vendor)](https://pixverse.ai/en/blog/sora-vs-veo-vs-pixverse-ai-video-comparison), [Skywork FAQ](https://skywork.ai/blog/ai-video/sora-2-how-to-fix-its-5-most-annoying-errors). Reliability of those vendor claims is low; the PixVerse piece also claims Sora 2 went offline March 24, 2026 (uncorroborated).
- Reproducibility metadata: ComfyUI embeds `prompt` and `workflow` JSON into output files; re-encoding can strip it; `--disable-metadata` prevents recovery. **[search snippet only]** — [ComfyUI docs: workflow metadata](https://docs.comfy.org/development/api-development/workflow-metadata).
- Deterministic code rendering: HyperFrames states same input produces same video ([README](https://raw.githubusercontent.com/heygen-com/hyperframes/main/README.md), primary); the in-repo test found local renders can differ across machines (fonts, Chrome version) and recommends Docker for production — [in-repo report](/home/user/awesome-claude-skills/reports/skill-tests/03-hyperframes.md).

### Inferences
Reliability matrix (researcher judgment based on the mechanisms above, not measured):
- Kinetic type/data motion graphics, screen-record overlays, retro post-process: lock everything in tokens/CSS; AI only writes code and copy. Reliability: highest.
- Whiteboard/2D explainer: generate or hand-draw a fixed asset kit once (characters, icons, backgrounds as SVG/PNG with transparent background), then compose and animate in code. If generating raw images: one style-reference image + IP-Adapter at fixed scale + one style LoRA trained on 15-30 curated images (number is a common practitioner range, not sourced) + fixed seed per asset + identical prompt skeleton. Reliability: medium-high.
- Documentary/b-roll: consistency from a grade (LUT/grain applied in post) rather than from generation; prefer real stock/public-domain over generated.
- Cinematic AI scenes/avatars: reference frame at frame 0 + character LoRA + fixed character block + short clips (a few seconds) cut on action; accept shot-level (not frame-level) consistency; plan shots that hide faces/hands. Reliability: lowest.
- Failure-mode mitigations: (1) text/numbers/logos/charts always in HTML/SVG overlays; (2) no hands in focus, wide/OTS shots; (3) keep clips short, cut before drift; (4) generate N takes and pick, log the winner's seed/metadata; (5) upscale/denoise consistently in one final pass; (6) freeze model + LoRA + node versions per season of episodes; (7) validate with an automated check (palette histogram vs tokens, contrast check, text overflow check) before render.
- For a free-tools creator in Vietnam, the practical constraint is GPU: Wan2.2's 5B model on a 24 GB card (per README) is the main open path to local generated video; otherwise stay with code-rendered archetypes.

### Gaps
- No controlled benchmark comparing consistency methods (IP-Adapter vs LoRA vs reference-to-video) per archetype; evidence is README/vendor-blog level.
- Hugging Face / Diffusers / ComfyUI docs could only be seen as snippets.
- No sourced training-set size or LoRA hyperparameters for style LoRAs, and no verified current (Oct 2026) open-weight leaderboard for temporal consistency.
- Licences of specific style/character checkpoints (e.g., SDXL/Flux variants) were not researched.

---

## 4. Versioning and reusing prompts and style tokens across episodes

### Takeaway
No authoritative standard for "prompt libraries" was found; the sources support three building blocks: a DTCG-format token file, embedded generation metadata (ComfyUI) plus workflow JSON kept in git, and deterministic code-rendered scenes where the project folder itself is the version-controlled source of truth. The folder/naming scheme below is a proposal.

### Cited Findings
- The DTCG token format is now a stable (2025.10) Community Group spec with aliases/inheritance and theming, so a style can inherit from a "base" token set and override per series. **[search snippet only]** — [W3C DTCG announcement](https://www.w3.org/community/design-tokens/2025/10/28/design-tokens-specification-reaches-first-stable-version/).
- ComfyUI embeds `prompt` and `workflow` metadata in outputs; metadata can be lost on re-encode, so a separate copy is needed. **[search snippet only]** — [ComfyUI docs](https://docs.comfy.org/development/api-development/workflow-metadata). The search tool's own caveat: seed alone does not reproduce an output; checkpoint, LoRAs, sampler settings and custom-node versions also matter.
- HyperFrames projects are plain HTML/CSS/media with data attributes for timing; generated projects include `CLAUDE.md`/`AGENTS.md` for agent instructions; the tool recommends one sub-composition file per scene (`data-composition-src`) for long videos. — [HyperFrames README](https://raw.githubusercontent.com/heygen-com/hyperframes/main/README.md) (primary) and [in-repo report](/home/user/awesome-claude-skills/reports/skill-tests/03-hyperframes.md).
- LTX docs and Diffusers show LoRA/adapters are small separate files (IP-Adapter files about 100 MB per the Diffusers snippet; an LTX distilled LoRA "requires only 1GB of VRAM" extra per the README), which supports versioning them as named, pinned assets. — [LTX README](https://raw.githubusercontent.com/Lightricks/LTX-Video/main/README.md), [Diffusers docs](https://huggingface.co/docs/diffusers/v0.39.0/api/loaders/ip_adapter).

### Inferences (proposal, not from a source)
```
channel/
  style/                       # the "style system" (versioned, semver)
    tokens.base.json           # DTCG: color, type, space, motion, audio
    tokens.series-<name>.json  # overrides (aliases to base)
    STYLE.md                   # human rules + do/don't + contrast table
    CHANGELOG.md               # v1.2.0: changed accent hex, reason, affected episodes
  prompts/
    image/<archetype>.<role>.v003.yaml   # skeleton + slots + negative + seed policy
    video/<shot-type>.v002.yaml
    voice/persona.v001.yaml              # model, speaker id, speed, pronunciation dict
  assets/                      # character sheets, icon kit, LoRA/adapter files with hash + licence
  templates/                   # lower-third, chart, title, outro, thumbnail
  episodes/EP012-<slug>/
    brief.md  script.md  storyboard.md  data/ (sources + CSV)
    scenes/ (one file per scene referencing tokens)
    gen-log.jsonl              # prompt id+version, seed, model hash, LoRA hash, tool versions, picked take
    qa-report.md               # contrast, overflow, loudness, safe-area checks
    style.lock                 # pins style version + tool versions used
```
- Rules: semantic versioning for style (breaking = palette/typography change; minor = new component; patch = fix); never edit a prompt in place, create a new version and log which episodes used it; pin model/LoRA/tool hashes in `style.lock`; keep generation metadata in both the file and `gen-log.jsonl`; episodes are rendered against a pinned style version so re-renders stay identical; "series" overrides allow multiple formats (long-form, Shorts) under one brand.

### Gaps
- No authoritative source on prompt-library structure or prompt versioning practices was found (search returned none); everything in Inferences is a design proposal.
- No evidence found on how many creators actually version style tokens.

---

## 5. Audience reception evidence: how viewers respond to AI visuals/voices, trust drivers, especially informational/finance

### Takeaway
Evidence consistently shows viewers want disclosure and are wary of being misled, with trust penalties tied more to labeling/expectation than to measurable audio quality; blind tests suggest many listeners cannot detect good AI voices. For realistic synthetic presenters and finance, available evidence is thin, mostly vendor/trade-press or small studies, and no direct measurement of investor reaction to finfluencer-style AI avatars was found.

### Cited Findings
All items below are **[search snippet only]** unless stated.
- Hub Entertainment Research, "AI and Audiences" (November 2025, 2,500 U.S. respondents aged 16-74): 72% say companies should always disclose AI use in content creation; 21% when AI plays a significant role; 7% say no disclosure needed; top concern is being misled / blurred reality. — [NewscastStudio](https://www.newscaststudio.com/2026/01/14/hub-study-finds-growing-comfort-with-ai-tools-but-disclosure-remains-key-for-viewers), [Advanced Television](https://www.advanced-television.com/2026/01/15/survey-audiences-top-ai-concern-is-blurred-reality).
- Animoto (U.S., about 460 participants, fielded September 2025, vendor-commissioned): 82.6% suspected they had watched AI-generated videos; 36% said AI videos reduce brand trust; 77.9% trust videos featuring real people; over a third trust AI content as much as human-made. Self-reported. — [Business Wire](https://www.businesswire.com/news/home/20260121875037/en/83-of-Consumers-Can-Spot-AI-Videos-36-Say-It-Lowers-Brand-Trust-According-to-Animotos-New-Report), [Adweek](https://www.adweek.com/adweek-wire/83-of-consumers-can-spot-ai-videos-36-say-it-hurts-brand-trust-new-animoto-report/).
- HeyGen 2025 AI sentiment report (vendor; 2,385 consumers) reports growing acceptance of AI avatars in brand video; one secondary source quotes 90.4% having no problem with brands using AI avatars. Weigh as vendor marketing. — [HeyGen report](https://www.heygen.com/2025-ai-sentiment-report).
- Aalto University experiment (HICSS 2025, n=107): authors expected AI disclaimers to hurt viewing experience but their data did not support that; small sample. — [Aaltodoc](https://aaltodoc.aalto.fi/items/33777b82-7e9e-443a-a7fa-9539038ea494).
- Reuters Institute Generative AI and News Report 2025 (YouGov, six countries, about 2,000 each, published Oct 7, 2025): 12% comfortable with fully AI-made news, 21% when a human is in control, 43% when journalist-led with AI assistance; 62% prefer news made entirely by humans (as quoted by a secondary site). — [reporterzy.info summary](https://reporterzy.info/en/5307,journalism-in-the-age-of-ai-why-people-prefer-humans-over-machines.html), [NewscastStudio](https://www.newscaststudio.com/2025/10/16/public-use-of-generative-ai-grows-but-trust-and-comfort-with-news-applications-remain-low), [Oxford record](https://ora.ox.ac.uk/objects/uuid:6ac16418-fe70-4fc5-99a1-b3296c82deab). Secondary write-ups; verify numbers in the original report before citing.
- Voice evidence: a radio study (May-June 2026, 1,326 listeners) found human and synthetic voices scored nearly identically on trust, energy, likability, with listeners no better than chance at identifying the human; 33% said knowing a station uses AI voices would make them less favorable, 47% no difference, 21% more favorable — [Radio Ink](https://radioink.com/2026/07/07/radio-listeners-cant-detect-ai-voice-but-dont-trust-it-either/). Studio Resonate (ad-testing firm) reported trust dropped 27% when listeners were primed to expect an AI voice — [ContentGrip](https://www.contentgrip.com/studio-resonate-ai-voice-study/). Adobe Express survey (850 consumers): nearly 3 in 4 think brands should disclose AI voice/music; only 19% accept AI voices in news — [ContentGrip](https://www.contentgrip.com/ai-voices-in-marketing-adobe/). An academic CogSci paper found human recordings conveyed emotion more accurately than TTS (79.82% vs 72.65% in study 1) — [CogSci paper](https://journalpub.escholarship.org/cognitivesciencesociety/article/49426/galley/37388/download). An Edison Research audiobook study commissioned by AI audio company Spoken found AI narration rated higher (sponsor bias). All are trade/vendor sources except the CogSci paper.
- Finance/avatars: a March 2026 randomized experiment dataset (human executive vs digital avatar, AI-written vs human-reviewed disclosure, simulated company, about 75 s earnings video) exists, but results were not retrieved — [Mendeley Data](https://data.mendeley.com/datasets/yb7rmbdxjy/1). A reported FT investigation (via BetaNews) found human creators generated 2.7x more engagement than AI personas — [BetaNews](https://betanews.com/2025/09/11/brands-are-increasingly-testing-ai-influencers-but-trust-in-them-is-low/) (secondary, about influencer marketing generally). An IAB 2026 study reportedly found 82% of ad executives thought Gen-Z/Millennials viewed AI ads favorably versus 45% of consumers actually doing so — via [Digital Applied](https://www.digitalapplied.com/blog/ai-avatar-ads-vs-real-ugc-creators-cost-trust-2026) (secondary).
- Platform: YouTube places more prominent labels for sensitive topics including finance on realistic synthetic content (see section 1 SEJ snippet); labels reportedly do not by themselves affect recommendations or monetization.

### Inferences
- Trust levers consistent across sources: (1) transparency (disclose AI use; mislabeling in either direction hurts), (2) a visible human accountable identity/oversight, (3) verifiable sourcing, (4) avoiding hyper-real synthetic people, (5) voice quality (system quality varies several-fold per a TechRadar-reported Vocal Image study of 10,000+ participants, snippet only: [TechRadar](https://www.techradar.com/pro/people-dont-trust-bad-ai-voices-listeners-rated-a-chinese-startups-synthetic-voices-higher-for-trust-and-realism-than-those-from-microsoft-google-and-amazon)).
- For finance/educational content, a stylized (clearly non-photoreal) visual language with on-screen sources, a named human author, a consistent decent TTS voice, and a standing "AI-assisted, not financial advice" card is the lowest-risk combination. This is consistent with the evidence but is not itself tested by any found study.
- Because detection is imperfect even for human-made work (Kurzgesagt case), a distinct, consistent, hand-curated style and an original-value script are also a protection against mis-flagging.

### Gaps
- No peer-reviewed study of viewer reaction specifically to AI-voiced or AI-visual YouTube finance/education channels; no Vietnamese-audience data found.
- No platform-published data on retention/CTR differences for AI vs human visuals.
- Kapwing's original report and YouTube/Reuters primary documents were not opened (blocked); figures are as reported by press.
- Several surveys are vendor-funded (Animoto, HeyGen, Spoken/Edison, Studio Resonate); no independent replication found.
- The Mendeley investor experiment results were not retrieved.
