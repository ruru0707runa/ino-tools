# Smoke test — 2026-11-08 (install day)

Scope approved by ino: inspection + smoke test only. Nothing posted,
nothing generated, no locked reel reworked.

## Inspection

- Repo cloned to `~/workspace/custom-skills/_staging/instagram-agent-skill-ja`
  (this time the clone succeeded; earlier attempts failed with TLS/403).
- All 13 upstream `SKILL.md` files read (headers + mapping); all Python
  tools read by pattern inspection: imports are stdlib only (argparse,
  json, os, re, statistics, sys, unicodedata) plus the local `jp.py`
  (identical md5 in all three upstream copies). No urllib / requests /
  socket / subprocess / os.system / eval / exec anywhere. File writes
  happen only with an explicit output path (`humanize.py --out`,
  `swipe.py --out`). README's "no network, sends nothing out" claim is
  now verified at the code level for this snapshot.

## Tools copied to `tools/`

hookscore.py, beats.py, jp.py, hooks.json, caption.py, humanize.py,
detect.py, slop.json, swipe.py, rubric.json.

## Smoke test on C1 (mouthwash, finished reel, 20.0s, reserved 11/13)

Script source: `~/workspace/ig_ren_ai_nerve/mouthwash_reel_script_2026-10-27.md`
+ `c1_mouthwash/config_c1.json` (actual line timings and audio files).

### hookscore.py on the C1 hook 「その水、ちょっと待って」

- Total 32.4 — 弱い. Breakdown: 長さ 100, 具体性 15 (no numbers or
  names), 懸かっている物 20, 前に置く 30, 相手に向く 55.
- Weakest: specificity. Consistent with ino's own critique that the
  hooks are not common-sense-breaking enough. Calibration only —
  C1 is locked and was not reworked.

### beats.py on the 5 C1 lines

- Default 9 kana/s: total speech estimate 7.7s — far under the real
  recordings, because the default is a human talking-head speed.
- Actual line recordings (ffprobe): 1.44 / 3.29 / 2.95 / 2.93 / 2.52s,
  total 13.1s for ~69 kana sounds → measured speed ≈ 5.3 kana/s
  (`beats.py --measured 13.1` agrees: 5.3).
- At `--cps 5.3`: per-line estimates 2.0 / 3.8 / 2.5 / 2.8 / 2.0s —
  within ~0.9s of the recordings on every line.
- The reel's remaining time to 20s is clip pacing and pauses between
  lines (actual line starts 0.4 / 6.4 / 10.4 / 13.8 / 17.2s), which
  the tool does not model. Use beats.py for speech length only.

### caption.py on the C1 caption draft (bonus)

- Works. Visible part before the fold: 「朝起きて、すぐ水を飲んでいませ
  んか？」. Flags: no concrete number/name in the visible part, and no
  ask (お願い0つ) in the caption draft. Hashtags 5 — OK.

## Verdict

Tools are safe and usable for Ren with `--cps 5.3`. First live use is
the next reel script after the 9-test, per the draft checklist.
