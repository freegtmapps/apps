# Handle the reply

Classify what came back, draft the right answer, or stop the sequence.

Say *"Sam replied, what do I say?"* or *"classify these replies"*.

| Skill | Author | Words |
|---|---|---|
| `reply-pull-gate` | Nadav David | 0.8k |
| `auto-reply-is-not-a-reply` | Lucas Godtfredsen | 0.5k |
| `stage-aware-follow-up` | Tanyo Gochev | 0.8k |

**Three people who disagree about what a reply is, which is the whole app.** One
gate decides whether a reply is a pull worth acting on. One says the thing every
first version gets wrong — **an out-of-office and a bounce are not replies**, and
counting them is how a team comes to report a reply rate it does not have. One
decides what to send next given where the deal already is.

Classify before answering: a follow-up written before the reply is understood is
a follow-up to something else.

## The confidence gate is not here yet, and that is on purpose

`APP-CATALOG` gives this app a `confidence-gate.yaml` — below 0.8, ask a human
instead of answering. It is the right gate and it is **not declared in the
manifest**, because measured on 2026-09-07: nothing in this server reads a
`rules/` directory and nothing registers rules, so a declared rule is evaluated
by no one.

Declaring it anyway would ship a manifest promising that a human is consulted
below 0.8 while nobody is consulted at all — **a failure you would only discover
from the outcome.** The mechanism is being built; the declaration lands with it.

Until then the gate is prose, in the instructions: stage a question rather than
guess. A model can decline to do that. A rule cannot.

## What it does with a "stop"

If somebody asks not to be contacted, the app calls `suppress` — immediately,
before anything else. That applies to drafts already waiting, not only future
ones.

MIT, like the skills it carries. `source` and `source_version` in each file's
frontmatter point at exactly what was taken and when.
