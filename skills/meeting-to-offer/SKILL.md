---
name: meeting-to-offer
description: Turn a client meeting transcript into a needs analysis and a draft offer (nabídka), with two human checkpoints. Use when someone shares a meeting transcript, call notes or recording summary and wants a client offer, proposal or quote prepared from it.
---

# Meeting to offer

Turns a transcript of a meeting with a (potential) client into:

1. a **needs analysis** – what the client really needs, backed by quotes from the transcript,
2. a **draft offer** – a proposal in the client's language, built from the company's own service list and price list.

The skill prepares. A human decides. Nothing is ever sent to the client by this skill.

## Principles

- **Human in the loop.** Two checkpoints: after the analysis and after the draft. Do not skip them unless the user explicitly says so.
- **Evidence, not guesses.** Every need in the analysis points to what the client actually said (speaker + quote or timestamp). What is only implied is marked as *assumption*.
- **Never invent prices, dates or promises.** Prices come only from `references/pricing.md` (or the price list the user gives). Anything missing is written as `[DOPLNIT: ...]` / `[FILL IN: ...]` and listed for the user.
- **Simplest solution that works.** Propose the lowest level of automation that solves the need (see the ladder below). An autonomous agent is not a goal in itself.
- **Data care.** A transcript is client data. Use it only for this task, do not upload it anywhere, do not copy personal details (phone numbers, private matters, other people's names) into the offer unless they are needed there. If the transcript contains sensitive data (health, finances of private persons, children), say so at checkpoint 1.

## Inputs

- **Transcript** – pasted text, a file, or a document. Any format (Teams, Zoom, Fireflies, Plaud, YouTube-style, plain notes).
- **Price list / service list** – `references/pricing.md`. If it still contains placeholders, ask the user for the real one or keep `[DOPLNIT]` markers.
- **Offer template** – `references/offer-template.md` (the company can replace it with its own).
- Optional: who the user is in the transcript (so the skill knows which speaker is "us").

If no transcript is given, ask for it. Ask nothing else before reading it – most answers are inside.

## Workflow

### Step 1 – Read and map the meeting

Identify:

- **Who is who:** speakers, their roles, who decides, who will use the solution.
- **Client context:** company, size, field, tools they already use (e-mail, Google/Microsoft, CRM, ERP, Excel…), their AI experience so far.
- **Pain points:** what costs them time, money or nerves. Look for numbers ("2 hours a day", "40 orders a week").
- **Goals:** what they want to achieve and how they will know it worked.
- **Explicit asks** vs **implied needs** – keep them apart.
- **Constraints:** budget, deadline, data sensitivity / GDPR, IT restrictions, people's fears or resistance.
- **Agreed next steps** from the meeting.

### Step 2 – Needs analysis → CHECKPOINT 1

Write the analysis in the structure below and **stop**. Ask the user to confirm or correct it.

```
## Analýza potřeb – [klient], schůzka [datum]

**Kdo je klient:** 2–3 věty.
**Kdo rozhoduje / kdo bude řešení používat:** …

### Potřeby (podložené přepisem)
| # | Potřeba | Důkaz z přepisu | Priorita |
|---|---------|-----------------|----------|
| 1 | … | „…“ (Jana, 12:40) | vysoká |

### Předpoklady (z přepisu nevyplývá přímo)
- …

### Omezení a rizika
- …

### Otevřené otázky – co chybí k nabídce
- …

### Doporučený rozsah (návrh)
- Úroveň řešení podle žebříčku + proč.
```

Use the language of the transcript for client-facing text (Czech transcript → Czech). Keep the analysis short enough to read in two minutes.

### Step 3 – Choose the solution level

The automation ladder – go only as high as the need requires:

1. **Chat + context** – the team uses AI with good prompts and shared company context.
2. **Skills** – a repeated task becomes a reusable skill (offer drafts, replies, reports).
3. **Routines / workflows** – scheduled or triggered flows (e.g. n8n, Make, Power Automate) with AI steps.
4. **Agent with checkpoints** – AI acts across tools, a human approves key steps (sending, paying, deleting).
5. **Autonomous system** – runs on its own; only where errors are cheap and reversible.

For each proposed part state: what it solves (need #), level, human checkpoint, what the client must provide (access, data, a contact person).

### Step 4 – Draft the offer → CHECKPOINT 2

Fill `references/offer-template.md`:

- Map each proposed part to an item from the price list. No matching item → `[DOPLNIT: cena]`.
- Phases with realistic order: start small (pilot), measure, then extend.
- Write for the client, not for us: their words, their numbers, their benefit. No jargon they did not use.
- Add an **internal note** block (kept separate, not for the client): assumptions, risks, what to verify, margin of uncertainty in effort.

Then run the self-check and present the draft:

- [ ] Every offer item traces back to a need from the analysis.
- [ ] No price, date or promise that is not in the price list or the transcript.
- [ ] All `[DOPLNIT]` markers listed for the user.
- [ ] Human checkpoints are visible in the offer (client knows where people stay in control).
- [ ] No unnecessary personal data copied from the transcript.
- [ ] Language and tone match the client.

End with: what the user should check, the list of `[DOPLNIT]` items, and a reminder that the offer is a draft – the user sends it, not the skill.

## Output

1. Needs analysis (checkpoint 1).
2. Draft offer + internal note (checkpoint 2).
3. Optional on request: a short cover e-mail to the client, and a list of questions for a follow-up call.

Save outputs where the user asks. If unsure, deliver them in the conversation as editable documents.

## Files

- `references/offer-template.md` – offer structure (Czech).
- `references/pricing.md` – service and price list template (company fills in).
- `examples/` – a fictional end-to-end example: transcript, analysis, offer.
