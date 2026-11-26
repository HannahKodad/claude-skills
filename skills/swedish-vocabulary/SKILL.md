---
name: swedish-vocabulary
description: Svensk ordlista: Hannah's trilingual vocabulary (Swedish-English-Czech) from all her learning. Offer new words after each work as word-family blocks for her Google Sheets glossary on Smartflow, no duplicates.
---

# Svensk ordlista

*Swedish – English – Czech vocabulary*

*(A Czech version of this skill is in `SKILL.cs.md`.)*

Hannah always needs to widen her Swedish vocabulary: technical (by field) and everyday spoken language, so that her speech becomes rich and natural. She learns English through Swedish, so the vocabulary is **trilingual for all her learning**: Swedish – English – Czech.

A language-learning app will later draw on this vocabulary. That is why the data must always have the same structure.

## When

From every piece of work where new Swedish words come up: school materials, assignments, texts we write together, everyday conversation.

## Process

1. **Duplicate check:** before offering words, I read the main vocabulary sheet. I don't offer words that are already in it. I compare the base form and the word family (*förberedde* belongs to the family *förbereda*).
2. **Offer:** at the end of a part of the work I offer 5–10 new words. Hannah chooses which ones to add.
3. **A new member of an existing family** is added to that family's block; no new family is created.
4. **Saving:** I write the chosen words as a small sheet into the inbox folder on Smartflow. A script in the main sheet (Google Sheets) picks them up, skips duplicates and moves the processed file to a "done" folder. Nothing is deleted.
5. I save nothing without Hannah's yes.

*(The names of the main sheet and the folders on Smartflow will be added once they exist.)*

## Structure: blocks by word family

One block = one word family (ordfamilj). Each row = one member of the family. All rows of a block have the same value in the `family` column.

**Fixed order within a block:** verb → noun → adjective → adverb → compounds → set phrases. A member that doesn't exist is left out.

### Columns

In Hannah's sheet the column names are in Czech (in brackets).

| family (rodina) | type (typ) | sv | forms (tvary) | en | cs | word breakdown (rozpad slova) | example sentence (příkladová věta) | synonyms and variants (synonyma a varianty) | field (obor) | source (zdroj) | date (datum) |
|---|---|---|---|---|---|---|---|---|---|---|---|

- **synonyms and variants:** a more colloquial / more formal variant
- **field:** IT-pedagog, svenska som andraspråk, guiding, spoken language…
- **source:** which task or material the word comes from (e.g. "17b Podcast manus")
- **date:** date added

### Forms by type (all written out in full)

- **Verb:** infinitive · present · preterite · supine · perfect (har + supine) · pluperfect (hade + supine) · imperative
  - e.g. *förbereda · förbereder · förberedde · förberett · har förberett · hade förberett · förbered!*
- **Noun:** indefinite and definite form, singular and plural
  - e.g. *en förberedelse · förberedelsen · förberedelser · förberedelserna*
- **Adjective:** en / ett / plural forms + comparative + superlative
  - e.g. *stor · stort · stora · större · störst*
- **Adverb:** base form (and comparison where it exists)
- **Compound:** the parts of the word
- **Set phrase:** no forms

### Word breakdown (a note on the row, in Czech)

- I split the word into its parts (prefix, root, suffix, parts of a compound). I don't translate the parts; the whole word is translated in the en and cs columns.
- I explain what the prefix or suffix does and why it is this one, e.g.: *för + bered(a) + -else · -else turns a verb into a noun (action / result); -het attaches to adjectives (fri → frihet)*.
- For compounds I note how combining the parts changes the meaning.
- **Homonyms:** write *homonym* in the note and refer to the families of the other meanings. The word belongs primarily to the family of the meaning it appeared in, e.g. *fil* = file (IT): *homonym – see also fil = soured milk (filmjölk), fil = lane (byta fil), fil = file, the tool (fila)*.

## Example block

| family | type | sv | forms | en | cs | word breakdown |
|---|---|---|---|---|---|---|
| förbereda | verb | förbereda | förbereder · förberedde · förberett · har förberett · hade förberett · förbered! | to prepare | připravit | för + bereda · för-: beforehand, in advance |
| förbereda | noun | förberedelse | en förberedelse · förberedelsen · förberedelser · förberedelserna | preparation | příprava | för + bered(a) + -else · -else: verb → noun (action / result) |
| förbereda | adjective | förberedd | förberedd · förberett · förberedda | prepared | připravený | participle of förbereda |
| förbereda | compound | förberedelsetid | förberedelse + tid | preparation time | čas na přípravu | förberedelse + tid · time set aside for preparation |
| förbereda | set phrase | vara väl förberedd | – | to be well prepared | být dobře připravený | – |

*(In Hannah's sheet the breakdown notes are written in Czech; they are shown in English here.)*

## Explaining

When Hannah asks how a word is formed (why this suffix, where the word comes from), I explain it in the chat with examples and point out the difference. A short version then goes into the word breakdown column.
