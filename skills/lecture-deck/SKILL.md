---
name: lecture-deck
description: Turn lecture content into a clean, branded .pptx in an organization's template, with full timed speaker notes. Use when asked to build or restyle a presentation or lecture deck.
---

# Lecture deck: content into a branded template

The lecturer focuses on content; the visual follows the organization's template. Output is a .pptx (presented from PowerPoint or Google Slides). Slides and speaker notes are in the lecture's language unless told otherwise.

Load the pptx skill first, then follow this.

## 1. Read both files
- Source lecture: extract every slide's text AND speaker notes.
- Template: thumbnail grid + list of layouts, placeholders, logo position, theme colors and fonts (python-pptx).
- Map each source slide to a template layout before building. Third-party materials stay private: never publish them.

## 2. Build approach (python-pptx on top of the template file)
- Open the template .pptx itself so masters, layouts, logo and fonts carry over.
- Reuse template slides that contain artwork (title slide with photo, break slide, final slide) by editing their runs; set text run by run so formatting is kept.
- New content slides: the template's "title + body" layout; remove the unused body placeholder, widen the title to the content width (max 2 lines).
- Remove unused template slides by dropping them from `sldIdLst`, then reorder to the final order.
- Validate the file, render it to images and check every slide.

## 3. Visual system (keep it identical across decks)
- White content slides; one motif: rounded cards (corner ~0.06) in a very light tint of the brand's dark color, no outlines, no accent stripes.
- Numbered items: small filled circles (brand accent color, white bold number) on the card's top-left edge or left of a row.
- Key question or quote: large bold text in the accent color, no box.
- Emphasis card: at most one accent-filled card per slide (golden rule, task, key point) with white text; a dark-brand-color card for legal/consequence content.
- Layout patterns to vary between: 3 columns, 5 columns, 2 columns (light + accent), stacked rows with number circles, 2x2 grid, 2x4 checklist, timeline with colored date chips, full-width banner at the bottom.
- Contrast (gradient) slides from the template only for: title, break, summary, thanks.
- Content area: 0.5" margins, below the title, above the logo. Body 10.5–12 pt, card headings 11.5–13 pt bold, 0.15–0.2" gap between cards.
- The text stays the source's text; shorten only if it would overflow, and say so.

## 4. Slides the template usually expects
- Title (lecture name, lecturer, format/length; leave out unknown dates).
- A licence slide, if the template has one, stays as it is (hidden if it is hidden).
- Learning goals ("what you will be able to do") and a summary (3–4 real takeaways, not repeated goals). Write them from the content and flag them as added.
- Break slide: just the word for break, big, plus a short text; no time to fill in (the lecturer says it aloud).
- Thanks slide + the template's closing image.

## 5. Speaker notes (always complete, always timed)
Every slide gets notes in this structure:
```
TIME: h:mm–h:mm (N min) | Topic
GOAL: ...
STEPS: numbered steps (activity, chat, breakout)
KEY POINTS: what to say
TIP: practical prep (open tabs, test audio, ...)
TRANSITION: one sentence to the next slide
```
- Times run without gaps from 0:00 to the full length (e.g. 3:00). After any change, recompute and check the total.
- Use only facts that are in the deck; mark facts that can change ("verify shortly before").
- Breakout rooms: split the time into assignment / work / sharing and say what to watch for.

## 6. Delivery
Check and deliver the .pptx. Number slides as the lecturer sees them in the preview (hidden slides not counted) and say so if that is ambiguous. Report briefly what was added or shortened.

## Brand profiles
Keep one profile per organization: colors (dark text color, accent, gradient, light card tint), fonts (headings, body), template file name and slide size, logo position, and how participants are addressed. Fill in a new profile before building the first deck for that organization.
