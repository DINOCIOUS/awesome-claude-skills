# Free non-AI music libraries and the free scriptable audio workflow for fitting background music to video (monetized YouTube)

Research date: 2026-10-10. READ-ACCESS NOTE: in this sandbox only github.com / raw.githubusercontent.com were reachable. WebFetch and curl failed with DNS/connection errors for pixabay.com, support.google.com, incompetech.com, mixkit.co, creativecommons.org, ffmpeg.org, freemusicarchive.org, etc. Therefore every license statement below is from a **SEARCH SNIPPET / search-engine summary (not a page read)** unless tagged **[READ]**. The only pages actually read in full were GitHub-hosted files (FFmpeg `doc/filters.texi`, `doc/ffmpeg.texi`, madmom/pydub/MTG/CLAP/Essentia READMEs). Re-verify each license on the live page before relying on it. Commands marked **[TESTED]** were run locally on ffmpeg 6.1.1 and librosa 1.0.0 with synthetic audio on 2026-10-10.

---

## 1. Free libraries whose licenses allow monetized YouTube use: terms, attribution text, Content ID risk

### Takeaway
Safest free, non-AI sources for a monetized channel: (1) YouTube Audio Library (only source with an official "won't be claimed via Content ID" statement), (2) CC0 / CC BY tracks you can prove, (3) Mixkit and Pixabay (no attribution, but no Content ID guarantee). Avoid anything CC BY-NC (not allowed on monetized videos) and treat Jamendo free downloads, Uppbeat free tier and Bensound free tier as attribution-bound with per-track or per-video obligations. No free library other than YouTube's own can fully rule out a later Content ID claim; your defense is a licensing log plus a dispute.

### Cited Findings

**A. YouTube Audio Library** (page status: SNIPPET from search results of official YouTube Help, 2026-10-10; fetch blocked)
- Official Help text (via snippet): copyright-safe Audio Library music/sound effects "won't be claimed by a rights holder through the Content ID system", and creators in the YouTube Partner Program can monetize videos using them — [YouTube Help: Use music and sound effects from the Audio Library](https://support.google.com/youtube/answer/3376882?hl=en) (snippet only; the search tool noted the cached copy may be an older version).
- Creative Commons tracks in the library still require credit: open the license icon in the License column, copy the attribution text, paste into the video description — same YouTube Help page (snippet). A "Music in this Video" section may also appear on the watch page (snippet).
- Filters named on Google's page per the search summary: title, genre, mood, artist, attribution, duration; instrument filter is described only by third-party guides (so UNVERIFIED on official page) — [YouTube Help](https://support.google.com/youtube/answer/3376882?hl=en-za); third-party: [Cal Poly guide](https://grandavehousing.calpoly.edu/news/free-music-your-guide-to), [Digital Citizen](https://www.digitalcitizen.life/how-to-download-free-music-from-youtube-library/). The "Attribution not required" filter wording comes from third-party guides, not the official page ([Fox iMusic summary via search](https://www.foximusic.com/blog/zh/?p=546)).
- Access path: YouTube Studio left menu → Audio Library, or youtube.com/audiolibrary; each track has a preview button and an MP3 download button (third-party guides; some say the UI is moving toward "Creator Music" with a link back to the free library — UNVERIFIED) — [Digital Citizen](https://www.digitalcitizen.life/how-to-download-free-music-from-youtube-library/).
- Limit of the guarantee: YouTube's guarantee covers tracks downloaded from the Audio Library; a vendor blog (Foxi, commercial interest) states YouTube is not responsible for claims on royalty-free music obtained elsewhere — [Foxi: Need background music that won't trigger Content ID](https://www.foximusic.com/blog/need-background-music-that-wont-trigger-content-id/) (snippet, biased source). A "no copyright" label on a re-upload of a track elsewhere (e.g. a YouTube "NoCopyrightSounds"-type channel or a third-party mirror) is NOT covered.
- Automation constraints: no official public API or bulk-download endpoint for the Audio Library found; downloads appear to be manual per-track in the Studio UI. UNVERIFIED (no source found either way). Scraping the logged-in Studio UI would likely violate YouTube ToS — not verified; do not recommend.
- Risk rating (my assessment): lowest Content ID risk of any free source.

**B. Pixabay Music** (page status: SNIPPET of pixabay.com/service/license/ ; terms page snippet)
- Official summary: content free to use without attribution (credit optional), may be modified/adapted, subject to Prohibited Uses; "only the full Content License is legally binding" — [Pixabay Content License Summary](https://pixabay.com/en/service/license/) (snippet).
- Terms: prohibited uses include selling/distributing content on its own unmodified, misleading/deceptive use, use with illegal/infringing content — [Pixabay Terms of Service](https://pixabay.com/en/service/terms/) (snippet).
- Content ID: I found no official Pixabay statement guaranteeing Content ID safety. A third-party competitor (Thematic) argues any Pixabay track can be registered with Content ID by its uploader after you download it — [Thematic vs Pixabay](https://hellothematic.com/thematic-vs-pixabay/) (competitor marketing, UNVERIFIED claim). A vendor blog says Pixabay itself acknowledges some composers' tracks are fingerprinted and users may need to dispute with a license certificate — [Foxi: Content ID Music guide](https://www.foximusic.com/blog/content-id-music-guide-monetization/) (secondary; not confirmed on a Pixabay page).
- License-change note: pre-9 Jan 2019 content is grandfathered as CC0, newer content is under the Pixabay Content License (a 2026 roundup; secondary) — [Foxi: Need background music…](https://www.foximusic.com/blog/?p=10). No official 2025–2026 change announcement found.
- Attribution text: not required; suggested courtesy credit e.g. "Music by <artist> from Pixabay" — my formatting, not an official string.
- Content ID risk: MEDIUM (no vetting; claims reported anecdotally).

**C. Incompetech (Kevin MacLeod)** (page status: SNIPPET from search; incompetech pages unreachable)
- Incompetech runs a dedicated "YouTube Content ID" page: MacLeod says that, because registered music can take months to unwind after a false claim, creators with many affected videos can bulk-release them through a form, or email help@incompetech.com; future uploads should carry the attribution from the FAQ — [incompetech: YouTube Content ID](https://incompetech.com/music/royalty-free/youtube-contentid.html) (snippet).
- License: Creative Commons Attribution (CC BY; current catalogue commonly cited as 4.0) — attribution REQUIRED; third-party sources say "free but absolutely requires attribution" — [Incompetech FAQ](https://incompetech.com/music/royalty-free/faq.html) (not read; the exact credit text was NOT retrieved). A French blog and many game credits show the usual pattern: `"Track Title" Kevin MacLeod (incompetech.com) Licensed under Creative Commons: By Attribution 4.0 License http://creativecommons.org/licenses/by/4.0/` — credits seen in [itch.io credit example](https://birdsfortwo.itch.io/paper-paladin-demo/devlog/866071/paper-paladin-demo-v012-demo-audio-attributions-document) (third-party; the site also generates copy-paste text on each track page, per a creator report — verify there).
- Content ID: a claim existing on your video means you cannot mark the video with the Creative Commons Attribution YouTube license (snippet, third-party). Because MacLeod's tracks are widely re-used and some have been auto-claimed historically, the Content ID page above exists for this reason. Risk: MEDIUM; mitigated by his release form.

**D. Free Music Archive (FMA)** (page status: SNIPPET of FMA FAQ/License Guide)
- License is per track; CC BY permits commercial use with credit; CC BY-NC bars commercial use — hence unusable on monetized videos; CC BY-ND permits commercial use but bars modification (edits/remixes) — [FMA FAQ](https://freemusicarchive.org/faq/), [FMA License Guide](https://freemusicarchive.org/License_Guide) (snippets); summary of monetized-YouTube implication from [Soundstripe on CC music](https://www.soundstripe.com/blogs/creative-commons-music) (vendor, secondary).
- Practical filter: only accept CC0, CC BY, CC BY-SA (check share-alike impact on your video; usually applies to the music adaptation, UNVERIFIED for video); reject NC and ND (trimming/mixing/fading is arguably an adaptation — treat ND as unsafe).
- Attribution text: use FMA's per-track "attribution" or write: `"Title" by Artist, from Free Music Archive (URL), licensed CC BY 4.0 (or the track's stated version).`
- Content ID risk: MEDIUM-HIGH (many independent artists also distribute via aggregators that register in Content ID — general, UNVERIFIED for FMA specifically).

**E. Freesound** (SNIPPET of forum posts)
- License is per sound: CC0 (no credit, commercial OK), CC BY (commercial OK with credit), CC BY-NC (not for monetized YouTube) — [Freesound forum: legal help](https://freesound.org/forum/legal-help-and-attribution-questions/38292), [second thread](https://freesound.org/forum/legal-help-and-attribution-questions/39864) (moderator/user posts, not the official license page). Better as a source of SFX/stings than of full music beds.
- Content ID risk: LOW for CC0 sound effects; MEDIUM for music uploads of unknown origin.

**F. ccMixter** — NOT VERIFIED. No result addressed ccMixter's current terms. Known (UNVERIFIED) pattern: per-track Creative Commons licenses, remix-oriented, many CC BY / CC BY-NC. Check each track's license badge; reject NC.

**G. Bensound free tier** (SNIPPET)
- Free license: a pop-up shows attribution text at download; text is valid for ONE video, re-download for each new video; if you forget it you can re-download, add text and dispute the claim; whitelisting is for paid licenses only — [Bensound: how to avoid copyright claims on YouTube](https://www.bensound.com/how-to-avoid-copyright-claims-on-youtube), [Bensound blog on whitelisting](https://blog.bensound.com/?p=1801) (snippets).
- Conflicting readings of free-license scope: a university guide quotes it as online video "published AND accessible free of charge", while LicenseOrg says commercial use is limited to monetized social platforms and excludes ads/paid promotion — [UConn guide](https://guides.lib.uconn.edu/hartfordmultimedia/software) vs [LicenseOrg Bensound vs Artlist](https://licenseorg.com/compare/bensound-vs-artlist). Resolve on bensound.com license page before using for a monetized channel.
- Content ID risk: MEDIUM (Bensound itself ties missing credit to claims).

**H. Uppbeat free tier** (SNIPPET of pricing/help)
- Pricing page: free plan = 3 downloads that refill by 1 per month (not 3/month); ~25–30% of catalogue (sources differ); all plans described as copyright-safe for monetization; free users must credit with Uppbeat's attribution link in the description to avoid claims; channel safelisting (real Content ID protection) is paid only — [Uppbeat pricing](https://uppbeat.io/pricing), [Uppbeat help center](https://fastly-f.uppbeat.io/help-center), [Uppbeat help: premium and business](https://fastly-f.uppbeat.io/help-center/premium-and-business). Third-party guide says free tier is for personal channels/small creators, not corporate/advertising use — [LicenseOrg Uppbeat](https://licenseorg.com/guide/music-audio/uppbeat) (UNVERIFIED).
- Content ID risk: LOW–MEDIUM only if the credit link is present in the description; no safelist on free.

**I. Mixkit** (SNIPPET)
- Mixkit's own page (per search summary): fine to use its music on YouTube; attribution appreciated but not required; one secondary page describes Free vs Restricted license tiers, with Restricted not allowed for monetized content — [Mixkit official information](https://mixkit.co/llm-info/), [Mixkit free stock music](https://mixkit.co/free-stock-music/), [Mixkit license](https://mixkit.co/license/) (NOT read). Advice to screenshot the license page at download time is from a roundup: [artyfile](https://www.artyfile.com/blog/10-best-sources-for-free-bg-music-for-youtube-videos).
- Content ID risk: MEDIUM (no safelist; Envato/Mixkit content ID stance not found).

**J. Jamendo** (SNIPPET + GitHub-read README)
- Jamendo's free downloads are for personal/non-commercial use; commercial use (ads, video content) goes through paid "Jamendo Licensing" sync licenses (single track, single project, perpetual) — [Jamendo Licensing](https://support-artist.jamendo.com/jamendo-licensing); third-party: [LicenseOrg Jamendo vs Artlist](https://licenseorg.com/compare/jamendo-vs-artlist). Individual tracks may carry CC licences that allow commercial use — check each track page.
- **[READ]** The MTG-Jamendo dataset README states Jamendo's music is made available only for non-commercial research, and defines commercial use as "any use… including… generating revenue through advertising" — [MTG-Jamendo README (License section)](https://github.com/MTG/mtg-jamendo-dataset/blob/master/README.md). This is a dataset notice, not Jamendo's consumer license, but it confirms Jamendo's strict stance on ad-revenue use.
- Verdict: for a monetized channel, Jamendo is NOT free; skip unless a track is explicitly CC BY/CC0 and you keep the page proof.

**K. Musopen / Internet Archive public-domain classical** (SNIPPET)
- Composition PD does not mean recording PD: a modern recording of an old piece can be claimed by the recording owner; Content ID matches audio and ignores legal status; false claims on PD classical recordings are documented (a 2009 case where a PD Wagner recording was claimed and the counternotice later re-muted) — [TunePocket: YouTube copyright claim on public domain music](https://www.tunepocket.com/youtube-copyright-claim-public-domain/), [Techdirt 2009](https://www.techdirt.com/2009/08/05/copyright-conundrum-was-apospublic-domainapos-music-silenced-on-youtube/). Musopen's and Archive.org's own current terms were not retrieved (UNVERIFIED).
- Rule: use only recordings explicitly tagged CC0 / Public Domain Mark for the *performance*, and keep the page capture. Content ID risk: MEDIUM-HIGH for classical because similar orchestral recordings match each other.

**L. Why "royalty-free" never equals "claim-free" and what disputes need**
- Content ID reads audio fingerprints, not license certificates, so licensed tracks can still be claimed; resolution is via dispute with proof (link to track + copy of license), whitelisting, or the rights holder releasing — [Musosoup](https://musosoup.com/blog/youtube-content-id), [Neosounds](https://www.neosounds.com/articles/how-to-solve-copyright-issues-on-youtube), [invideo help](https://help.invideo.io/en/articles/9780149-why-do-i-still-get-copyright-claims-for-music-tracks-used-from-within-the-invideo-library) (vendor sources, consistent with each other). Crediting an artist is not a license (same sources). Disputing without valid grounds can lead to escalation to a strike ([Foxi](https://www.foximusic.com/blog/content-id-music-guide-monetization/), secondary).

### Inferences
- For a Vietnamese solo creator avoiding paid tools, a defensible default order is: YouTube Audio Library "no attribution required" → CC0 (Freesound/FMA filter) → Mixkit/Pixabay with log → CC BY (Incompetech/FMA) with exact credit lines. Skip NC, ND and Jamendo free.
- Prefer tracks with a long public history (older uploads, many users) over brand-new Pixabay uploads, since retroactive registration is the only identified Pixabay-specific failure mode.
- Shorts and re-uploaded copies of the same video file on other platforms are not covered by the YouTube Audio Library guarantee unless the track was downloaded from the library (not verified for Shorts).

### Gaps
- Could not read any official license page (pixabay.com, incompetech FAQ, mixkit license, bensound license, jamendo, FMA, musopen) — all snippet-level.
- Exact current Audio Library UI labels (e.g. whether "Attribution not required" or "No attribution required"), and whether an instrument filter exists, unverified.
- No official statement on automating Audio Library downloads (API/bulk) found.
- Incompetech exact attribution string on the current FAQ not retrieved; ccMixter terms not found; Musopen/Archive.org terms not found; Freesound official license page not read.
- Bensound and Uppbeat free-tier monetization scope disagrees between sources.

---

## 2. Matching method: choosing tracks by mood/genre/tempo/duration; music brief from a script

### Takeaway
No peer-reviewed or primary sources were found for editor practice; the mapping below is a practitioner convention (flagged as inference). What is verifiable is the controlled vocabulary of mood/theme tags (MTG-Jamendo, 56 tags) which can be reused to write the brief and as labels for auto-tagging.

### Cited Findings
- The MTG-Jamendo mood/theme taxonomy (usable as a controlled vocabulary for briefs): action, adventure, advertising, ambiental, background, ballad, calm, children, christmas, commercial, cool, corporate, dark, deep, documentary, drama, dramatic, dream, emotional, energetic, epic, fast, film, fun, funny, game, groovy, happy, heavy, holiday, hopeful, horror, inspiring, love, meditative, melancholic, mellow, melodic, motivational, movie, nature, party, positive, powerful, relaxing, retro, romantic, sad, sexy, slow, soft, soundscape, space, sport, summer, trailer, travel, upbeat, uplifting — [moodtheme.txt in MTG-Jamendo repo](https://raw.githubusercontent.com/MTG/mtg-jamendo-dataset/master/data/tags/moodtheme.txt) **[READ]**; dataset has 87 genre, 40 instrument, 56 mood/theme tags — [README](https://github.com/MTG/mtg-jamendo-dataset/blob/master/README.md) **[READ]**.
- Library-side filters available: YouTube Audio Library (genre, mood, duration, attribution; instrument per third parties) — see section 1A.

### Inferences (practitioner convention, no citation; label as editorial heuristics in the report)
- Mood → genre/tempo/energy map for explainer/finance/education: "trustworthy, calm explanation" → ambient/light corporate/lo-fi/minimal piano, 70–100 BPM, low energy; "curiosity/discovery" → light electronic or pizzicato/pluck, 95–115 BPM; "tension/risk/crash" → dark ambient or cinematic pulse, 60–90 BPM or slow sub-bass drone, rising energy; "opportunity/win/CTA" → uplifting corporate/indie-acoustic, 100–125 BPM, brighter; "recap/outro" → return to opening motif, falling energy with long tail.
- Structure for narrated videos: avoid vocals (they compete with speech intelligibility); choose instrumentals with sparse midrange, no prominent lead melody in 1–4 kHz; use one bed per video or one bed per 2–3 minutes with a crossfade at a section boundary rather than many tracks.
- Level: music bed typically 15–25 dB under narration when voice is present (so about -30 to -22 LUFS short-term for music vs -16 to -14 LUFS overall mix); rise 6–10 dB in non-speech intro/outro. My tested ducking setup (section 3) yields about 11–15 dB reduction.
- Music brief template (turn a script into a search): for each script section record `section, start-end (s), purpose, mood tags (from the 56-tag list), energy 1–5, BPM range, instruments to avoid (vocals, strong lead), cue points (hook at 0, topic change, CTA)`; then a library query becomes `mood=<tag> AND duration >= section length AND no vocals`, and for a generation prompt `"instrumental, <mood>, <BPM> BPM, <instruments>, no vocals, steady, loopable"`. Pick duration ≥ video length + 10% so loops/trim are unnecessary; if shorter, choose tracks with a clean loop point (see section 3 beat alignment).

### Gaps
- No primary source for the BPM/energy mappings or dB-under-voice conventions; treat as editor heuristics that the report-writer should label as such.

---

## 3. Free scriptable tools: ffmpeg, Python, auto-tagging models

### Takeaway
Everything below is free and was either read in the official FFmpeg doc source on GitHub or run locally on 2026-10-10. A complete pipeline is: fit length → fade → duck under voice with `sidechaincompress` → `amix` → two-pass `loudnorm` → mux with `-c:v copy`.

### Cited Findings

**3.1 ffmpeg filter facts [READ in FFmpeg `doc/filters.texi`]** — [filters.texi](https://raw.githubusercontent.com/FFmpeg/FFmpeg/master/doc/filters.texi)
- `sidechaincompress`: first input is compressed according to the second; options `threshold` (default 0.125, 0.00097563–1), `ratio` (2, 1–20), `attack` (20 ms), `release` (250 ms, up to 9000), `makeup`, `knee`, `link`, `detection` (rms default), `level_sc`, `mix`. The doc's own example: `ffmpeg -i main.flac -i sidechain.flac -filter_complex "[1:a]asplit=2[sc][mix];[0:a][sc]sidechaincompress[compr];[compr][mix]amerge"` (note: doc uses `amerge`, which makes a multichannel stream; for a stereo mix use `amix`, shown below).
- `loudnorm`: EBU R128; options `I` (-70 to -5, default -24), `LRA` (default 7), `TP` (default -2), `measured_*`, `offset`, `linear` (default true, needs all four measured values; reverts to dynamic if target LRA < source LRA or true peak would exceed), `print_format`; dynamic mode upsamples to 192 kHz so set `-ar`/`aresample` explicitly.
- `ebur128`: logs M/S/I/LRA at 10 Hz; `peak=true` adds true peak; input converted to double float.
- `afade`: `type` in/out, `start_time`/`st`, `duration`/`d`, `curve` (tri default, qsin, hsin, esin, log, exp and others).
- `aloop`: `loop` (-1 infinite), `size` max samples, `start`. `atrim`: `start`, `end`, `duration`; does not rewrite timestamps (use `asetpts=PTS-STARTPTS`). `apad`: `whole_dur` pads silence to minimum duration. `amix`: `inputs`, `duration=longest|shortest|first`, `normalize` (default enabled; set 0 to avoid level changes), `weights`, `dropout_transition`.
- `-stream_loop N` (input option; -1 infinite) — [ffmpeg.texi](https://raw.githubusercontent.com/FFmpeg/FFmpeg/master/doc/ffmpeg.texi) **[READ]**.

**3.2 Tested command recipes [TESTED, ffmpeg 6.1.1, 2026-10-10]**

(a) Loop to exact video length with fade-in/out (45.000 s verified):
```bash
D=$(ffprobe -v error -show_entries format=duration -of csv=p=0 video.mp4)
ffmpeg -y -stream_loop -1 -i music.wav -t "$D" \
  -af "afade=t=in:st=0:d=2,afade=t=out:st=$(python3 -c "print($D-4)"):d=4:curve=qsin" music_fit.wav
```
Caveat: `-stream_loop` repeats hard; if the track does not end on a loop-friendly bar the seam will click. Use a beat-aligned cut (3.3) or `acrossfade` between two copies.

(b) Sidechain ducking under narration, then mix (measured: music stem RMS -44.1 dB without voice; with voice at -16 dB RMS and `threshold=0.03:ratio=8:attack=20:release=400` the music dropped to -58.9 dB, a 14.8 dB duck; with `threshold=0.05` -55.0 dB, 10.9 dB duck; returned to -44.1 dB within about 1 s after speech ended):
```bash
ffmpeg -y -i music_fit.wav -i voice.wav -filter_complex \
"[0:a]volume=-8dB[m];[1:a]asplit=2[key][vmix];\
[m][key]sidechaincompress=threshold=0.03:ratio=8:attack=20:release=400[d];\
[d][vmix]amix=inputs=2:duration=first:normalize=0[out]" -map "[out]" -ar 48000 mix.wav
```
Tuning lesson from testing: the threshold is a linear amplitude on the SIDECHAIN (voice). A quiet voice (peaks about -26 dBFS) with threshold 0.03 (about -30 dBFS) ducked only 1 dB. Normalize the voice (`loudnorm` or `dynaudnorm`) BEFORE using it as the key.

(c) Measure loudness / true peak (ebur128, tested):
```bash
ffmpeg -hide_banner -nostats -i mix.wav -af ebur128=peak=true -f null - 2>&1 | tail -12
```

(d) Two-pass loudnorm to -16 LUFS / -1.5 dBTP (result verified: I = -16.0 LUFS, true peak -2.6 dBFS, LRA 10.8):
```bash
ffmpeg -hide_banner -i mix.wav -af loudnorm=I=-16:TP=-1.5:LRA=11:print_format=json -f null - 2>&1 | sed -n '/^{/,/^}/p'   # pass 1
ffmpeg -y -i mix.wav -af "loudnorm=I=-16:TP=-1.5:LRA=11:measured_I=<input_i>:measured_TP=<input_tp>:measured_LRA=<input_lra>:measured_thresh=<input_thresh>:offset=<target_offset>:linear=true" -ar 48000 final.wav
```

(e) One-command mux to video, music loop + fade + duck + mix + loudnorm, video stream copied (tested, output h264 + aac, both 45.000 s):
```bash
ffmpeg -y -i video.mp4 -i music.wav -i voice.wav -filter_complex \
"[1:a]aloop=loop=-1:size=2e9,atrim=0:45,afade=t=in:d=2,afade=t=out:st=41:d=4,volume=-10dB[m];\
[2:a]asplit=2[k][v];[m][k]sidechaincompress=threshold=0.03:ratio=8:attack=20:release=400[d];\
[d][v]amix=inputs=2:duration=first:normalize=0,loudnorm=I=-14:TP=-1.5:LRA=11[a]" \
-map 0:v -map "[a]" -c:v copy -c:a aac -b:a 192k -ar 48000 -t 45 out.mp4
```
Note: single-pass loudnorm at the end is dynamic; prefer the two-pass of (d) for a file. Target value: -14 LUFS is the commonly cited YouTube reference but I did not read an official YouTube page for it (UNVERIFIED); -16 to -14 LUFS integrated with TP ≤ -1 dBTP is a safe range.

Volume automation without ducking (simple manual cue points):
```bash
-af "volume='if(between(t,10,25),0.25,0.8)':eval=frame"   # tested syntax class; `volume` supports eval=frame — doc: filters.texi section volume
```
(Expression syntax for `volume` documented in filters.texi `@section volume`; this exact line was not run.)

**3.3 Python: beat/tempo detection and cut alignment**
- librosa installed from PyPI (v1.0.0) and tested: on a synthetic 100 BPM click track `librosa.beat.beat_track` returned 99.4 BPM; snapping a target length to the nearest 4-beat bar returned 17.415 s for a 17 s target:
```python
import numpy as np, librosa
y, sr = librosa.load("track.mp3", sr=22050, mono=True)
tempo, beats = librosa.beat.beat_track(y=y, sr=sr, units="time")
bars = beats[::4]                      # assumes 4/4, first detected beat as downbeat
cut = bars[np.argmin(np.abs(bars - target_seconds))]
```
Cut then fade: `ffmpeg -i track.mp3 -t <cut> -af afade=t=out:st=<cut-3>:d=3 out.wav`. The "first beat = downbeat" assumption is UNVERIFIED for real music; confirm by ear or use madmom's downbeat tracker. Source: librosa repository [github.com/librosa/librosa](https://github.com/librosa/librosa) (README fetched; library code tested locally).
- madmom provides beat/downbeat trackers, but its **model/data files are CC BY-NC-SA 4.0** and commercial use "of any of these files… or technology which utilises them in a commercial product" requires contacting the authors; source code is BSD — [madmom README](https://raw.githubusercontent.com/CPJKU/madmom/main/README.rst) **[READ]**. Using it only to analyse your own library tracks offline is not distribution, but the report should flag the NC-SA model license (inference).
- pydub (wraps ffmpeg): `fade_in/fade_out`, `append(crossfade=ms)`, `*` to repeat, slicing by ms, `overlay`, `apply_gain` — [pydub README](https://raw.githubusercontent.com/jiaaro/pydub/master/README.markdown) **[READ]** (crossfade, `do_it_over = with_style * 2`, `.fade_in(2000).fade_out(3000)` examples present).

**3.4 Open-source mood/genre tagging for ranking tracks**
- MTG-Jamendo dataset: 55,000+ CC-licensed Jamendo tracks, 195 tags (genre/instrument/mood-theme); the dataset is NON-COMMERCIAL RESEARCH ONLY per its README, and its metadata is CC BY-NC-SA 4.0 — [README](https://github.com/MTG/mtg-jamendo-dataset/blob/master/README.md) **[READ]**. Fine to learn from, but do not rely on it for anything beyond private research; models trained on it may inherit restrictions (inference, UNVERIFIED).
- Essentia (AGPLv3 C++/Python library with `pip install essentia` / `essentia-tensorflow`) contains music descriptors and ships TensorFlow models for mood/genre — [Essentia README](https://raw.githubusercontent.com/MTG/essentia/master/README.md) **[READ]**. The essentia-models repo README is a one-line stub; the pretrained model files and their licenses are hosted at essentia.upf.edu (unreachable here, license UNVERIFIED — I recall CC BY-NC-SA for many models, but not confirmed).
- LAION-CLAP: `pip install laion-clap`; supports zero-shot audio classification with text prompts (e.g. "This audio is a <genre> song"); music checkpoints GTZAN zero-shot accuracy 51–71% depending on checkpoint — [CLAP README](https://raw.githubusercontent.com/LAION-AI/CLAP/main/README.md) **[READ]**. Useful for ranking by text prompts like "calm instrumental piano for finance explainer"; accuracy modest, so use only to shortlist.

**3.5 Licensing log fields** — see section 4.

### Inferences
- A cheap ranking pipeline: pre-filter by library mood/duration/no-attribution filters, compute BPM and mean RMS/spectral centroid with librosa (low centroid and low RMS variance suggest a bed that will not fight speech), optionally score 3–5 candidates with CLAP text prompts, then listen to the top 3 against the actual voiceover.
- Sidechain parameters are track-dependent; start with ratio 6–10, attack 10–30 ms, release 300–600 ms, threshold set so voice peaks exceed it by 10–20 dB, and verify duck depth by measuring RMS (command shown).

### Gaps
- ffmpeg.org docs page was not reachable (used the GitHub doc source, which is the page's source of truth).
- Did not test madmom, pydub or any tagging model locally; librosa was tested only on synthetic audio.
- YouTube's official loudness normalization reference value not read.
- The `volume=...eval=frame` ducking-by-timestamps line was not executed.

---

## 4. Licensing log: what to record per track to defend a Content ID claim

### Takeaway
Content ID cannot read licenses, so defense happens after a claim via dispute or release; success depends on proof tied to the exact asset and time of download. Keep one row per track per video.

### Cited Findings
- Dispute guidance from vendors: provide a link to the track used plus a copy of the license; keep a saved license artifact (contract, invoice, email grant, platform license receipt) tied to the exact asset; common failure reasons are license not covering YouTube monetization, lapsed subscription, and treating credit as a license — [Musosoup](https://musosoup.com/blog/youtube-content-id), [Neosounds](https://www.neosounds.com/articles/how-to-solve-copyright-issues-on-youtube), [Mixkit tip via artyfile](https://www.artyfile.com/blog/10-best-sources-for-free-bg-music-for-youtube-videos) (screenshot license page at download).
- Bensound's attribution text is per video, so log the exact text per video — [Bensound](https://www.bensound.com/how-to-avoid-copyright-claims-on-youtube) (snippet). Pixabay says a license certificate can help in disputes (via vendor blog, secondary) — [Foxi](https://www.foximusic.com/blog/content-id-music-guide-monetization/).

### Inferences
Recommended log columns (CSV/Sheet, one row per use):
`video_id/title, publish_date, track_title, artist, source_site, track_page_URL, direct_download_URL, license_name+version (e.g. CC BY 4.0, Pixabay Content License), license_URL, license_page_snapshot (PDF/screenshot/archive.org link), date_downloaded (UTC), account_used, original_file_name + SHA-256 hash, attribution_required (Y/N), exact_attribution_text_pasted_in_description, description_URL/timestamp, edits_made (trim/fade/loop), content_id_check (none / claim date / claim ID / outcome), dispute_notes`.
Also keep the original download, the license page capture, and a screenshot of the track page (showing uploader and license), and re-check the license page periodically since terms change (YouTube Help page itself changed over time per the search tool note).

### Gaps
- No primary source for what YouTube's dispute reviewers accept; evidence above is from vendor guidance.
- Not verified whether free libraries provide downloadable license certificates (Pixabay reportedly can; Mixkit, Freesound unverified).

---

## Sources actually READ vs SNIPPET summary
- READ in full (GitHub): FFmpeg `doc/filters.texi` and `doc/ffmpeg.texi`; madmom README.rst; pydub README; MTG-Jamendo README and `moodtheme.txt`; LAION-CLAP README; Essentia README; essentia-models README.
- SNIPPET only: every license/terms statement for YouTube, Pixabay, Incompetech, FMA, Freesound, Bensound, Uppbeat, Mixkit, Jamendo, Musopen/Archive.org, and all Content ID dispute guidance. Vendors (Foxi, Soundstripe, Thematic, Neosounds, Musosoup, LicenseOrg) have commercial interests and are used only as secondary corroboration.
