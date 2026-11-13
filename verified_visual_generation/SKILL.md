# Verified Visual Generation

## Clarify what the reference shows

- Ask the user whether a supplied image supplies style, content, or both before you reuse any element from it.

- Restate the decision the visual must support in one sentence before you generate anything, and let that sentence decide what to include and what to leave out.

- Confirm the audience, the format, and the single action the reader should take after seeing the visual.

## Verify facts before you draw

- Check each anatomical or technical claim against the source the user gave or a trusted reference before you place it in the image.

- Draw each structure in the view where it actually lives, and add a second view when one view cannot show both sides honestly.

- Keep each label short, keep it tied to one structure, and leave out a detail the source does not support.

- Name the source for a contested placement in your reply, and say what remains uncertain instead of filling the gap with a guess.

- Compare each generated dog against real photos of the dogs before delivery, and fix drift in the plan rather than accepting a close likeness.

- Give Roro cream markings on cheek, brow, mouth area, chest and legs, and never render him almost solid black.

- Give Riri a light brown pinkish nose, and never give her the same black nose as Roro.

- Render the white Shiba doctor as childlike in an oversized white coat that is large from the collar down with long sleeves, so she reads as a cute child trying hard rather than a polished teacher.

- Keep a supine dog head aligned with its body with its nose pointing to the ceiling, and never turn the head sideways.

- Use the approved trial 2 image at ~/workspace/imagine_media/media-generation-shiba-kid-doctor-trial2-0-209e2779-9a6e-46a8-bb2d-8e124f04f735.webp as the baseline for the white Shiba doctor, and check new frames against it before delivery.

## Lock the script before you generate video

- Build a measured frame table from the source itself before you write the timed script for a reproduction, and record a start second and an end second for each distinct movement, pose change and camera move.

- Never split a source into equal length clips, and never add a movement the source does not show at those seconds.

- Measure the music tempo in beats per minute and in seconds per beat, and plan each movement to land on a beat with the whole body moving, repeating the cycle the source repeats instead of holding one pose.

- Mark any estimated second as an estimate, and do not promise an exact reproduction until the frame table and the beat are measured.

- When the script teaches steps from a source brief, copy the source step order into the locked plan and check every draft line against it before production.

- Never carry a step order from an intermediate outline or idea book without re-checking the source, and fix the outline too when its order differs from the source.

- Write a timed script that names the speaker for every line and the seconds when only that speaker moves.

- Give silent action its own seconds, and hold every other speaker still while one speaker talks.

- State plainly what you did not check in audio or motion after generation, and offer a silent video with separately timed captions and voice when exact timing matters.

## Check the result and fix the cause

- Compare the generated output against the locked plan, and name each mismatch by time and speaker before you regenerate anything.

- Name the worst visible defect plainly in your reply, with its timestamp and what it actually is, and never soften it into a vague phrase.

- Rewrite the plan first when the same mismatch repeats, instead of regenerating from the same prompt.

- Offer a still diagram with narration when generated motion keeps distorting a fact that must stay accurate.

## Platform safe zones (Instagram Reels, learned 2026-10-25)

The user flagged that reel 1 text was hidden behind Instagram own UI. Rules for any 720x1280 vertical video (scale proportionally for other sizes):

- Keep ALL burned-in text inside y 170 to 1030. The top 150px is covered by the app status bar and the tab row; the bottom 250px is covered by username, caption and action UI.

- Keep text out of the right rail (x 640 or more) below mid-height, where like, comment and share icons sit.

- Never stack two text elements in the same band at the same time (telop plus subtitle overlapped in reel 1 and produced unreadable double text).

- Check every text line rendered width before burning in: a line wider than the canvas gets clipped at both edges (happened to a 21-char subtitle at fontsize 40).

- When an existing cut has text in the danger zone, shifting the whole frame down (scale plus black pad on top) moves top text into the safe zone without a rebuild; rebuild from a clean base when bottom text is also affected.

- Verify fixes by extracting frames at the exact timestamps where each text element appears and viewing them before delivery.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Use a still diagram plus a short narration script when motion would hide the exact placement you need to teach.

- Ask the user to approve the timed script and the placement list before generation when a correction would cost another full generation cycle.

- Offer a text checklist of the steps when the user mainly needs something to follow later rather than a polished video.
