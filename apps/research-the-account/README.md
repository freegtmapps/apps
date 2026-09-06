# Research the account

One brief — who they are, what they sell, what changed, and who runs it.

Say *"research acme.com"*, *"brief me on Acme before my 2pm"*, or *"what should
I know about Notion?"* to your assistant.

## What it is made of

| Skill | Author | Words | What it contributes |
|---|---|---|---|
| `account-intelligence` | Yoni Tserruya | 1.2k | The gather: firmographics, buying signals, named contacts, recent news, ranked next actions |
| `recent-discourse-sweep` | Nadav David | 0.8k | What has actually been said lately, with a coverage report and a query plan as reference pages |
| `account-research-brief` | Amir Baldiga | 0.5k | The compression: what a person can read in the two minutes before a call |

**None of this thinking is ours.** freegtm composed the three; `built_on` names
Yoni Tserruya, Amir Baldiga and Nadav David, and every body is vendored
byte-identical from [gtm-skills](https://github.com/swan-gtm/gtm-skills) at
`7723903`, so `adapted: false` is a claim you can verify rather than a promise.

It replaces a five-line house skill that did this job by asserting it.

## Order

Gather → sweep → compress, and the order is the composition order. The brief is
written **last** because it is the only one of the three that has to decide what
to leave out, and it cannot do that before the other two have run.

## What it needs to reach

`web` is **required**, not optional. Every one of these three is a research
method, and a research app with nothing to read is not a degraded app — it is a
different one, and it should refuse rather than improvise.

Optional: `enrichment`, `linkedin`, `crm`, `github`. Say no once through
`set_reach` and it stops asking.

**On `enrichment`.** `account-intelligence`'s body says *"Requires a Lusha
connection"* — that is its author writing for his own stack, and we left his
words alone. The manifest declares the **capability**, `enrichment`, because a
bundle may not name a brand (APP-BUNDLE §5: *capabilities, never brands*). If
your assistant can reach some other enrichment source, the skill's method still
works; if it can reach none, you will be told once instead of on every run.

## What it writes

The brief goes onto the lead with `update_lead`. `may` is `read` and
`write_lead` — it drafts nothing and sends nothing.

`emits: [research.blocked]` is a declaration that is **inert here**. Signals are
the commercial product; the field stays so one bundle describes one app on both.

## Credit and licence

MIT, like the skills it carries. If one of these is yours and the credit is
wrong, or you would rather it were not vendored here, open an issue — the
`source` and `source_version` in each file's frontmatter point at exactly what
was taken and when.
