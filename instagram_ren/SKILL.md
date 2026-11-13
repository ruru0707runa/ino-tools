# Instagram Operations for @ren_ai_nerve

Installed 2026-11-08 with ino's approval ("入れる（検査と試運転まで）"). Merged from the Japanese Instagram agent skill set (Alman-creator-uslog/instagram-agent-skill-ja, MIT, upstream copies in `upstream/`), rewritten under Ren rules. The full upstream procedures live in `upstream/ig-*.md`; read the matching one before using that workflow. Tools live in `tools/` and were inspected on install: imports are Python standard library only (argparse, json, os, re, statistics, sys, unicodedata, plus the local `jp.py`), with no network, subprocess, eval or exec calls. Two tools write a file only when an output path is passed (`humanize.py --out`, `swipe.py --out`).

## Ren rules — these override the upstream skill wherever they conflict

- Apply the health-expression filter first: the AI.md brief's NG→OK table outranks every upstream hook formula. Never use 消える・治る・若返る・痩せる as an effect claim, never state a mechanism or effect as fact, hedge with 〜と言われています / 軽く感じる人も, and close with the medical-care line where the brief requires it. Drop a hook that needs a banned claim, however high it scores.

- Use Riri's voice, not ino's: `voice.md` in this folder replaces the upstream `templates/voice.md`. The speaker is the childlike apprentice teacher Riri in an oversized white coat, with a light-brown pinkish nose; Roro keeps his cream markings on cheek, brow, mouth, chest and legs.

- Hold the reel format: about 20 seconds, real moving clips only, no stills carousel and no carousel video, telop mandatory inside the safe zone (720×1280, y≈170–1030, clear of the right icon column), a single movement focus, and a cute single voice with audio.

- Never post or reserve from this skill: drafts and scores only. Publishing follows the standing approval flow, with an explicit "投稿して" from ino for each post. Read `~/workspace/custom-skills/publish_authorization_gate/SKILL.md` alongside this skill whenever a draft approaches publication.

- Treat every number from the upstream repo, a course, or a benchmark account as a claim until it is checked against Ren's own app insights. The Instagram connector cannot fetch per-reel view counts, so the 1,500-view gate is judged from the app, not from connector output.

- Judge reels by the 1,500-view gate first, then the 48-hour rule. Do not rework locked reels (the 9-test A/B/C reels) with this skill without ino's approval.

## Reel workflow (upstream /ig-reel)

- Start from one topic and draft three hooks from the 26 formulas in `tools/hooks.json`, then score all three before writing the full script: `python3 tools/hookscore.py <hooks.txt>` with one hook per line.

- Use the score only as a filter that drops clearly weak hooks before production. The upstream validation separates bad hooks well (AUC 0.91) but cannot separate hits from misses inside one genre (AUC 0.47), so never present a high score as a promise the reel will spread.

- Build the timing table before production: `python3 tools/beats.py <script.txt> --target 20`, one spoken line per line of the file. Flag a hook line over 3 seconds, any single cut that runs long, filler lines with no concrete content, and a missing loop back to the first line.

- Measure Riri's TTS reading speed from finished reels and reuse it with `--cps` instead of trusting the 9-kana-per-second default. The C1 smoke test (2026-11-08) measured C1's five line recordings at 13.1 seconds of speech for about 69 kana sounds, about 5.3 kana per second, and at `--cps 5.3` the tool's per-line estimates (2.0 / 3.8 / 2.5 / 2.8 / 2.0 seconds) landed within about 0.9 seconds of the actual line recordings (1.44 / 3.29 / 2.95 / 2.93 / 2.52 seconds). Use the tool for speech length per line, not for total reel runtime: the rest of a Ren reel's 20 seconds is clip pacing and pauses between lines, which the tool does not model.

- Write the script, telop and caption from the winning hook, keeping the health filter above, and read `upstream/ig-reel.md` for the full procedure when a step is unclear.

## Viral research (upstream /ig-viral)

- Rank candidate reels by how far each beat its own account's median views, never by raw view count: collect the figures by hand at human pace, then run `python3 tools/swipe.py <captured.tsv> --out <swipe.md>`.

- Name the hook formula each winning reel used and keep the result as a swipe file the next script can draw from.

- Never scrape Instagram mechanically and never log in as anyone else; research is read-only viewing, in line with the upstream design and platform terms.

## Caption workflow (upstream /ig-caption)

- Write the caption so the part visible before "…続きを読む" — about 30 full-width characters, username included on the first line — already carries the problem or the curiosity gap.

- Check every finished caption before delivery: `python3 tools/caption.py <caption.txt> --keywords "<search words>"`. Keep hashtags at five or fewer, placed after the fold, with exactly one ask (comment keyword, save, or share).

- Run the AI-phrasing pass on captions and scripts before showing them to ino: `python3 tools/humanize.py <draft.txt> --report` and `python3 tools/detect.py <draft.txt>`, then rewrite the flagged sentence shapes by hand instead of accepting mechanical rewrites. The dictionary is `tools/slop.json` (117 Japanese set phrases).

## Profile and audit (upstream /ig-profile, /ig-audit)

- Score the profile with the 12-item, 100-point rubric in `tools/rubric.json` when ino asks for a profile review, and rewrite the lowest-scoring items first, in that order.

- Audit published reels by growth multiple and shares per reach, not by raw views, and let Ren's own audit data outrank any generic rule in this skill set, including this file.

## Out of scope unless ino instructs otherwise

- Use `/ig-carousel` for feed carousel posts only, never to build a carousel video.

- Do not use `/ig-story`, `/ig-comment`, `/ig-reply`, `/ig-dm`, `/ig-plan` or `/ig-repurpose` without a separate instruction from ino naming that workflow.

## Source and licence

- Upstream: https://github.com/Alman-creator-uslog/instagram-agent-skill-ja (Japanese rebuild of Jake Schincariol's instagram-agent-skill), MIT licence, licence text in `upstream/LICENSE`.

- The draft this install was built from is kept at `~/workspace/custom-skills/instagram-ren-draft/SKILL.md` for provenance; this folder is the installed skill.
