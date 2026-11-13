# voice.md — レン／リリの声（@ren_ai_nerve）

Upstream `templates/voice.md` assumes the account owner speaks on camera.
For @ren_ai_nerve the speaker is a character, so this file replaces it.
Written 2026-11-08 at install time, from ino's approved direction.

## Speaker

- 見習いリリ先生: white Shiba, childlike apprentice teacher — not a polished,
  competent teacher. She tries hard and is endearing doing it.
- Look: oversized white coat (large from the collar down, sleeves too long),
  nose is light brown, pinkish — never black like Roro's.
- Baseline sample (approved by ino 2026-10-30):
  `~/workspace/imagine_media/media-generation-shiba-kid-doctor-trial2-0-209e2779-9a6e-46a8-bb2d-8e124f04f735.webp`
- Roro (black Shiba): never almost solid black — big cream markings on
  cheek, brow, around the mouth, chest and legs.

## Voice in scripts

- One voice only: Riri's cute single voice (TTS default voice, ja).
  Lines are short — one idea per line, sized for telop.
- Tone: childlike and earnest. The opening 0–1 seconds may be a visual
  gag (e.g. tripping over an oversized stethoscope), but the procedure
  itself is stated correctly and plainly.
- Telop carries the story: state a problem or a feeling, not an
  explanation. The health point lands as one line inside the story or
  in the caption.
- Health wording follows the AI.md brief's NG→OK table, always:
  no 消える・治る・若返る・痩せる as effects, no mechanism stated as
  fact, hedge (〜と言われています／軽く感じる人も), and close with
  「強い痛み・しびれが続く場合は医療機関へ」 where the brief requires it.
- Fixed wording example (mouthwash): never 「神経に効く」. Say that
  rinsing before the morning water means not swallowing the bacteria
  that grew overnight, framed as an image that connects to 腸活 —
  never as a stated effect.

## Reading speed

- Measured (C1 smoke test, 2026-11-08): Riri's TTS voice reads about
  **5.3 kana/second** — C1's five line recordings total 13.1 seconds of
  speech for about 69 kana sounds. Always run `beats.py` with
  `--cps 5.3` for Ren scripts; the upstream default of 9 is a human
  talking-head speed and underestimates every line.
- At 5.3, per-line estimates land within about 0.9 seconds of the real
  recordings. The remaining reel time is clip pacing and pauses, which
  the tool does not model — judge total runtime from the edit, not
  from `beats.py`.
