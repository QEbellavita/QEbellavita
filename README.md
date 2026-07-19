<div align="center">

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/header.svg?v=2" alt="QEbellavita — neural workflows, closed-loop prediction, cross-modal fusion" width="100%">

<br>

<img src="https://readme-typing-svg.demolab.com?font=Inter&weight=600&size=19&pause=1200&color=2563EB&center=true&vCenter=true&width=760&lines=Emotional+AI+on+real+biometric+signals;Cross-modal+fusion+%E2%80%94+cardiac%2C+camera%2C+context;Models+that+abstain+instead+of+guessing;Full-stack+architect+%E2%80%94+backend%2C+ML%2C+mobile" alt="What I work on">

</div>

<div align="center"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/divider.svg?v=2" alt="" width="100%"></div>

## What I'm building

**Quantara** — emotional intelligence infrastructure. Biometric signals in, a read on how
you actually feel out.

- Cross-modal fusion running live in production — **cardiac, camera-derived HR, ambient
  context and music signal**, blended against a per-user arousal baseline.
- A six-phase Neural Workflow engine — ingest → detect → predict → feedback → report →
  evolve — with the prediction layer wired to real outcome feedback rather than to its
  own guesses.
- Per-user baseline modulation, so the read is calibrated to *you* rather than to a
  population mean. Ships on iOS, watchOS and the web.
- Designed to **abstain under low confidence**. A confident wrong number is worse than no
  number, and on this kind of signal the wrong number is easy to produce.

**Scale.** ~450 API endpoints over 233 tables, 839 test suites, backed by a six-service
production deployment — Node API, sklearn model server, a 246-feature valence/arousal
service, speech emotion over wav2vec2, a medical inference surface, and Postgres. The iOS
client ships through TestFlight; the watchOS companion runs **CoreML inference on-device**,
with battery-aware model unloading and cloud fallback.

**The models report their own baselines.** Subject-independent, held out by subject:

| Task | Corpus | Result | Baseline |
|---|---|---|---|
| Stress | WESAD | 87.7% accuracy | 78.0% majority |
| Sleep staging (5-class) | Sleep-EDF | 0.738 macro-F1 | 40,145 held-out epochs |
| Cognitive workload | STEW | 0.794 macro-F1 | GroupKFold by subject |
| Activity | WISDM | 0.752 macro-F1 | Subject-independent |

That baseline column is the point. 87.7% sounds strong until you know the majority class is
78.0% — so the honest delta is what gets recorded, in the artifact, next to the metric.

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

And a written inventory of the platform's own inert code: ~15 fully-built capabilities
gated off, each with its effect-when-off and a safe-to-flip verdict. Knowing what *isn't*
switched on is a feature.

**belcrm** — a white-label CRM, customisable to any business. Ticketing, case management,
CSAT/CES, inventory and delivery ops — but the parts that aren't standard CRM:

- **SLA-breach risk is a trained model, not a rule.** A logistic regression fit in-process
  from each tenant's own resolved tickets, on six leakage-free creation-time features. It
  only serves if it clears **AUC ≥ 0.68 and beats the majority-class baseline** on a
  held-out split; otherwise it stays in shadow mode and the heuristic answers. Shadow
  predictions are logged and later scored for AUC, Brier and per-band calibration against
  real outcomes.
- **An autonomous ticket agent inside a risk-tiered sandbox** — every tool is *auto*,
  *needs-human-approval*, or *refuse-always*, and every action writes its audit row
  **before** it executes. It learns per tenant, retrieving that tenant's own past approved
  *and rejected* decisions as embedding-ranked few-shot examples.
- **Knowledge-base auto-linking** over Gemini embeddings with a keyword-overlap fallback,
  relevance floors tuned against a live production sweep rather than guessed — and
  deflection measured, not assumed.
- **Tenant isolation is proven in CI, not asserted in a doc.** An 811-line suite boots the
  real router under real auth and checks one tenant cannot reach another's rows, next to a
  boot smoke that starts the server against a deliberately stale schema. Underneath, a
  libSQL/Turso drop-in for the node-sqlite3 API runs identical code against edge-replicated
  remote, local file, and in-memory test databases.

**Signal research** — I work across EEG, GSR, audio and text affect on the standard corpora
(DEAP, WESAD, DREAMER, AMIGOS, FACED), and I publish the results that didn't work as
plainly as the ones that did.

Pre-registered spikes found that subject-independent EEG affect sits at the **chance
ceiling** once the splits are honest — including at N=123. Several promising-looking
results turned out to be leakage. That's a repo, not a footnote: knowing which signals
*don't* carry the information is what makes the ones that do worth trusting.

The camera work says something similar in a different register — rPPG can be trusted less
often than the field's headline numbers suggest, and considerably less often on darker
skin.

<div align="center"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/divider.svg?v=2" alt="" width="100%"></div>

## Public work

<div align="center">

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/pipeline.svg?v=2" alt="Pipeline diagram. Face ROI video feeds POS, CHROM and GREEN/ICA extraction; these feed an SNR and cross-method agreement stage, which feeds a confidence gate. The gate outputs either a heart rate or an abstention. Separately, 1000 Hz ECG feeds R-peak detection, which with POS output feeds scoring against ground truth." width="100%">

</div>

<div align="center">
  <a href="https://github.com/QEbellavita/eeg-affect-honest-negatives"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-eeg.svg?v=2" alt="eeg-affect-honest-negatives — pre-registered spikes finding EEG affect sits at the chance ceiling, including at N=123. Python, MIT, 3 datasets." width="47%"></a>
  <a href="https://github.com/QEbellavita/system-brain-mcp"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-brain.svg?v=2" alt="system-brain-mcp — read-only MCP tools for where code deploys, what is fabricated, whether the feedback loop closes. JavaScript, MIT, 8 tools and 51 tests." width="47%"></a>
  <a href="https://github.com/QEbellavita/claude-honest-engineering-skills"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-skills.svg?v=2" alt="claude-honest-engineering-skills — nine skills that make a coding agent check its work. Markdown, MIT." width="47%"></a>
  <a href="https://github.com/QEbellavita/rppg10-eval-harness"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-harness.svg?v=2" alt="rppg10-eval-harness — camera heart-rate extraction scored against synchronized ECG. Python, Apache-2.0, 14 test modules." width="47%"></a>
  <a href="https://github.com/QEbellavita/rppg-skin-tone-equity"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-equity.svg?v=2" alt="rppg-skin-tone-equity — Fitzpatrick-stratified error for cross-dataset deep rPPG. Python, MIT." width="47%"></a>
  <a href="https://github.com/QEbellavita/hf-papers-mcp"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-hfpapers.svg?v=2" alt="hf-papers-mcp — MCP server for Hugging Face Papers. Python, MIT, 6 tools and 11 tests." width="47%"></a>
  <a href="https://github.com/QEbellavita/obsidian-vault-mcp"><img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/main/assets/repo-card-obsidian.svg?v=2" alt="obsidian-vault-mcp — Obsidian MCP that survives iCloud eviction. JavaScript, MIT, 5 tools and 15 tests." width="47%"></a>
</div>

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

### Tools

**[obsidian-vault-mcp](https://github.com/QEbellavita/obsidian-vault-mcp)** — an MCP server
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

Most of my work is in private repos — Quantara, belcrm, and client systems. What's public
is the research I can share without redistributing gated corpora or anyone's data.

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

