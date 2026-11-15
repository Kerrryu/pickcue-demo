# PickCue | Proposed pilot at GottaGacha

Handoff for whoever is building the pitch deck. The demo's official address is
`https://gottagacha.com/labs/pickcue`. This repository hosts the screenshots, the video and this
note, plus a mirror of the built demo. It does not hold the source.

## What it is

PickCue is a prototype heads-up pick list for trading-card singles on Even Realities G2 glasses.
A picker sees one card at a time (bin, name, set and number, finish, labeled condition, quantity),
checks the card in hand, and taps to move on. It is proposed as a pilot at GottaGacha, an esports
gaming arcade in Warren, Michigan.

The pitch is for a G2 developer loaner. The software runs in a browser and in Even's official
simulator today; the loaner is what would let it be tested on real glasses.

## Wording rules

- Cover line: **PickCue | Proposed pilot at GottaGacha**
- Presenter: **Sebastian Maj, GottaGacha co-founder and 168 Group technical director**
- Do not write "Built by OMOWorlds" anywhere. OMOWorlds may appear only in a short founder bio as
  part of his software track record.
- Do not imply 168 Group is formally backing the project.
- Who owns the code, who applies to Even Hub and who publishes is not decided. Do not state or
  imply an answer.
- Call it a prototype. All data is synthetic: the cards, sets, bins and the order are invented.

## Live demo

The official address for the deck is **https://gottagacha.com/labs/pickcue**. It is live on the
GottaGacha site as of 15 November 2026. Use that link in slides.

| What | Link |
| --- | --- |
| Official (use this in the deck) | https://gottagacha.com/labs/pickcue |
| Pick | https://gottagacha.com/labs/pickcue?snapshot=pick |
| Exception | https://gottagacha.com/labs/pickcue?snapshot=exception |
| Resume | https://gottagacha.com/labs/pickcue?snapshot=resume |
| Summary | https://gottagacha.com/labs/pickcue?snapshot=summary |
| Display only, for screenshots | https://gottagacha.com/labs/pickcue?view=capture&snapshot=pick |
| Display plus one-line label | https://gottagacha.com/labs/pickcue?view=capture&label=1&snapshot=pick |

This GitHub Pages site is only the file host for the images, the video and this note. Do not use
its address as the demo link in the deck.

Controls: Enter taps, Down arrow swipes down, Up arrow swipes up, U double-taps, keys 1 to 4 jump
to the four moments. On a phone, use the four buttons at the bottom or tap the display.

## Images and video

All PNGs are 1920 x 1080 unless noted. Each already carries its own label at the bottom.

Simulator set. These are the official Even Hub simulator's own output, enlarged 3x. Caption them
as "Even Hub simulator", never as glasses or hardware.

| Moment | File |
| --- | --- |
| Pick | https://kerrryu.github.io/pickcue-demo/screenshots/simulator-1-pick.png |
| Exception | https://kerrryu.github.io/pickcue-demo/screenshots/simulator-2-exception.png |
| Resume | https://kerrryu.github.io/pickcue-demo/screenshots/simulator-3-resume.png |
| Summary | https://kerrryu.github.io/pickcue-demo/screenshots/simulator-4-summary.png |

Browser set. Same four moments in the browser preview. Caption them as "browser prototype".

| Moment | File |
| --- | --- |
| Pick | https://kerrryu.github.io/pickcue-demo/screenshots/browser-1-pick.png |
| Exception | https://kerrryu.github.io/pickcue-demo/screenshots/browser-2-exception.png |
| Resume | https://kerrryu.github.io/pickcue-demo/screenshots/browser-3-resume.png |
| Summary | https://kerrryu.github.io/pickcue-demo/screenshots/browser-4-summary.png |

Other files:

| What | File |
| --- | --- |
| Whole demo page, desktop | https://kerrryu.github.io/pickcue-demo/screenshots/browser-demo-desktop.png |
| Whole demo page, phone (1170 x 1992) | https://kerrryu.github.io/pickcue-demo/screenshots/browser-demo-phone.png |
| Display alone, no label (1728 x 864) | https://kerrryu.github.io/pickcue-demo/screenshots/browser-hud-only-pick.png |
| Raw simulator frames, unlabeled, 576 x 288 with transparent background | `screenshots/simulator-raw-1-pick-576x288.png`, `-2-exception-`, `-3-resume-`, `-4-summary-`, `simulator-raw-variant-576x288.png` |
| Walkthrough video, WebM, 1920 x 1080, 51 seconds, 14 captioned steps | https://kerrryu.github.io/pickcue-demo/screenshots/pickcue-simulator-walkthrough.webm |

The video is a step-by-step slideshow of real simulator frames captured during the automated run.
It is not a continuous screen recording. It is WebM; Keynote and PowerPoint may need it converted
to MP4.

## What each moment shows

1. **Pick.** The first card of a six-line order. Bin, card name, set and number, finish, labeled
   condition and quantity are on one screen. Lines 1 and 2 are the same card in different finishes
   (NON-FOIL and HOLO FOIL), so the display adds a warning.
2. **Exception.** A card is not in its bin. The picker swipes down and the display asks before it
   closes the line as missing. Tap confirms, swipe up cancels, double-tap undoes it afterwards.
3. **Resume.** The picker confirmed the first of two copies, then the session was dropped. It
   comes back on the same line asking for copy 2 of 2, marked RESUMED.
4. **Summary.** Every line is picked or flagged: 5 lines picked, 1 flagged missing, 6 of 7 cards
   picked, 1 short, and the missing card is named.

## What has been verified (15 November 2026)

| Level | Result |
| --- | --- |
| Browser | 61 unit tests on the picking logic passed. 14 browser scenarios passed at desktop and phone size (28 runs, Chromium). |
| Official Even Hub simulator 0.9.5, SDK 0.0.16 | 10 scripted steps passed, driven through the simulator's automation port. |
| G2 hardware | Not tested. |

Behaviours covered at all three test layers (unit, browser, simulator): two look-alike variants,
a quantity of two confirmed one copy at a time, flagging a missing item, undo, resuming the
unfinished copy, a double-fired tap counted once, summary totals, and a deliberate two-step reset.

## Claims the deck can make

- The same picking logic drives the browser preview and the Even Hub build.
- The Even Hub build runs in Even's official simulator and passed a scripted run there.
- It uses only documented SDK text, input and storage calls, and needs no permissions, network,
  microphone, camera, ring or Enterprise access.
- Staff check the physical card. The app shows the condition written on the label.
- In the simulator, progress survived the simulator process being killed and relaunched.
- The build packs into a valid Even Hub package locally. Nothing has been uploaded to Even Hub.

## Claims the deck must not make

- That it has run on G2 glasses, in the Even app on a phone, or with an R1 ring.
- That phone lock, app backgrounding, app kill or Bluetooth loss have been tested. The resume test
  was a browser reload and a simulator restart, not an Android or iOS lock test.
- That the app scans, identifies or grades cards.
- That it is connected to GottaGacha inventory, orders or customers. It is not.
- That browser screenshots show the simulator, or that simulator screenshots show the glasses.
- That readability, brightness, battery or comfort in a real shop are known.

## What the loaner would answer

These came out of the simulator run and can only be settled on a device:

- Which storage survives on a real phone. In the simulator, the SDK's bridge storage did not
  survive a restart; the app's second copy in the WebView's storage did.
- Whether a save made in the instant before the app is killed is lost. In the simulator it can be,
  which would make the picker re-confirm one card.
- Whether the text is readable at arm's length from a bin in shop lighting, and whether the
  tap, swipe and double-tap gestures are comfortable while holding cards.
- Phone lock, backgrounding and Bluetooth drops during a pick.

Contact for corrections: Sebastian Maj.
