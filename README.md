<div align="center">

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/header.svg?v=2" alt="QEbellavita — neural workflows, closed-loop prediction, cross-modal fusion" width="100%">

<br>

<img src="https://readme-typing-svg.demolab.com?font=Inter&weight=600&size=19&pause=1200&color=2563EB&center=true&vCenter=true&width=760&lines=Emotional+AI+on+real+biometric+signals;Cross-modal+fusion+%E2%80%94+cardiac%2C+camera%2C+context;Models+that+abstain+instead+of+guessing;Full-stack+architect+%E2%80%94+backend%2C+ML%2C+mobile" alt="What I work on">

</div>

I build emotional-intelligence infrastructure on real biometric signal — cardiac, camera,
context — and I publish the results that didn't work as plainly as the ones that did. A
lot of what follows is the second kind: gates that refuse to promote, models that abstain,
and a pre-registered result that came back at the chance ceiling and stayed there.

<div align="center">

<a href="https://github.com/QEbellavita/QEbellavita/blob/main/assets/media/quantara-film.mp4"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/media/quantara-film-preview.gif" alt="Opening of the Quantara film — a sculpted heart on a teal wall as an EKG trace draws itself across and the wordmark resolves" width="62%"></a>

<sub><a href="https://github.com/QEbellavita/QEbellavita/blob/main/assets/media/quantara-film.mp4">▶ Quantara — heart, to EKG, to brain, to the app running it</a></sub>

</div>

<div align="center"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/divider.svg?v=2" alt="" width="100%"></div>

## Public work

<div align="center">
  <a href="https://github.com/QEbellavita/eeg-affect-honest-negatives"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-eeg.svg?v=2" alt="eeg-affect-honest-negatives — pre-registered spikes finding EEG affect sits at the chance ceiling, including at N=123. Python, MIT, 3 datasets." width="47%"></a>
  <a href="https://github.com/QEbellavita/system-brain-mcp"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-brain.svg?v=2" alt="system-brain-mcp — read-only MCP tools for where code deploys, what is fabricated, whether the feedback loop closes, what to do next. JavaScript, MIT, 11 tools and 72 tests." width="47%"></a>
  <a href="https://github.com/QEbellavita/claude-honest-engineering-skills"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-skills.svg?v=2" alt="claude-honest-engineering-skills — nine skills that make a coding agent check its work. Markdown, MIT." width="47%"></a>
  <a href="https://github.com/QEbellavita/rppg10-eval-harness"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-harness.svg?v=2" alt="rppg10-eval-harness — camera heart-rate extraction scored against synchronized ECG. Python, Apache-2.0, 14 test modules." width="47%"></a>
  <a href="https://github.com/QEbellavita/rppg-skin-tone-equity"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-equity.svg?v=2" alt="rppg-skin-tone-equity — Fitzpatrick-stratified error for cross-dataset deep rPPG. Python, MIT." width="47%"></a>
  <a href="https://github.com/QEbellavita/hf-papers-mcp"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-hfpapers.svg?v=2" alt="hf-papers-mcp — MCP server for Hugging Face Papers. Python, MIT, 6 tools and 11 tests." width="47%"></a>
  <a href="https://github.com/QEbellavita/obsidian-icloud-mcp"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-obsidian.svg?v=2" alt="obsidian-icloud-mcp — Obsidian MCP that survives iCloud eviction. JavaScript, MIT, 5 tools and 15 tests." width="47%"></a>
</div>

### Research

**[rppg10-eval-harness](https://github.com/QEbellavita/rppg10-eval-harness)** — camera-based
HR extraction over Dataset_rPPG-10, scored against synchronized 1000 Hz ECG. The README
leads with the number that isn't good: 11.44 bpm overall is not a usable reading.

<div align="center">

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/abstention-chart.svg?v=2" alt="Horizontal bar chart. Camera heart-rate error falls from 11.44 bpm across all three regions of interest, to 8.59 using the forehead only, to 5.87 once a confidence gate is applied — while coverage falls from 78 clips to 26 to 13." width="100%">

</div>

**[rppg-skin-tone-equity](https://github.com/QEbellavita/rppg-skin-tone-equity)** —
Fitzpatrick-stratified error for cross-dataset deep rPPG. Dark skin is worse on every
metric from every source model. Measured on a weak baseline at rest with n=12 — stated up
front, because the caveats are the finding as much as the numbers are.

<div align="center">

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/equity-chart.svg?v=2" alt="Grouped bar chart of camera heart-rate mean absolute error by source model and Fitzpatrick skin-tone group. PURE 17.29 light vs 21.68 dark; UBFC 10.63 vs 23.44; SCAMPS 24.65 vs 43.95. Darker skin is worse in every case." width="100%">

</div>

**[eeg-affect-honest-negatives](https://github.com/QEbellavita/eeg-affect-honest-negatives)** —
pre-registered spikes asking whether EEG predicts self-reported affect for a person the
model has never seen. It doesn't, and the ceiling holds at N=123. The reason published numbers
look better: they decode *which clip you watched*, which is a different task. The harness
reproduces that result first, to prove a null isn't just a broken pipeline.

<div align="center">

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/pipeline.svg?v=2" alt="Pipeline diagram. Face ROI video feeds POS, CHROM and GREEN/ICA extraction; these feed an SNR and cross-method agreement stage, which feeds a confidence gate. The gate outputs either a heart rate or an abstention. Separately, 1000 Hz ECG feeds R-peak detection, which with POS output feeds scoring against ground truth." width="100%">

</div>

### Tools

**[system-brain-mcp](https://github.com/QEbellavita/system-brain-mcp)** — eleven read-only
MCP tools that let a coding agent interrogate the system it's working in: where this code
*actually* deploys, what in it is fabricated, what's still open, whether the learning loop
closes — and what the evidence says to do next. `brain_recommend` is a deterministic rule
table over the brain's own evidence: degraded sources produce fewer recommendations, never
invented ones. The deploy tool cross-checks the declared target against every platform
config in the repo and reports the strays, because a leftover project on another platform
is the usual cause of "production keeps reverting".

**[obsidian-icloud-mcp](https://github.com/QEbellavita/obsidian-icloud-mcp)** — an MCP server
for Obsidian vaults that survives iCloud eviction. The naive version hangs forever on
dataless files; `stat`'s block count is the only reliable signal that a note is really
there.

**[hf-papers-mcp](https://github.com/QEbellavita/hf-papers-mcp)** — an MCP server for
Hugging Face Papers, so "what shipped on speculative decoding this week?" returns real
papers instead of training data.

**[claude-honest-engineering-skills](https://github.com/QEbellavita/claude-honest-engineering-skills)**
— nine skills that make a coding agent verify its work. Each one exists because something
went wrong; one of them is for catching an "implemented" engine that turns out to be
`Math.random()` behind a confident interface.

<div align="center"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/divider.svg?v=2" alt="" width="100%"></div>

## What I'm building

**Quantara** — emotional intelligence infrastructure. Biometric signals in, a read on how
you actually feel out. Cross-modal fusion running live in production across cardiac,
camera-derived HR, ambient context and music signal, blended against a per-user arousal
baseline rather than a population mean. A six-phase engine — ingest → detect → predict →
feedback → report → evolve — with the prediction layer wired to real outcome feedback
rather than to its own guesses. Designed to **abstain under low confidence**, because a
confident wrong number is worse than no number and on this signal the wrong number is easy
to produce. Ships on iOS, watchOS and the web.

**Scale.** ~450 REST endpoints over a 234-table schema, and 1,127 backend test suites
across ~8,300 cases. Six services in production on Railway, with Socket.io real-time across
21 namespaces. The watchOS companion runs CoreML inference on-device against compiled
`.mlmodelc` weights, falling back to cloud when the local model declines.

**The ML and AI layers.** ONNX inference in-process under a bounded-concurrency loader; a
weighted ensemble where roughly nine models actually vote, behind a staged shadow tier
carrying zero weight until promoted. 28-label text emotion from a quantized RoBERTa
GoEmotions model running in Node with a hand-written byte-level BPE tokenizer, because the
native `tokenizers` addon isn't available in the container. On top sits a Groq-backed LLM
gateway with per-provider circuit breakers and per-user token budgets — and every
user-facing message passes a **hard honesty gate** that extracts numeric tokens from the
model's output and rejects any figure not derivable from the underlying signal. A gate
failure falls back to a deterministic template; the same prompt is never shopped to a
second model hoping for a passing answer. Crisis detection sits below all of it and emits a
hardcoded message with real resources, deliberately not LLM-generated.

The platform also exposes itself as an **MCP server** — 72 tools across 18 domains,
fail-closed so it won't mount at all if the secret is missing. One of those tools is a
fabrication audit that scans the codebase for its own placeholder cores.

**Three things I built because the alternative was lying to a user:**

- **A promotion gate that refuses to promote.** Forecast engines cannot self-promote. The
  endpoint returns a fail-closed, decision-only verdict needing ≥300 *paired* targets and a
  ≥5% composite-MAE win — and no automatic flip mechanism exists. Promotion is deliberate
  manual work, by design.
- **A feedback loop fail-closed to an allowlist**, so a model can't train on its own
  output. An earlier weak-labeller prompted an LLM with the model's own prediction and
  recorded the echo as ground truth. That's pseudo-label poisoning; it was killed at source.
- **Process-level ONNX crash isolation.** A native runtime abort is uncatchable in JS, and
  worker threads don't help — a thread abort kills the process. So scoped inference runs in
  a forked sidecar where the abort becomes an ordinary rejection and the engine falls back
  to its heuristic, behind a sticky per-model circuit breaker.

Plus a written inventory of the platform's own inert code: ~15 fully-built capabilities
gated off, each with its effect-when-off and a safe-to-flip verdict. Knowing what *isn't*
switched on is a feature.

**belcrm** — a white-label CRM covering ticketing, case management, CSAT/CES and delivery
ops. The parts that aren't standard CRM: **SLA-breach risk is a trained model, not a rule**
— a logistic regression fit in-process from each tenant's own resolved tickets on six
leakage-free creation-time features, which only serves if it clears AUC ≥ 0.68 and beats
the majority-class baseline on a held-out split, and otherwise stays in shadow mode while
the heuristic answers. An **autonomous ticket agent inside a risk-tiered sandbox** where
every tool is *auto*, *needs-human-approval* or *refuse-always*, and every action writes its
audit row **before** it executes. And **tenant isolation proven in CI, not asserted in a
doc** — an 811-line suite boots the real router under real auth and checks one tenant
cannot reach another's rows.

Most of my work is in private repos — Quantara, belcrm, and client systems. What's public
is the research I can share without redistributing gated corpora or anyone's data.

<div align="center"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/divider.svg?v=2" alt="" width="100%"></div>

## Quantara — in motion

The visual identity the platform ships under — anatomically-grounded organs rendered in
claymation warmth, wired with EKG neon. Same premise as the engineering: the signal is a
real body, so the imagery is a real body.

<div align="center">

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/media/landing-hero-art.jpg" alt="Quantara landing hero art — an anatomical brain and heart joined by glowing neural filaments over an EKG trace, on a deep violet field" width="100%">

<br><br>

<a href="https://github.com/QEbellavita/QEbellavita/blob/main/assets/media/quantara-film.mp4"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/media/quantara-film-poster.jpg" alt="Closing frame of the Quantara film — a claymation brain wired into a radial mesh of threads and gears, with the app running the same brain on a phone beside it" width="78%"></a>

<sub>▶ &nbsp;<a href="https://github.com/QEbellavita/QEbellavita/blob/main/assets/media/quantara-film.mp4">play the full 25s</a></sub>

<br><br>

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/media/heart-neon.jpeg" alt="Quantara mark — neon anatomical heart on textured blue with an EKG trace running behind it" width="42%">

</div>

<div align="center"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/divider.svg?v=2" alt="" width="100%"></div>

## Stack

<div align="center">
  <p><strong>Languages &amp; ML</strong></p>
  <p><img src="https://skillicons.dev/icons?i=python,ts,js,swift,pytorch,tensorflow,sklearn&theme=dark" alt="Python, TypeScript, JavaScript, Swift, PyTorch, TensorFlow, scikit-learn"></p>

  <p><strong>Backend &amp; Data</strong></p>
  <p><img src="https://skillicons.dev/icons?i=nodejs,express,fastapi,postgres,sqlite,supabase&theme=dark" alt="Node.js, Express, FastAPI, PostgreSQL, SQLite, Supabase"></p>

  <p><strong>Mobile &amp; Frontend</strong></p>
  <p><img src="https://skillicons.dev/icons?i=react,expo,threejs,tailwind,vite&theme=dark" alt="React, React Native, Expo, Three.js, Tailwind, Vite"></p>

  <p><strong>Infra</strong></p>
  <p><img src="https://skillicons.dev/icons?i=railway,docker,githubactions,git&theme=dark" alt="Railway, Docker, GitHub Actions, Git"></p>
</div>

<div align="center"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/divider.svg?v=2" alt="" width="100%"></div>
