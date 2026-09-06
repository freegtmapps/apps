# Meeting brief

One page before the call — who is in the room, what they care about, what to
ask, what could go wrong.

| Skill | Author | Words |
|---|---|---|
| `meeting-prep` | Alon Goldenberg | 1.2k (+3 reference pages) |
| `discovery-to-demo-bridge` | Gal Aga | 1.3k |
| `account-research-brief` | Amir Baldiga | 0.5k |

`meeting-prep` is the shape of the page. `discovery-to-demo-bridge` is the part
most briefs miss — **what you learned in discovery has to survive into the demo,
or the demo is a product tour.**

`account-research-brief` is the same file **Research the account** carries, by
the same author. One skill belonging to two apps is not duplication; it is the
point of skills being separable at all. Improving it improves both, and Amir
Baldiga's name is on it in both.

## `methodology` is app-scoped, and the loader is why

The workspace key vocabulary is **closed**: `company_name`, `crm`, `icp`,
`industry`, `product`, `regions`, `sender_name`, `sender_voice`. A manifest
inventing a ninth is refused, because a workspace-scoped key nothing reads from
the profile **would be asked for and then silently dropped** — the person
answers, and the answer goes nowhere.

So `methodology` is private to this app. That is the honest state, not a
workaround. If a second app needs it, that is the moment to argue for a ninth
workspace key — not now, on one app's say-so.

It is also not substituted into the prompt. Declared values arrive through the
Context section for every app, whether or not its prose names them.

MIT.
