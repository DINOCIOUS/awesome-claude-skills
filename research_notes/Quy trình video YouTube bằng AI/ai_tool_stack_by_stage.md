# AI tool stack by stage for YouTube video production (free / open-source first), as of 2026-10-09

Method and access caveat (read first): in this research environment only github.com / raw.githubusercontent.com pages could be fetched. huggingface.co, remotion.dev, elevenlabs.io, support.google.com, ai.google.dev and vendor pricing pages were BLOCKED (proxy 403 / DNS failure). Therefore:
- "GitHub LICENSE/README" claims below were read in full from the repository files (strongest evidence, but they state the CODE license; a Hugging Face model card can differ for the WEIGHTS — flagged per item).
- "Search snippet only" means the claim comes from a WebSearch result summary of third-party pages; the vendor page itself was not read. Treat as needing verification before the creator relies on it.
- Anything I could not confirm is marked UNVERIFIED.

---

## 1. Script writing and research (LLM and research tools)

### Takeaway
I could not retrieve primary pricing/free-tier pages for any LLM service, so free-tier limits for chat LLMs are UNVERIFIED. What is well supported is the pitfall side: LLM-generated citations are frequently fabricated or wrong, even in source-grounded tools such as NotebookLM, so every fact and citation in a script must be checked against the original page. YouTube treats AI use for scripts/ideas/captions as a "productivity" use that needs no synthetic-content label.

### Cited Findings
- Studies cited in an AAAI 2026 abstract report citation-hallucination rates from 18% (GPT-4) to over 70% for other frontier models, up to 88% in legal contexts; a PsyPost write-up reports nearly two-thirds of AI-generated scientific citations were fabricated or erroneous, worst on obscure topics (underlying paper not verified) — search snippet only: [Underline AAAI abstract](https://underline.io/lecture/138676-705-detecting-citation-hallucinations-in-large-language-model-outputs-student-abstract); [PsyPost](https://www.psypost.org/study-finds-nearly-two-thirds-of-ai-generated-citations-are-fabricated-or-contain-errors/embed/)
- NotebookLM (source-grounded): a University of Michigan teaching-consulting page (March 2026) judged hallucination "feels much lower" than other LLMs but unproven, and warned citations can make dishonest material harder to detect — search snippet only: [UMich LSA](https://sites.lsa.umich.edu/learningteachingconsulting/2026/03/12/a-critical-look-at-notebooklm/)
- A 2025 arXiv paper on NotebookLM in medical education says it lacks fact-checking, can repeat outdated information, and its citations can themselves be hallucinated — search snippet only: [arXiv 2505.01955](https://arxiv.org/pdf/2505.01955v1)
- One blog reports "source blindness" (missing info that is present, plausible gap-filling) after a Feb 2026 model change; single secondary source, unconfirmed — search snippet only: [ainauten](https://news.ainauten.com/markdown/der-notebooklm-fehler-der-deine-recherche-ergebnisse-ruiniert)
- YouTube disclosure rule: creators must label realistic altered/synthetic content (e.g., cloned real person's voice, realistic fake events); clearly unrealistic/animated content and "productivity" uses such as generating scripts, ideas or automatic captions are exempt; labels may be forced on sensitive topics (health, finance, elections, conflicts) — search snippet only (Engadget/PPC Land coverage; date of current Help text not confirmed): [Engadget](https://www.engadget.com/youtube-lays-out-new-rules-for-realistic-ai-generated-videos-154248008.html); [PPC Land](https://ppc.land/youtube-introduces-mandatory-disclosure-for-ai-content/)
- YouTube Partner Program "inauthentic content" update (15 July 2025): YouTube says it clarifies existing "original and authentic" requirement to target mass-produced/repetitious content (near-identical narrated slideshows, template story variations, synthesized voice over re-composed others' clips); YouTube's Rene Ritchie called it a "minor update"; commentary/reaction/review remain eligible. Some outlets over-state it as a new AI crackdown — search snippet only: [eWeek](https://www.eweek.com/news/youtube-responds-to-ai-concerns/); [Fliki summary](https://fliki.ai/blog/youtube-monetization-policy-2025)

### Inferences
- A safe script workflow for a creator avoiding paid services: use any free-tier chat LLM or a locally run open-weight LLM (via Ollama/llama.cpp) only for outlining and drafting; do research from primary sources the creator opens themselves; feed those sources into a source-grounded tool (NotebookLM-style) to draft, then manually click through every citation and number. Keep a "claim -> source URL" sheet (this also serves the storyboard step).
- Because YouTube's monetization policy targets mass-produced, templated, voice-over-over-others'-clips content, a human-authored angle, original script editing and original visuals reduce demonetization risk. This is an inference from the snippet-level sources, not a YouTube guarantee.

### Gaps
- Free-tier quotas and commercial terms of ChatGPT, Claude, Gemini, Perplexity, NotebookLM: not retrieved (vendor pages blocked) — UNVERIFIED.
- License of open-weight LLMs (Llama, Qwen, Gemma, Mistral, etc.): not checked — UNVERIFIED; check each model card's license field (HF blocked here).
- No independent 2026 benchmark of citation accuracy for a specific tool was found.

---

## 2. Image generation (keyframes, thumbnails, illustrations)

### Takeaway
For fully free, commercially safe local generation, Apache-2.0 models are the cleanest: FLUX.2 [klein] 4B (~8 GB VRAM), Qwen-Image, Z-Image (code repo is Apache-2.0; weights card not checked), and SANA's code is Apache-2.0. Avoid FLUX.1 [dev], FLUX.2 [dev] and FLUX.2 [klein] 9B for monetized work (non-commercial license). Stable Diffusion 3.5 is free commercially only under $1M annual revenue. Hosted free tiers (Gemini app etc.) are volatile and their commercial terms were not verified.

### Cited Findings
- FLUX.2 [klein] 4B and 4B Base: Apache-2.0; klein 9B, 9B KV, 9B Base and FLUX.2 [dev]: "FLUX Non-Commercial License". klein 4B "fits in ~8GB VRAM (RTX 3090/4070 and up)"; released 15 Jan 2026 (klein), FLUX.2 [dev] 32B on 25 Nov 2025 — [BFL flux2 README](https://github.com/black-forest-labs/flux2/blob/main/README.md)
- FLUX.1 [dev] license: "Non-Commercial License v1.1.1", weights for "non-commercial and non-production use"; the license says outputs may be used for any purpose including commercial, except as expressly prohibited — [FLUX.1 dev license](https://github.com/black-forest-labs/flux/blob/main/model_licenses/LICENSE-FLUX1-dev). (Important nuance: output use is permitted, but running the model for a revenue-generating pipeline is arguably a commercial use of the model; ambiguous — treat FLUX.1 [dev] as NOT recommended.)
- Qwen-Image: "licensed under Apache 2.0"; DiffSynth-Studio supports low-VRAM layer-by-layer offload (inference "within 4GB VRAM"), FP8, LoRA training — [Qwen-Image README](https://github.com/QwenLM/Qwen-Image/blob/main/README.md)
- Z-Image / Z-Image-Turbo (Tongyi-MAI): repository LICENSE is Apache-2.0; Turbo is a distilled 8-NFE variant; supported by stable-diffusion.cpp and DiffSynth low-VRAM inference. Weights license on the HF card NOT checked (HF blocked) — [Z-Image LICENSE](https://github.com/Tongyi-MAI/Z-Image/blob/main/LICENSE); [README](https://github.com/Tongyi-MAI/Z-Image/blob/main/README.md)
- SANA: code base license changed to Apache 2.0 (11 Jan 2025); 4-bit SANA runs within 8 GB VRAM; weights license not checked — [SANA README](https://github.com/NVlabs/Sana/blob/main/README.md)
- stable-diffusion.cpp: MIT, pure C++ engine (CUDA, Vulkan) — [LICENSE](https://github.com/leejet/stable-diffusion.cpp/blob/master/LICENSE)
- ComfyUI (node-based local UI for image/video/audio models): GPL-3.0-style license text in repo (file begins GNU GPL) — [ComfyUI LICENSE](https://github.com/comfyanonymous/ComfyUI/blob/master/LICENSE)
- Stable Diffusion 3.5: Stability AI Community License allows commercial use free for orgs/creators with total annual revenue under US$1M (all revenue counts, not only from the model); above that an Enterprise License is needed; users retain ownership of outputs — search snippet only: [Stability announcement](https://stability.ai/news/introducing-stable-diffusion-3-5); [Stability license page](https://stability.ai/license)
- Gemini consumer app free image generation (Nano Banana 2): reported ~20 images/day at up to 1K resolution; Nano Banana Pro ~2/day; Gemini API free tier reportedly has zero or sharply cut image quota (sources conflict; a Dec 2025 quota cut is reported) — search snippet only, third-party blogs: [laozhang.ai limits](https://blog.laozhang.ai/en/posts/gemini-image-generation-free-limit-2026); [Zenmux pricing](https://zenmux.ai/blog/how-much-does-the-nano-banana-api-cost-in-2026)

### Inferences
- Character/style consistency (technique, not a sourced fact from this research): the usual open-source levers are a fixed seed plus a locked style prompt, a trained LoRA on the creator's own character (the FLUX.2 README explicitly lists Base variants for "fine-tuning, LoRA training"), and multi-reference image editing (klein/FLUX.2 support single- and multi-reference editing per the README) to keep a character stable across keyframes. Verify with a small test set before committing.
- For a Vietnamese-language channel needing on-image text (thumbnails), diffusion models often mangle diacritics; plan to add text in an editor (Kdenlive/Resolve/Pillow/HTML) rather than generate it. This is an inference; I did not find a source testing Vietnamese text rendering.
- Hosted "free" image tiers should be treated as non-commercial until the vendor's terms are read; I did not verify them.

### Gaps
- Official terms for output commercial use in Gemini app / Bing / Leonardo / Ideogram / Canva free tiers: not retrieved.
- SDXL, HiDream, Hunyuan-Image and other open image-model licenses: not checked — UNVERIFIED.
- Weights license for Z-Image and SANA: HF model cards blocked.
- No 2026 independent image-quality benchmark was gathered.

---

## 3. Image-to-video and text-to-video

### Takeaway
Best open options with licenses I read: Wan2.2 (Apache-2.0, includes a 5B model for 24 GB cards, 720p@24fps) and HunyuanVideo-1.5 (custom community license, excludes EU/UK/South Korea). LTX-2.x is "free" only for entities with annual revenue under US$10M and its license text changed on 11 Aug 2026. Hosted free tiers (Veo, Kling, Hailuo) are watermarked and non-commercial per one May 2026 comparison; none are suited to a monetized channel. Open-weight clips are short; plan on stitching 5-10 s clips.

### Cited Findings
- Wan2.2 license: models "licensed under the Apache 2.0 License. We claim no rights over your generated contents" with use restrictions (no illegal/harmful content, misinformation etc.) — [Wan2.2 README](https://github.com/Wan-Video/Wan2.2/blob/main/README.md); [LICENSE.txt](https://github.com/Wan-Video/Wan2.2/blob/main/LICENSE.txt)
- Wan2.2 models: T2V-A14B and I2V-A14B (480P and 720P), TI2V-5B (T2V+I2V at 720P/24fps, "can also run on consumer-grade graphics cards like 4090"), S2V-14B (speech-to-video), Animate-14B (character animation/replacement). Single-GPU A14B commands say "at least 80GB VRAM"; the TI2V-5B command says "at least 24GB VRAM (e.g., RTX 4090)" — [Wan2.2 README](https://github.com/Wan-Video/Wan2.2/blob/main/README.md)
- Third-party blogs say ComfyUI offloading/quantization (FP8/GGUF) can bring Wan2.2 5B to roughly 8 GB and A14B to ~24 GB for 480p; figures vary between vendors — search snippet only: [ThunderCompute](https://www.thundercompute.com/blog/wan-2-2-comfyui-ai-video-model); [Hivenet](https://www.hivenet.com/post/wan-2-2-cloud-gpu-comfyui)
- HunyuanVideo-1.5: 8.3B-parameter DiT; 480p and 720p T2V/I2V; minimum 14 GB GPU memory with offloading; step-distilled 480p I2V runs "within 75 seconds" on one RTX 4090; Wan2GP app claims as low as 6 GB VRAM — [HunyuanVideo-1.5 README](https://github.com/Tencent-Hunyuan/HunyuanVideo-1.5/blob/main/README.md)
- HunyuanVideo-1.5 license: Tencent Hunyuan Community License; "does not apply in the European Union, United Kingdom and South Korea"; use of Outputs outside the Territory is "unlicensed"; a licence request is needed above 100 million MAU — [LICENSE](https://github.com/Tencent-Hunyuan/HunyuanVideo-1.5/blob/main/LICENSE). Note: a creator based in or publishing from the EU/UK/South Korea should not use it.
- LTX-2.x (Lightricks): generates synchronized audio and video; README says defaults 1024x1536 at 24 fps, UHD 4K option; LTX-2.5 weights on HF. License (LTX-2.x Community License, dated 11 Aug 2026; applies to all LTX-2.5 versions): free "for any purpose" subject to Attachment A restrictions, BUT entities with annual revenue of at least US$10,000,000 (including affiliates) need a paid Commercial Use Agreement; an individual hobby/non-revenue use is "Non-Commercial Purpose" for large entities. Previous LTX-2 license (5 Jan 2026) covered LTX-2.3 until 11 Aug 2026 — [LTX-2 README](https://github.com/Lightricks/LTX-2/blob/main/README.md); [LICENSE index](https://github.com/Lightricks/LTX-2/blob/main/LICENSE); [LICENSE-2_x](https://github.com/Lightricks/LTX-2/blob/main/LICENSE-2_x). Hardware requirement for LTX-2.5 and clip length limit not extracted — UNVERIFIED (older LTX-Video README: LTX-2 clips "up to 10 seconds"; older LTX-Video 0.9.x was Apache-2.0 / OpenRAIL-M with a 2B model on 8 GB — [LTX-Video README](https://github.com/Lightricks/LTX-Video/blob/main/README.md)).
- Hosted free tiers (May 2026 comparison): Veo 3.1 via Flow ~50 daily credits, 8 s, 720p, watermark, no commercial use; Kling 3.0 ~66 daily credits, 5 s, 720p, watermark, no commercial use; Hailuo 3-5 gens/day, 6 s, 720p, watermark, no commercial use; Seedance 2.0 listed as 100 daily credits, 4 s, 1080p, no watermark, commercial allowed (another guide lists only 5-10 credits — conflict); Runway Gen-4 one-time 125 credits. Search snippet only: [fast.io comparison](https://fast.io/resources/best-free-ai-video-generators-2026.md); [Atlas Cloud guide](https://atlascloud.ai/blog/guides/10-best-ai-video-generators-free-no-subscription-in-2026)

### Inferences
- With the creator's constraint (avoid paid services + monetize), Wan2.2 (TI2V-5B for 24 GB cards, GGUF/FP8 variants for less) is the lowest-license-risk video generator verified here; keep most of the video as motion graphics/stills with Ken Burns motion and use AI clips sparingly for b-roll, because open-weight clips are only a few seconds and quality caveats (morphing, text artifacts, physics errors) are well known (general knowledge, not sourced here).
- Without a GPU, none of the open models are practical locally; Colab/Kaggle free GPUs have their own terms I did not check.
- Seedance's "commercial use on free tier" claim should be treated as UNVERIFIED until read from the vendor's terms.

### Gaps
- Official clip-length/resolution/VRAM specs for LTX-2.5 and Wan 2.5/2.6 (if released) not confirmed.
- Whether newer Wan versions (2.5+) are open-weight: not found in the Wan2.2 repo; UNVERIFIED.
- Hosted-service terms read directly from vendors: none (all blocked).
- Independent 2026 video-quality benchmark: none obtained.

---

## 4. Motion graphics / programmatic video

### Takeaway
For data/explainer videos the strongest free stack is code-driven: HyperFrames (HTML, Apache-2.0), Manim (MIT), MoviePy (MIT), FFmpeg (LGPL-3.0 core). Remotion is free for individuals and for-profit companies with up to 3 employees, and for non-profits — so a solo YouTuber is eligible — but larger companies need a paid Company License.

### Cited Findings
- Remotion license (LICENSE.md, copyright 2026): free license for "an individual; a for-profit organization with up to 3 employees; a non-profit or not-for-profit organization; or evaluating"; "Individuals and small companies are allowed to use Remotion to create videos for free (even commercial)"; larger for-profits need a Company License (price at remotion.pro, not read); disallowed: copying/modifying Remotion to sell/relicense your own derivative; file notes the license "will slightly change" in Remotion 5.0 (PR #3750, not read) — [Remotion LICENSE.md](https://github.com/remotion-dev/remotion/blob/main/LICENSE.md); [README](https://github.com/remotion-dev/remotion/blob/main/README.md). Company License price: UNVERIFIED (remotion.pro blocked).
- HyperFrames (HeyGen): "open-source framework for turning HTML, CSS, media, and seekable animations into deterministic MP4 videos"; Apache-2.0 "with no per-render fees or commercial-use thresholds"; renders by seeking each frame in headless Chrome (Puppeteer) and encoding with FFmpeg; requires Node.js 22+ and FFmpeg; supports GSAP, CSS, Lottie, Three.js, Anime.js, WAAPI; ships 21 agent skills, a Claude Code plugin, Studio/CLI; local and AWS Lambda render paths; comparison table says Remotion is "Source-available Remotion License" with a "mature cloud renderer" — [HyperFrames README](https://github.com/heygen-com/hyperframes/blob/main/README.md); [LICENSE](https://github.com/heygen-com/hyperframes/blob/main/LICENSE). Release/version number not confirmed on the page (GitHub Releases section appeared empty; npm package `hyperframes`).
- Manim Community: MIT License (copyright 3Blue1Brown LLC, 2018) — [LICENSE](https://github.com/ManimCommunity/manim/blob/main/LICENSE). Best for math/science animation; (strengths are general knowledge, not sourced).
- MoviePy: MIT licence ("Zulko ... released under the MIT licence") — [README](https://github.com/Zulko/moviepy/blob/master/README.md); [LICENCE.txt](https://github.com/Zulko/moviepy/blob/master/LICENCE.txt)
- FFmpeg repo COPYING.LGPLv3: LGPL v3 (builds that enable GPL components/x264 can be GPL) — [COPYING.LGPLv3](https://github.com/FFmpeg/FFmpeg/blob/master/COPYING.LGPLv3)

### Inferences
- For a data/explainer channel: HyperFrames or Remotion for charts, kinetic captions and lower-thirds; Manim for equations; FFmpeg to concatenate and mix. HyperFrames is the license-simplest option for anyone who might later exceed 3 employees. Remotion's Lambda renderer is more mature per HeyGen's own (self-interested) comparison.
- HyperFrames has a media-use skill and caption workflows, so it can also host TTS/music assets via an agent; I did not verify bundled TTS integration.

### Gaps
- Remotion 5.0 license change details; Company License price; HyperFrames version/date.
- Independent review/benchmark of HyperFrames vs Remotion: none found (the comparison is by HyperFrames' maker).

---

## 5. Voiceover / TTS and voice cloning

### Takeaway
English: Kokoro-82M (Apache-licensed weights, tiny, runs on CPU) and Chatterbox (MIT) are the lowest-risk open options; Qwen3-TTS (Apache-2.0 repo) also. Vietnamese is the hard part: Kokoro, Qwen3-TTS and Chatterbox do NOT list Vietnamese; the Vietnamese-specific VieNeu-TTS claims Apache-2.0 (weights card unverified), while VietTTS has CC-BY-NC pretrained models (not for monetized use). Fish Audio S2 (supports Vietnamese) and F5-TTS pretrained weights are NOT usable commercially without separate arrangements. ElevenLabs free plan: no commercial rights.

### Cited Findings
- Kokoro-82M: "open-weight TTS model with 82 million parameters... Apache-licensed weights"; README language codes: American/British English, Spanish, French, Hindi, Italian, Japanese, Brazilian Portuguese, Mandarin — Vietnamese is NOT in the list; uses espeak-ng for some languages; no voice cloning in README. Repo license Apache-2.0 — [Kokoro README](https://github.com/hexgrad/kokoro/blob/main/README.md); [LICENSE](https://github.com/hexgrad/kokoro/blob/main/LICENSE). HF model-card license field not read (HF blocked).
- Piper: development moved to OHF-Voice/piper1-gpl; repo license GPL-3.0; "fast and local neural text-to-speech engine" with espeak-ng; Open Home Foundation is "looking for maintainers" (maintenance risk). Per-voice licenses vary and the voice list is on HF (blocked) — Vietnamese voices: UNVERIFIED — [piper1-gpl COPYING](https://github.com/OHF-Voice/piper1-gpl/blob/main/COPYING); [README](https://github.com/OHF-Voice/piper1-gpl/blob/main/README.md); [old repo pointer](https://github.com/rhasspy/piper)
- Chatterbox (Resemble AI): MIT License; Multilingual V3 is 0.5B, 23+ languages: ar, da, de, el, en, es, fi, fr, he, hi, it, ja, ko, ms, nl, no, pl, pt, ru, sv, sw, tr, zh — Vietnamese NOT listed; zero-shot cloning; every output carries Resemble's PerTh imperceptible watermark — [Chatterbox README](https://github.com/resemble-ai/chatterbox/blob/master/README.md); [LICENSE](https://github.com/resemble-ai/chatterbox/blob/master/LICENSE)
- Qwen3-TTS (Qwen): repository LICENSE is Apache-2.0; 10 languages (zh, en, ja, ko, de, fr, ru, pt, es, it) — no Vietnamese; 3-second voice clone; 0.6B and 1.7B models. Weights license on HF card not read — [Qwen3-TTS README](https://github.com/QwenLM/Qwen3-TTS/blob/main/README.md); [LICENSE](https://github.com/QwenLM/Qwen3-TTS/blob/main/LICENSE)
- F5-TTS: code MIT, but "pre-trained models are licensed under the CC-BY-NC license due to the training data Emilia" — not commercial — [F5-TTS README](https://github.com/SWivid/F5-TTS/blob/main/README.md)
- Fish Audio S2 Pro (4B, March 2026): code and weights under "Fish Audio Research License" (last updated 7 Mar 2026); research and non-commercial free; "Any use ... for a Commercial Purpose requires a separate written license agreement"; commercial purpose includes any use "in connection with a product or service for which You charge a fee or generate revenue, whether directly or indirectly"; supports 80+ languages including Vietnamese (vi listed under Global Coverage), 10-30 s voice cloning; claimed top results on benchmarks (vendor claims) — [Fish Speech README](https://github.com/fishaudio/fish-speech/blob/main/README.md); [LICENSE](https://github.com/fishaudio/fish-speech/blob/main/LICENSE). Verdict: not for monetized channels unless licensed.
- VieNeu-TTS (Vietnamese, Pham Nguyen Ngoc Bao): README states "License: Apache 2.0 (Free to use)"; v3 Turbo is the latest open version, 48 kHz, 25 preset voices across North/Central/South, instant voice cloning, bilingual Vietnamese/English, runs on CPU via ONNX (RTF ~0.5) and GPU (RTF ~0.02, RTX 3060, 115 ms first audio); a "v3 Nano" preview has "noticeably lower quality"; v1 is deprecated; depends on neucodec (v1/v2) and MOSS-Audio-Tokenizer-Nano (v3) — [VieNeu README](https://github.com/pnnbao97/VieNeu-TTS/blob/main/README.md); [LICENSE](https://github.com/pnnbao97/VieNeu-TTS/blob/main/LICENSE) (Apache-2.0 text). The HF weights card and the licenses of training data/audio codecs were NOT checked — mark weight license UNVERIFIED until the HF card (pnnbao-ump/VieNeu-TTS-v3-Turbo) is read. Cloning a real person's voice raises the YouTube synthetic-content label and consent issues.
- VietTTS (dangvansam/viet-tts): source code Apache-2.0, but "Pre-trained models and audio samples are licensed under the CC BY-NC License" — not for monetized use — [VietTTS README](https://github.com/dangvansam/viet-tts/blob/main/README.md)
- Meta MMS-TTS Vietnamese (mms-tts-vie): I believe it is CC-BY-NC 4.0 but did not verify — UNVERIFIED, treat as non-commercial. (Search result said the same from the assistant's own knowledge, not from a source.)
- CosyVoice (FunAudioLLM): repo LICENSE is Apache-2.0; languages/weights license not checked — [LICENSE](https://github.com/FunAudioLLM/CosyVoice/blob/main/LICENSE). UNVERIFIED for Vietnamese and weights.
- XTTS (Coqui TTS): repo LICENSE is MPL-2.0 for code (file read is the 16 KB MPL text), but the XTTS v2 weights are under Coqui Public Model License (non-commercial) and Coqui shut down — from my knowledge, not verified here; mark UNVERIFIED, not recommended — [coqui TTS LICENSE.txt](https://github.com/coqui-ai/TTS/blob/main/LICENSE.txt)
- ElevenLabs free plan: 10,000 credits/month (~10 minutes of TTS), no commercial rights and attribution required on public output; Starter ~US$5/month adds commercial license and instant voice cloning; credit-per-character ratio sources conflict — search snippet only (third-party): [BigVu pricing 2026](https://bigvu.tv/blog/elevenlabs-pricing-2026-plans-credits-commercial-rights-api-costs/); [Toolradar](https://toolradar.com/tools/elevenlabs/pricing). The vendor page https://elevenlabs.io/pricing was not readable here, so the exact free-plan restriction wording is UNVERIFIED.

### Inferences
- English narration: Kokoro-82M for speed/low hardware, Chatterbox or Qwen3-TTS for cloning/expressiveness; pick by listening tests. Check the HF card license field for each before first monetized upload.
- Vietnamese narration with a fully free, commercially clean path: VieNeu-TTS is the only candidate found whose README says Apache-2.0, but because training data of Vietnamese TTS is often scraped, the creator should read the HF card and the repo's data notes and keep screenshots of license pages. VietTTS, F5-TTS, MMS and Fish S2 should be excluded for monetized use. If nothing meets the bar, record own voice (a human voice is the most YouTube-policy-safe choice).
- Pronunciation of numbers, abbreviations and English trading/finance terms inside Vietnamese text is a common failure for TTS; plan a text-normalization pass (VieNeu bundles sea-g2p for normalization).

### Gaps
- HF license fields for every TTS weight (HF blocked).
- Vietnamese quality comparisons/MOS: no independent 2026 benchmark found.
- Piper Vietnamese voice availability/license; XTTS and MMS licenses; Kokoro-Vietnamese fan models' license (a search snippet named ContextBox AI but gave no license) — all UNVERIFIED.

---

## 6. Music and sound effects

### Takeaway
Safe free sources: YouTube Audio Library (monetizable in YPP; follow attribution for CC tracks), plus CC0/own-license libraries (verify per track). For AI music, avoid MusicGen weights (CC-BY-NC). ACE-Step is Apache-2.0 (repo) and Stable Audio 3.0 small/medium open weights are free commercially under US$1M revenue (per press, not primary). Suno/Udio free tiers are non-commercial.

### Cited Findings
- YouTube Audio Library: YPP members can monetize videos using Audio Library music and sound effects; copyright-safe Audio Library tracks won't be claimed through Content ID per the Help page; Creative Commons tracks require attribution text pasted in the description; "Attribution not required" filter exists; YouTube is not responsible for issues with other "royalty-free" libraries. Some third-party sources claim residual Content ID claims can occur (unconfirmed) — search snippet of YouTube Help plus third-party summaries: [YouTube Help 3376882](https://support.google.com/youtube/answer/3376882?hl=en) (page itself not fetched); [vidIQ](https://www.vidiq.com/blog/post/royalty-free-music-youtube-audio-library). One licensing guide says standard-license tracks are limited to YouTube, whereas CC-BY tracks may be used elsewhere with attribution (third-party, unverified): [licenseorg](https://licenseorg.com/guide/music-audio/youtube-audio-library)
- MusicGen / AudioCraft: "code ... released under the MIT license ... model weights ... released under the CC-BY-NC 4.0 license" — NOT for monetized channels — [AudioCraft README](https://github.com/facebookresearch/audiocraft/blob/main/README.md); [MusicGen model card](https://github.com/facebookresearch/audiocraft/blob/main/model_cards/MUSICGEN_MODEL_CARD.md)
- ACE-Step (music generation): repository license Apache-2.0; supports 19 languages for vocals (10 well-performing); VRAM reduced to 8 GB; speed claim 27x real-time on a high-end GPU. Weights license on HF not read; training data provenance not verified — [ACE-Step README](https://github.com/ace-step/ACE-Step/blob/main/README.md); [LICENSE](https://github.com/ace-step/ACE-Step/blob/main/LICENSE)
- Stable Audio 3.0 (May 2026): per press, Small SFX, Small and Medium are open-weight; Large is API-only; Community License lets orgs under US$1M revenue use commercially, outputs owned by user; Stability claims fully licensed training data (company claim). Official license text not read — search snippet only: [The Decoder](https://the-decoder.com/stability-ai-launches-stable-audio-3-0-with-up-to-six-minute-tracks-and-open-weights/); [Digital Music News](https://www.digitalmusicnews.com/2026/05/21/stability-ai-3-0-release/). The older Stable Audio Open's terms were reported inconsistently by third parties — [Stability membership page](https://stability.ai/membership)
- Suno: free tier non-commercial; paid subscribers get commercial rights to songs downloaded while subscribed (Suno terms update of 10 Aug 2026 per one source); Udio: sources conflict on whether any plan allows commercial use — treat as risky; Suno signed a deal with Warner (Nov 2025) but UMG/Sony litigation continues — search snippet only: [Dupple Suno vs Udio](https://dupple.com/learn/suno-vs-udio); [fast.io alternatives](https://fast.io/resources/suno-alternatives-2026/)
- Pexels: its license allows commercial use without attribution (video and photo); Pixabay: royalty-free, but recognizable trademarks restrict commercial use and Pixabay content cannot be used to train AI; music/SFX license terms of Pixabay/Pexels not confirmed; none clear likeness rights — search snippet only: [licenseorg stock traps](https://licenseorg.com/blog/free-stock-photos-licensing-traps); [Pixabay FAQ](https://pixabay.com/service/faq/)

### Inferences
- Lowest-risk monetized-music plan: YouTube Audio Library ("attribution not required" filter) + own-composed or CC0 tracks; keep a log of track name, source URL, license, and download date for every asset in case of a Content ID dispute.
- ACE-Step / Stable Audio small are plausible free generators but need weight-license verification and carry the generic AI-copyright ambiguity (AI output may not be copyrightable, so you cannot stop others from reusing it; not sourced here).
- FFmpeg-generated tones or Freesound CC0 clips are common SFX sources; I did not verify Freesound's current terms.

### Gaps
- Direct reading of YouTube Help text and any 2026 changes to the Audio Library.
- Licenses for Incompetech, Freesound, FMA, Mixkit, Bensound etc.: not checked.
- HF license fields for ACE-Step and Stable Audio 3.0 weights.

---

## 7. Captions, subtitles, transcription, translation

### Takeaway
Whisper and its fast runtimes (faster-whisper, whisper.cpp) are MIT-licensed and free; WhisperX is BSD-2-Clause. Vietnamese works but accuracy lags English; an indicative FLEURS figure is ~9% WER for large-v3/turbo.

### Cited Findings
- openai/whisper: MIT License — [LICENSE](https://github.com/openai/whisper/blob/main/LICENSE)
- faster-whisper (SYSTRAN): MIT — [LICENSE](https://github.com/SYSTRAN/faster-whisper/blob/master/LICENSE)
- whisper.cpp (ggml): MIT, copyright through 2026 — [LICENSE](https://github.com/ggml-org/whisper.cpp/blob/master/LICENSE)
- WhisperX (alignment/word timestamps/diarization): BSD 2-Clause — [LICENSE](https://github.com/m-bain/whisperX/blob/main/LICENSE). (Its diarization pyannote models have their own gated terms — not verified.)
- Vietnamese accuracy indication: Handy model comparison lists Vietnamese FLEURS WER ~8.74% (large-v3) and ~9.48% (large-v3-turbo), at Q8_0, runtime not faster-whisper; turbo is large-v3 with decoder cut from 32 to 4 layers (faster, small quality drop), may lose more on tonal/low-resource languages; a Vietnamese fine-tune "EraX-WoW-Turbo-V1.1-CT2" exists for faster-whisper (numbers not read) — search snippet only: [Handy VI ranking](https://models.handy.computer/languages/vi); [EraX model card](https://huggingface.co/erax-ai/EraX-WoW-Turbo-V1.1-CT2/blob/main/README.md)
- YouTube: automatic captions generation counts as productivity use exempt from AI labels (see section 1).
- HyperFrames ships an `/embedded-captions` skill for kinetic captions — [HyperFrames README](https://github.com/heygen-com/hyperframes/blob/main/README.md)

### Inferences
- Workflow: audio -> faster-whisper (large-v3-turbo or large-v3) -> SRT -> manual proofreading of names, numbers and diacritics -> translate with an LLM (free-tier or local) keeping timestamps fixed -> re-check line length/pacing -> upload SRT to YouTube and/or burn-in via FFmpeg/HyperFrames. Translating with timestamps locked and checking syllable/second pacing before TTS dubbing mirrors the user's existing SRT-based workflow.

### Gaps
- No fresh independent 2026 Vietnamese benchmark on faster-whisper specifically; recommend own test on a 5-minute sample.
- License of the EraX Vietnamese fine-tune and pyannote: not checked.

---

## 8. Editing, assembly, mixing, loudness

### Takeaway
FFmpeg (scripted), Kdenlive (GPL, fully free), and DaVinci Resolve Free (commercial use allowed per forum/EULA reports) cover editing without paid fees. CapCut free is the weakest for monetized work because of built-in-asset restrictions and its broad content license.

### Cited Findings
- Kdenlive: "free and open-source video editor" (KDE project; GPL — license text not read in this fetch) — [Kdenlive README](https://github.com/KDE/kdenlive/blob/master/README.md)
- DaVinci Resolve Free: exports up to 4K UHD/60 fps (Studio goes higher), no noise reduction/multi-GPU/some codecs; Studio one-time ~US$295-299; a Blackmagic staff member reportedly confirmed free and Studio can be used for commercial work; EULA limits installs to one device per user. One source says the scripting API is Studio-only (unverified) — search snippet only: [Storyblocks comparison](https://www.storyblocks.com/resources/tutorials/davinci-resolve-free-vs-studio); [CineD](https://www.cined.com/davinci-resolve-an-in-depth-comparison-between-the-free-and-studio-version/); [PostFlow](https://thepostflow.com/post-production/video-editing/resolve-studio-vs-free/)
- CapCut free: ~1080p export cap; watermark behavior varies by template/AI feature/platform; Terms grant CapCut a broad license to user content; built-in sounds/music are not granted for commercial use; Pro ~US$9.99-19.99/month (varies by source) — search snippet only: [VidPros](https://vidpros.com/capcut-pro-vs-free/); [autoae.online](https://autoae.online/blog/is-capcut-free-for-commercial-use); [fluxnote](https://fluxnote.io/guides/capcut-free-plan-limits-2026)
- Loudness: common target for web video is about -14 LUFS integrated, -1 dBTP true peak, LRA about 11; use FFmpeg `loudnorm` two-pass (first pass `print_format=json` to measure, second pass `linear=true` with measured values); re-encode audio (e.g., AAC 192 kbps/48 kHz). These are community-standard targets; YouTube's own published number was not retrieved — search snippet only: [FileFlows/Instagit guides](https://instagit.com/browser-use/video-use/social-media-loudness-normalization-targets/); [Ahosting](https://www.ahosting.net/faq/ffmpeg-hosting/how-to-normalize-audio-loudness-with-ffmpeg.html)
- FFmpeg: LGPL-3.0 core (see section 4).

### Inferences
- For a repeatable AI pipeline, FFmpeg/HyperFrames scripts (no GUI) beat GUI editors; use Kdenlive or Resolve Free for manual polish. Because Resolve Free lacks Studio-only features, avoid planning around them.

### Gaps
- Official Kdenlive license text, Resolve EULA, CapCut Terms were not read directly.
- YouTube's current normalization behavior (official) not retrieved.

---

## 9. Orchestration and automation

### Takeaway
n8n is source-available (Sustainable Use License), free to self-host for your own internal business use but not for reselling; scripts + CLI tools + agent skills (HyperFrames' Claude Code plugin) are the simplest free orchestration. MCP-based agents are possible but I gathered no vetted MCP server list.

### Cited Findings
- n8n license: "Sustainable Use License" — you may use or modify it "only for your own internal business purposes or for non-commercial or personal use"; distribution only free of charge for non-commercial purposes; `.ee.` files need an Enterprise License — [n8n LICENSE.md](https://github.com/n8n-io/n8n/blob/master/LICENSE.md). Self-hosted community edition cost/limits not verified here.
- HyperFrames supports agent-driven production (Claude Code, Codex, Cursor, Gemini CLI skills; non-interactive CLI; `npx hyperframes skills update`) with a "plan, write HTML, lint, preview, render" loop — [HyperFrames README](https://github.com/heygen-com/hyperframes/blob/main/README.md)
- VieNeu-TTS exposes an OpenAI-compatible `/v1/audio/speech` server (Docker profiles), so it can be plugged into n8n/agents as a drop-in TTS endpoint — [VieNeu README](https://github.com/pnnbao97/VieNeu-TTS/blob/main/README.md)
- ComfyUI can be driven headlessly as a node-graph backend (general knowledge; not sourced here).

### Inferences
- A free orchestration spine: a Python/Node script (or n8n self-hosted for personal use) calling local servers: LLM -> TTS server -> image model (ComfyUI/stable-diffusion.cpp) -> faster-whisper -> HyperFrames/FFmpeg render -> loudnorm. Keep human review gates (script facts, synthetic-content label decision, license log) because YouTube monetization risk is about low-effort mass production.

### Gaps
- MCP servers for FFmpeg/ComfyUI/TTS: no verified list; ffmpeg MCP not found in this pass.
- n8n community-edition feature limits and Docker resource needs not checked.

---

## 10. Summary table: stage | free/open-source option | paid alternative | commercial-use license note | key limitation | source URL

| Stage | Free / open-source option | Paid alternative (optional) | Commercial-use license note | Key limitation | Source URL |
|---|---|---|---|---|---|
| Script and research | Free-tier chat LLMs / local open-weight LLM; NotebookLM-style grounded drafting; manual source check | Paid LLM plans | Free-tier commercial terms UNVERIFIED; YouTube treats script generation as an exempt "productivity" use | Fabricated/wrong citations are common; verify every claim | https://www.psypost.org/study-finds-nearly-two-thirds-of-ai-generated-citations-are-fabricated-or-contain-errors/embed/ (snippet); https://sites.lsa.umich.edu/learningteachingconsulting/2026/03/12/a-critical-look-at-notebooklm/ |
| Images | FLUX.2 [klein] 4B (Apache-2.0), Qwen-Image (Apache-2.0), Z-Image (repo Apache-2.0), ComfyUI, stable-diffusion.cpp (MIT) | Midjourney, hosted Nano Banana Pro, etc. | AVOID FLUX.1 dev / FLUX.2 dev / klein 9B (non-commercial); SD 3.5 free only under US$1M revenue | Needs a GPU (klein 4B ~8 GB); diacritic text in images unreliable (inference) | https://github.com/black-forest-labs/flux2/blob/main/README.md ; https://github.com/QwenLM/Qwen-Image/blob/main/README.md |
| Image/text-to-video | Wan2.2 (Apache-2.0; TI2V-5B on 24 GB), HunyuanVideo-1.5 (custom; not EU/UK/KR), LTX-2.x (free under US$10M revenue) | Veo, Kling, Runway, Hailuo, Seedance paid | Wan2.2: Apache-2.0, no rights claimed on outputs; free hosted tiers watermarked / non-commercial (snippet) | Short clips (about 5-10 s); A14B needs 80 GB or heavy quantization | https://github.com/Wan-Video/Wan2.2/blob/main/README.md ; https://github.com/Tencent-Hunyuan/HunyuanVideo-1.5/blob/main/LICENSE ; https://github.com/Lightricks/LTX-2/blob/main/LICENSE-2_x |
| Motion graphics / programmatic | HyperFrames (Apache-2.0), Manim (MIT), MoviePy (MIT), FFmpeg (LGPL-3.0), Remotion (free for individuals/up to 3 employees) | Remotion Company License; Canva/After Effects | Remotion: individual/<=3-employee for-profit/non-profit free; larger companies pay; HyperFrames has no thresholds | Remotion 5.0 license may change; HyperFrames version unconfirmed | https://github.com/remotion-dev/remotion/blob/main/LICENSE.md ; https://github.com/heygen-com/hyperframes/blob/main/README.md |
| TTS English | Kokoro-82M (Apache), Chatterbox (MIT), Qwen3-TTS (Apache repo) | ElevenLabs Starter (about US$5/mo), others | Free ElevenLabs plan: no commercial rights + attribution (snippet only) | HF weight cards unread; Chatterbox adds watermark | https://github.com/hexgrad/kokoro/blob/main/README.md ; https://github.com/resemble-ai/chatterbox/blob/master/LICENSE ; https://bigvu.tv/blog/elevenlabs-pricing-2026-plans-credits-commercial-rights-api-costs/ |
| TTS Vietnamese | VieNeu-TTS v3 Turbo (README: Apache-2.0; weights card UNVERIFIED) | ElevenLabs, Fish.audio hosted | EXCLUDE VietTTS weights (CC BY-NC), F5-TTS weights (CC-BY-NC), Fish S2 (research license) | Kokoro/Qwen3/Chatterbox lack Vietnamese; no independent quality benchmark | https://github.com/pnnbao97/VieNeu-TTS/blob/main/README.md ; https://github.com/dangvansam/viet-tts/blob/main/README.md ; https://github.com/fishaudio/fish-speech/blob/main/LICENSE |
| Voice cloning | Chatterbox, Qwen3-TTS (3 s), VieNeu (vi) | ElevenLabs IVC | Cloning a real person -> consent + YouTube synthetic-content label | Quality varies; Vietnamese cloning only via VieNeu | https://github.com/QwenLM/Qwen3-TTS/blob/main/README.md ; https://www.engadget.com/youtube-lays-out-new-rules-for-realistic-ai-generated-videos-154248008.html |
| Music / SFX | YouTube Audio Library; ACE-Step (repo Apache-2.0); Stable Audio 3.0 small/medium (under US$1M revenue, per press) | Suno paid, Udio, Epidemic Sound, Artlist | AVOID MusicGen weights (CC-BY-NC 4.0); Suno/Udio free = non-commercial | AI music weights license on HF unverified; CC tracks need attribution | https://github.com/facebookresearch/audiocraft/blob/main/README.md ; https://github.com/ace-step/ACE-Step/blob/main/LICENSE ; https://support.google.com/youtube/answer/3376882 (snippet) |
| Captions / transcription | faster-whisper, whisper.cpp, openai/whisper (all MIT), WhisperX (BSD-2) | Descript, Rev, ElevenLabs Scribe | MIT/BSD: free commercial use of code and outputs | Vietnamese WER about 9% on FLEURS; needs proofreading | https://github.com/SYSTRAN/faster-whisper/blob/master/LICENSE ; https://models.handy.computer/languages/vi (snippet) |
| Editing / assembly | FFmpeg, Kdenlive, DaVinci Resolve Free | Resolve Studio (about US$295), CapCut Pro, Premiere | Resolve Free commercial use reported OK; CapCut free built-in music not cleared | Resolve Free: no noise reduction, 4K/60 cap; CapCut watermark/terms | https://github.com/KDE/kdenlive/blob/master/README.md ; https://www.storyblocks.com/resources/tutorials/davinci-resolve-free-vs-studio (snippet) |
| Loudness | FFmpeg `loudnorm` two-pass to about -14 LUFS / -1 dBTP | iZotope, Auphonic | Open tool, no restriction | -14 LUFS is a community target, not verified from YouTube | https://www.ahosting.net/faq/ffmpeg-hosting/how-to-normalize-audio-loudness-with-ffmpeg.html (snippet) |
| Orchestration | Scripts + ComfyUI + HyperFrames skills; n8n self-hosted | n8n Cloud, Zapier, Make | n8n Sustainable Use License: internal business/personal use only, no resale | No verified MCP server list | https://github.com/n8n-io/n8n/blob/master/LICENSE.md |
| Platform policy | Human-authored angle, labels where required | n/a | YPP "inauthentic content" targets mass-produced/repetitive AI videos; label realistic synthetic content | Policy wording read only via secondary summaries | https://www.eweek.com/news/youtube-responds-to-ai-concerns/ |

---

## Overall unresolved items for the report writer
- All Hugging Face license fields (weights) were unreachable; every "weights license" statement above comes from GitHub repos or secondary sources and is labeled accordingly.
- Vendor pricing pages (ElevenLabs, CapCut, Blackmagic, Google, Suno, Stability) and YouTube Help were not read directly; only search-result summaries were seen.
- Commit/release dates are only partly known: LTX-2.x license dated 11 Aug 2026; Fish license updated 7 Mar 2026; FLUX.2 klein 15 Jan 2026; Stable Audio 3.0 about 21 May 2026 (press date in URL); Remotion LICENSE copyright 2026; HunyuanVideo-1.5 released 21 Nov 2025; Chatterbox Multilingual V3 date not found; Wan2.2 latest listed news Nov 2025 (no newer Wan version found in that repo).
