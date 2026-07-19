<div align="center">

<img src="./assets/header.svg" alt="QEbellavita — neural workflows, closed-loop prediction, cross-modal fusion" width="100%">

<br>

<img src="https://readme-typing-svg.demolab.com?font=Inter&weight=600&size=19&pause=1200&color=2563EB&center=true&vCenter=true&width=760&lines=Emotional+AI+on+real+biometric+signals;Cross-modal+fusion+%E2%80%94+cardiac%2C+camera%2C+context;Models+that+abstain+instead+of+guessing;Full-stack+architect+%E2%80%94+backend%2C+ML%2C+mobile" alt="What I work on">

</div>

<div align="center"><img src="./assets/divider.svg" alt="" width="100%"></div>

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

**belcrm** — an enterprise CRM for magazine distribution: ticketing, case management,
routing, SLA tracking, and an AI layer over customer service and distribution operations.
Node/Express + SQLite, deployed on Railway.

**Signal research** — beyond what ships, I work across EEG, GSR, audio and text affect on
the standard corpora (DEAP, WESAD, DREAMER, AMIGOS). That work includes negative results
I've kept rather than buried: subject-independent EEG affect sits at the chance ceiling
once the splits are honest, and several published-looking spikes turned out to be leakage.
Knowing which signals *don't* carry the information is what makes the ones that do worth
trusting.

The camera work is the part I can publish. Two repos below, and the short version is that
rPPG can be trusted less often than the field's headline numbers suggest — and
considerably less often on darker skin.

<div align="center"><img src="./assets/divider.svg" alt="" width="100%"></div>

## Public work

<div align="center">
  <a href="https://github.com/QEbellavita/rppg10-extractor"><img src="./assets/repo-card-extractor.svg" alt="rppg10-extractor — camera heart-rate extraction scored against synchronized 1000 Hz ECG ground truth. Python, MIT, 70 tests." width="46%"></a>
  <a href="https://github.com/QEbellavita/rppg-skin-tone-equity"><img src="./assets/repo-card-equity.svg" alt="rppg-skin-tone-equity — Fitzpatrick-stratified error for cross-dataset deep rPPG, caveats stated up front. Python, MIT, research." width="46%"></a>
</div>

**[rppg10-extractor](https://github.com/QEbellavita/rppg10-extractor)** — camera-based HR
extraction over Dataset_rPPG-10, scored against synchronized 1000 Hz ECG. The validation
doc opens by correcting an earlier claim the project itself got wrong.

<div align="center">

<img src="./assets/abstention-chart.svg" alt="Horizontal bar chart. Camera heart-rate error falls from 11.44 bpm across all three regions of interest, to 8.59 using the forehead only, to 5.87 once a confidence gate is applied — while coverage falls from 78 clips to 26 to 13." width="100%">

</div>

**[rppg-skin-tone-equity](https://github.com/QEbellavita/rppg-skin-tone-equity)** —
Fitzpatrick-stratified error for cross-dataset deep rPPG. Dark skin is worse on every
metric from every source model. Measured on a weak baseline at rest with n=12 — stated up
front, because the caveats are the finding as much as the numbers are.

<div align="center">

<img src="./assets/equity-chart.svg" alt="Grouped bar chart of camera heart-rate mean absolute error by source model and Fitzpatrick skin-tone group. PURE 17.29 light vs 21.68 dark; UBFC 10.63 vs 23.44; SCAMPS 24.65 vs 43.95. Darker skin is worse in every case." width="100%">

</div>

Most of my work is in private repos — Quantara, belcrm, and client systems. What's public
is the research I can share without redistributing gated corpora or anyone's data.

<div align="center"><img src="./assets/divider.svg" alt="" width="100%"></div>

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

<div align="center"><img src="./assets/divider.svg" alt="" width="100%"></div>

<!--
  Contribution snake removed from display for now. .github/workflows/snake.yml
  is still present but fails with "Resource limits for this query exceeded" —
  the default GITHUB_TOKEN cannot pull contribution data. Fixing it means
  minting a PAT with read:user and storing it as a repo secret. Re-add this
  once that is decided:
  <img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/output/snake.svg" alt="Contribution graph" width="100%">
-->

<!--
  Contact badges go here — waiting on a real address/URL. Do not re-add
  quantara.app (parked page, not ours) or a mailto on the GitHub noreply
  address (cannot receive mail).

  The snake image above is generated by .github/workflows/snake.yml into the
  `output` branch, and renders broken until that workflow has run once.
-->
