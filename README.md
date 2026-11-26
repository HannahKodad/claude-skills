# claude-skills

Claude skills and agent specifications by **Hannah Kodad** (Smartflow AI).

I help individuals and small businesses use AI safely: data management, automations and AI workflows that stay transparent and under human control. This repository shows how I work: the skills I use every day, the template I design agents with, and one agent specification from real use. I add new skills step by step.

## What you find here

| Path | What it is |
| --- | --- |
| `skills/learning-with-ai/` | Base skill for learning **with** AI, never instead of the learner: teacher + assistant roles, one step at a time, vocabulary log for a second language (examples in Swedish). |
| `skills/learning-with-ai-and-swedish-vocabulary/` | My own learning in Swedish (IT-pedagog, svenska som andraspråk, courses in Sweden): learning **with** AI, and every piece of work ends with new words for a Swedish–English–Czech vocabulary. English `SKILL.md`, Czech `SKILL.cs.md`. |
| `skills/swedish-vocabulary/` | Svensk ordlista: a Swedish–English–Czech vocabulary built from every piece of work, as word-family blocks (all verb, noun and adjective forms, word breakdown, homonyms) for a Google Sheet that a language app can read. No duplicates. English `SKILL.md`, Czech `SKILL.cs.md`. |
| `skills/data-guard/` | Safe data handling for clients' data: nothing is deleted by AI, to-delete folders, GDPR protection levels, confirmation cards, admin log. Companion to the data-guard plugin in [smartflow-ai-public](https://github.com/HannahKodad/smartflow-ai-public). |
| `skills/meeting-to-offer/` | Turns a client meeting transcript into a needs analysis (every need backed by a quote) and a draft offer from your own price list. Two human checkpoints, no invented prices, nothing sent to the client. Includes a fictional end-to-end example in Czech. |
| `skills/lecture-deck/` | Turns lecture content into a clean deck in an organization's template, with complete timed speaker notes. |
| `skills/ikt-pedagog/` | School assignments in ICT pedagogy and the frameworks RAT, PICRAT, SAMR and TPACK. |
| `templates/TEMPLATE.md` | Template for specifying an AI agent: purpose, scope, access, approval points, tests, metrics and version history. |
| `agents/agent-builder.md` | Example specification: the agent that designs, versions and reviews all other agents (anonymised). |

## Principles behind the work

1. **The human has the last word.** AI prepares, the person decides. Nothing is sent, merged, shared or deleted without explicit approval.
2. **Nothing gets deleted by AI.** Files to delete go to a to-delete folder; a person deletes them after review.
3. **Least privilege.** Every agent gets only the access it needs, and every access has a written reason.
4. **Data stays where it belongs.** Personal data does not leave the client's environment.
5. **Learning with AI, not outsourcing to it.** The learner stays in the process and can explain what they did and what the AI did.

## Learning and teaching

- I study **IT-pedagog** (ICT pedagogy), a one-year course at a folk high school in Sweden, in Swedish. My course website: [it-pedagogy](https://github.com/HannahKodad/it-pedagogy).
- I teach: **AI and ethics** – a 3-hour interactive online workshop for participants of the course *Manažerka AI transformace* (AI transformation manager) at Czechitas. Topics: where bias comes from in data and models, a 7-question data bias audit, what the EU AI Act requires today and what is coming, data rules for a company ("data traffic light"), safe boundaries for AI agents and deepfake fraud, and an ethical stress test of a transformation project. The course materials belong to Czechitas, so the slides are not published here.

## How to use a skill

1. Download the `SKILL.md` file from the skill's folder.
2. Add it as a skill in Claude (in Claude Code: save it to `~/.claude/skills/<skill-name>/SKILL.md`).
3. Adapt names, folders, languages and protection levels to your own setup.

A skill is a set of instructions, not a technical lock. For hard limits, combine it with technical controls such as access rights, branch protection or hooks.

## Contact

- LinkedIn – Hannah Kodad: [linkedin.com/in/hannah-kodad](https://www.linkedin.com/in/hannah-kodad/)
- LinkedIn – Smartflow AI – CZ: [linkedin.com/showcase/111983362](https://www.linkedin.com/showcase/111983362/)
- Babička na treku: [babickanatreku.cz](https://babickanatreku.cz/)

## License

No license yet. You are welcome to read and learn from the content; ask before reusing it.

---

Hannah Kodad · Smartflow AI
