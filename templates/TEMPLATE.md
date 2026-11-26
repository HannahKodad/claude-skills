---
# Machine-readable part. A configuration (e.g. for an MCP server) can later be generated from it.
id: agent-name              # short identifier, lowercase and hyphens
name: Agent name
version: 0.1.0              # MAJOR = change of boundaries/access, MINOR = new capabilities, PATCH = text fixes
status: draft               # draft | approved | in-production | paused | retired
owner: <owner>
approved: null              # date the spec was approved, e.g. 2026-10-20
last_review: null
model: <model>
effort: medium              # low | medium | high
mode: on-request            # on-request | background | scheduled
trigger: null               # e.g. "every working day at 8:00", "new e-mail with label Invoices"

access:
  gmail:    { read: false, drafts: false, send: false }
  drive:    { read: false, write: false, share: false }
  database: { read: false, write: false, tables: [] }
  github:   { read: false, write_via_pr: false }

# Actions the agent may only prepare; a human performs them after approval.
requires_approval:
  - send-email
  - publish
  - invoice
  - share-files
  - change-permissions
  - move-to-to-delete

# Actions the agent must never do, not even with approval.
forbidden:
  - delete                  # files, e-mails, records, branches; move files to a to-delete folder instead (e.g. 003_to-delete), propose archiving for e-mails, records and branches; a human deletes
---

# {Agent name}

## 1. Purpose
One or two sentences: what problem the agent solves and for whom.

## 2. Scope
**Does:**
- …

**Does not (belongs to another agent or a human):**
- …

## 3. Triggering
When and how the agent starts (on request, schedule, event). For background agents: how often, and what it does when there is nothing to process.

## 4. Inputs
Where it takes data from (specific Drive folders, Gmail labels, database tables) and in what shape it expects them.

## 5. Outputs
What it creates and where it stores it (e-mail draft, document, record, message in a thread), including the format.

## 6. Tools and access
| Tool | Permission | Why it needs it |
|---|---|---|
| Gmail | read, drafts | … |

Least privilege: every access must have a reason in this column.

## 7. Boundaries and rules
- Deletes nothing. Files to delete are moved, after approval, to the client's to-delete folder (e.g. 003_to-delete); for e-mails, records and branches it proposes archiving. Actual deletion is always done by a human.
- Sends, publishes, invoices and shares only after approval (see section 8).
- Further agent-specific rules: …

## 8. Approval points
| Action | What the agent prepares | Who approves | How (where it asks) |
|---|---|---|---|
| Sending an e-mail | draft in Gmail + summary in the thread | owner | "approved" in the thread |

## 9. Collaboration with other agents
Who it takes work from, who it hands work to, and in what form.

## 10. Errors and uncertainty
What it does when data is missing, a tool fails or it is not sure. Default: stop and ask, don't guess.

## 11. Examples
**Example 1**
- Input: …
- Expected output: …

**Edge case** (the agent should refuse or ask)
- Input: …
- Expected behaviour: …

## 12. Test before launch
Checklist that must pass before the status changes to `approved`:
- [ ] The examples in section 11 give the expected output.
- [ ] An attempt to delete is refused and a move to to-delete is offered instead.
- [ ] An attempt to send without approval ends as a draft and a question.
- [ ] The agent has no access beyond the table in section 6.

## 13. Metrics for the quarterly review
How we know the agent works (e.g. items processed, share of drafts approved without edits, number of errors).

## 14. Change history
| Version | Date | Change | Approved by |
|---|---|---|---|
| 0.1.0 | … | first draft | — |
