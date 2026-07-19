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

**rPPG research** — camera-based heart-rate extraction, and the question of when it can be
trusted. Two repos below. Short version: less often than the field's headline numbers
suggest, and considerably less often on darker skin.

<div align="center"><img src="./assets/divider.svg" alt="" width="100%"></div>

## Public work

<div align="center">
  <a href="https://github.com/QEbellavita/rppg10-extractor"><img src="https://github-readme-stats.vercel.app/api/pin/?username=QEbellavita&repo=rppg10-extractor&theme=react&bg_color=0D1117&title_color=2563EB&icon_color=0D9488&border_color=1F2937&hide_border=false" alt="rppg10-extractor"></a>
  <a href="https://github.com/QEbellavita/rppg-skin-tone-equity"><img src="https://github-readme-stats.vercel.app/api/pin/?username=QEbellavita&repo=rppg-skin-tone-equity&theme=react&bg_color=0D1117&title_color=2563EB&icon_color=0D9488&border_color=1F2937&hide_border=false" alt="rppg-skin-tone-equity"></a>
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

<div align="center">

<img src="https://raw.githubusercontent.com/QEbellavita/QEbellavita/output/snake.svg" alt="Contribution graph" width="100%">

</div>

<!--
  TODO before this reads as finished:
  - Add real contact/site badges here once you decide what to publish. The previous
    draft linked quantara.app / a mailto on the GitHub noreply address; neither was
    a real destination, so both were removed rather than left as dead links.
  - The snake image above is generated by .github/workflows/snake.yml into the
    `output` branch. It renders as broken until that workflow runs once.
-->
