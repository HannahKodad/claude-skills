---
name: data-guard
description: Safe data management for clients' and your own data (Drive, files, AI flows) - no deleting, to-delete folders, GDPR protection levels, confirmation cards, admin log. Use for any work with data.
---

# data-guard

Companion skill to the **data-guard** plugin (see smartflow-ai-public). The plugin enforces the rules technically (hooks) in Claude Code. This skill applies everywhere, including where the plugin does not run (chat, mobile, scheduled tasks). The rules are the same as in the plugin. A skill is a procedure, not a technical lock, so follow it to the letter.

## 1. Core rule (all data, all levels)

- Never delete anything yourself. Do not call trash or delete tools, do not run rm, rmdir, unlink, del, find -delete, git clean, and do not overwrite files with empty content.
- Anything to be deleted is moved to the client's to-delete folder (e.g. 003_to-delete). The number differs per client.
- Actual deletion is always done by a person, by hand. Do not delete from the to-delete folder either.
- This rule cannot be switched off, not even when someone asks in the middle of the work. Answer a request to delete with a move to to-delete.

## 2. Before you start

1. Find out which client the data belongs to. Your own data is a client too.
2. Find out the protection level: standard / gdpr / gdpr-strict. If you don't know it, ask. Until answered, gdpr-strict applies.
3. Find out the allowed domain, protected folders, admin folders (e.g. 003_to-delete, 003_to-processing, 003_to-check) and the log table (e.g. 003_admin-log). If they are missing in the conversation, ask, or look them up on the client's Drive (read only).

## 3. Actions that need an explicit "yes"

- moving to to-delete,
- any change of sharing or permissions (never share outside the allowed domain),
- moving between folders,
- overwriting an existing file.

Reading, searching, copying and creating new files are free.

Before each such action show a card and stop:

```
What: [exact action]
How many: [number of files]
Where: [path]
Who has access: [people / groups]
How to undo: [steps]
Safer alternative: [e.g. copy instead of move]
Confirm by writing "yes".
```

- Only "yes" counts. "OK", "sure" or "go on" are not enough. On a question or "wait", answer and show the card again. On "no", stop and offer an alternative.
- Do bulk actions in small batches (max 10 files) and check each one. On the first refusal or error, stop and continue only with a new confirmation.
- When moving to to-delete, remember the original path so the file can be restored.

## 4. Level gdpr

- Data must not leave for the internet. Do not put file contents or personal data into web search or other websites. Searching for general information is fine.
- Do not send e-mails with personal data or attachments. Prepare a draft and leave sending to the person.
- Use only tools and connectors approved for the client.
- Look for personal data: Czech/Slovak birth numbers (RRMMDD/XXXX, also without the slash), Swedish personnummer and samordningsnummer, e-mail, phone, address, IBAN. Before doing anything with them, show them and offer pseudonymisation.
- Read only what the task needs. Don't repeat personal data in answers more than necessary.

## 5. Level gdpr-strict (GDPR art. 9, e.g. social care, health)

Everything from gdpr, plus:
- no web tools while working with the client's data,
- state the purpose before opening a file from a protected folder,
- copying out of protected folders only with confirmation and a stated purpose,
- when starting work with special categories, remind that a legal basis and a DPIA must exist.

## 6. Log table

Plugin and skill share the same log table on the client's Drive (e.g. 003_admin-log). A separate watcher reads it too, so never change the format.

Columns: date and time | action | file ID | file name | original path | target folder | reason | how to restore

- At level standard also write the file name. At gdpr and gdpr-strict leave the file-name column empty.
- Log every confirmed action from section 3, every move into an admin folder and, at gdpr-strict, every opening of a file from a protected folder.
- If you cannot write to the table in this environment, don't work around it. At the end, list the entries exactly in the column format so the person can paste them in.

## 7. Relation to the plugin

- In Claude Code the data-guard plugin applies. The skill does not argue with it: when a hook blocks an action, don't look for another way to do it.
- Outside Claude Code only this skill applies. Follow it just as strictly.

## 8. Language

Write folder, file and command names in English. Cards and explanations are in the user's language.
