# Instagram Skill for @ren_ai_nerve — DRAFT (not installed)

Status: DRAFT prepared 2026-11-08. Not installed, not wired into any workflow.
Nothing here posts, reserves, or generates anything. Use only after ino says go.

## Source (verified 2026-11-08 via the public repo page)

- Repo: https://github.com/Alman-creator-uslog/instagram-agent-skill-ja
- Public, MIT licence, created 2026-10-28, 8 stars, 5 commits at check time.
- No API key, no account login, no external service needed (README).
- 13 skills, 5 local Python tools. README states the tools do not connect
  to the network and send nothing out — that claim itself is NOT yet verified:
  a `git clone` from this preparation run was denied (HTTP 403), so the
  tool files were never read here. Before any tool is run, clone the repo
  and inspect each `.py` file line by line for network / subprocess calls.
- The skill never posts: "あなたがOKと言うまで、何も投稿しません" is its
  design, matching ino's rule (no publishing without an explicit "post").

## What the repo's own validation says (do not overclaim)

- Hook scoring separates bad hooks from good ones well (AUC 0.91) but
  cannot separate hits from misses inside one genre (AUC 0.47 — no better
  than chance). Use it ONLY as a filter to drop weak hooks before shooting.
  It never guarantees a viral hook.
- Timing estimate (`beats.py`): reading speed default 9 kana/second;
  measure Riri's actual voice speed with `--measured` and reuse that number.
- Caption check: what is visible before "…続きを読む" is about 30 full-width
  characters; hashtags are checked against a limit of 5 per post.
- Growth comparison (`swipe.py` / `/ig-viral`): rank by multiple of each
  account's own median views, never by raw view count.

## Ren rules — these override the upstream skill wherever they conflict

1. **Health-expression filter wins.** The upstream hook types include
  煽り ("損する""失敗" style). In ren, the AI.md brief's NG→OK table is
   the top rule: never use 消える・治る・若返る・痩せる as an effect,
   never state a mechanism or effect as fact, always hedge
   (〜と言われています / 軽く感じる人も), and close with the medical-care
   line where the brief requires it. A hook that needs a banned claim is
   dropped, however high it scores.
2. **Voice is Riri, not ino.** Upstream `templates/voice.md` assumes the
   account owner speaks on camera. Replace it with the Riri voice:
   childlike apprentice teacher, cute single voice, oversized white coat,
   light-brown pinkish nose. Roro: cream markings on cheek, brow, mouth,
   chest and legs — never almost solid black. Baseline sample is trial 2:
   `~/workspace/imagine_media/media-generation-shiba-kid-doctor-trial2-0-209e2779-9a6e-46a8-bb2d-8e124f04f735.webp`.
3. **Format is the 9-reel test, not generic reels.** 20 seconds, moving
   clips only (no stills carousel — carousel video is banned), telop in
   the safe zone (720×1280, y≈170–1030, keep clear of the right icon
   column), telop mandatory so the reel reads without sound, single
   movement focus. Judge by the 1,500-view gate, then the 48-hour rule.
4. **No auto-posting, ever.** Drafts only. Reservation / posting stays on
   the existing approved flow (explicit approval per reel).
5. **Numbers are claims until checked.** Instructor figures in the repo
   and in any benchmark account are claims. Ren's own numbers come from
   the app's insights (connector cannot fetch per-reel views).

## Which upstream skills map to ren work

- Use: `/ig-reel` (hook 3-way + score + script + telop + timing table),
  `/ig-viral` (growth-multiple ranking), `/ig-caption` (visible-30-char
  check), `/ig-profile` (re-check the new bio), `/ig-audit` (growth
  multiple + shares per reach, not raw views), `/ig-human` (AI-phrasing
  cleanup for captions).
- Feed-only: `/ig-carousel` may be used for feed posts only, never for
  carousel video.
- Do not use without a separate instruction: `/ig-story`, `/ig-comment`,
  `/ig-reply`, `/ig-dm`, `/ig-plan`, `/ig-repurpose`. None of these is in
  the current 9-reel test or Threads plan.

## Install checklist (for the main agent, after ino's go-ahead)

1. `git clone https://github.com/Alman-creator-uslog/instagram-agent-skill-ja.git`
   into a staging folder; read every `SKILL.md` and each of the 5 Python
   tools (`hookscore.py`, `beats.py`, `caption.py`, `humanize.py`,
   `detect.py`, `swipe.py`) and confirm no network calls before running any.
2. Copy into `~/workspace/custom-skills/instagram-ren/` as one merged skill
   with this file's Ren rules at the top; do not copy into `~/.claude/skills/`.
3. Write `voice.md` for Riri (not ino) from the approved trial-2 sample and
   the C2 apprentice-teacher direction.
4. Smoke-test on an existing script first (e.g. C1 mouthwash): run
   `hookscore.py` on its hook and `beats.py --target 20` on its lines,
   and compare the timing table against the finished C1 reel before
   trusting the tools on a new reel.
5. First live use: the next reel script after the 9-test (B3/C1/C2/C3 are
   already locked — do not rework them with this skill without approval).
