HYROX Trainer — Chicago '27

A single self-contained web app that tracks my training for HYROX Chicago (Navy Pier, Feb 11 2027). It's a 16‑week plan plus a 5‑week transition bridge, built to carry my D‑10 strength base into a HYROX race engine.

Sibling project to my D‑10 Trainer — same patterns: one vanilla index.html, per‑device logging, week/phase navigation, built‑in timers, benchmark tracking.

What it is
One file, no build step. Plain HTML/CSS/JS in a single index.html. No framework, no bundler, no dependencies.
Offline‑friendly. All logs live in the browser's localStorage on that device (storage key hyrox_v1). Nothing is sent anywhere.
Installable. On iOS Safari: Share → Add to Home Screen to run it full‑screen like an app.
The plan at a glance

The program runs across five phases, shown as the progress "spine" in the header:

Phase	Length	Focus
Transition Bridge	~5 weeks	Re‑entry off D‑10 — rebuild easy running, relearn ergs/stations, set baseline tests
Phase 1 — Aerobic Base	4 weeks	Build the aerobic engine; station work as fresh capacity blocks
Phase 2 — Strength‑Endurance	4 weeks	Stations at race weight; compromised running introduced
Phase 3 — Race Specificity	5 weeks	Full race‑order compromised work, race‑pace runs, simulations
Phase 4 — Sharpen & Taper	3 weeks	Openers, primers, race day

Do the Bridge first — it's a separate on‑ramp before Week 1, not part of the numbered weeks.

How the programming works

Every session in the plan is fully specified — exact distances, station names, reps, rounds, rest, and weights — so there's nothing to interpret on the day.

Station weights are Open‑Men race standard and appear on every session: SkiErg 1000m · Sled push 50m @ 152kg · Sled pull 50m @ 103kg · Burpee broad jump 80m · Row 1000m · Farmers 200m @ 2×24kg · Sandbag lunge 100m @ 20kg · Wall balls 100 @ 6kg to the 10ft/3m target. (Sled figures include the sled itself.)
Progression is built in. Phase 1 trains stations fresh to build capacity; Phase 2 introduces compromised running with shorter station doses at race weight; Phase 3 runs full race‑order compromised sessions at race pace plus timed simulations (half → ~75% → dress rehearsal); Phase 4 sharpens and tapers.
Deload weeks auto‑lighten (W4, W8, W11) instead of prescribing a full grind.
Run paces stay relational — "@ race pace", "@ 5k pace", "@ threshold" — because they're set from the 5 km time trial in Bridge Week 5, which individualizes them to me. The "How to read the plan" panel explains the mapping and shows the race‑weight reference.
The tabs
Train — the week‑by‑week plan. Tap any day to open the full, explicitly‑programmed session, log your numbers, and see your last values as "ghost" placeholders. Check off days to fill the phase progress bar.
Tests — benchmark tracking (5 km TT, 1 km HYROX pace, 500 m Ski, 500 m Row, max wall balls, simulation total). Retest at the Bridge, Week 8, and Week 13 to watch the engine come.
Course — the 8 stations in race order with weights and race‑day rules of thumb.
Fuel — carb/protein targets periodized to the training day; syncs conceptually with my Food Buddy macros.
More — export/import your log, share the app, save to home screen, reset.
Timers

The red button (bottom‑right) opens three timers with audio cues:

Stopwatch with laps
Rest countdown (quick‑set 60/90/120s)
Interval (work/rest/rounds) for signature interval sessions
How I work on this

I don't edit code myself. When I ask for a change, the assistant makes the edit and returns a complete, ready‑to‑upload index.html plus click‑by‑click deploy steps.

Ground rules for any change:

Keep it one self‑contained index.html. Do not convert to React/Vite or split into multiple files.
Preserve the existing patterns (localStorage, ghost/last values, phase/week nav, timers, benchmarks).
Deploy (GitHub Pages)

This site is hosted on GitHub Pages using Deploy from a branch.

Put index.html at the root of the repo.
Add an empty .nojekyll file at the root (stops GitHub from processing the site with Jekyll).
In the repo: Settings → Pages → Build and deployment → Source: Deploy from a branch, pick your branch (e.g. main) and folder / (root), then Save.
Wait ~1 minute; the live URL appears at the top of the Pages settings.

To update: replace index.html with the new version, commit, and Pages redeploys automatically. Logged data is untouched — it lives in the browser, not the file. Hard‑refresh the live page after a deploy.

Repo layout
/
├── index.html     # the entire app
├── .nojekyll      # empty file — required for GitHub Pages
└── README.md      # this file
Data & privacy

All logs are stored only in the browser on the device you use. There's no account and no server. Use More → Export to copy your data as text before switching devices, and More → Import to restore it. More → Clear wipes everything on that device and can't be undone.

Possible future adds
Supabase cross‑device sync (like Food Buddy)
Editable pace presets
CSV export of the log
A "training day type" that ties into Food Buddy's macros

Personal training tracker. The program details live in my training doc; this app is the tracker.
