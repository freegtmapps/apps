# Battlecard

Positioning, weaknesses and objection handling against a named competitor.

| Skill | Author | Words |
|---|---|---|
| `competitor-intel` | Yoni Tserruya | 0.9k |
| `competitor-positioning` | Alon Goldenberg | 1.1k (+3 reference pages) |

## Two skills, not the three the catalogue lists

`APP-CATALOG` names `competitive-intelligence-radar` (Sabahudin Murtic) as a
third. **It is not here, and the reason is worth stating rather than hiding.**

It is not a research method — it is the documentation for a **separate Claude
Code plugin**: `/radar-setup`, `/radar`, `/radar-council`, needing a BrightData
API token, a Notion connection, and Claude Code's experimental agent-teams.
Vendored into this bundle, a model would read a description of a toolchain it
cannot invoke and **improvise in the voice of it** — citing a dossier it never
gathered, from a weekly run that never happened.

The `validate` host-bound check flagged it (8 backticked `radar-*` identifiers
this server provides none of) and told us to read the skill before acting,
because that check has produced false positives before. We read it. This one is
real.

Nothing is wrong with his work — it is a good plugin, and it lives at
[competitive-intelligence-radar](https://github.com/sabahudin-web/competitive-intelligence-radar).
It is simply not a thing this app can carry.

## Read-only, and that is the interesting field on the manifest

A battlecard is a claim about **somebody else's** product, and the one thing it
must never do is write that claim onto a lead's record as though it were a fact
about the lead. `may: [read]`. Nothing stages, nothing writes.

`web` is required rather than optional: a battlecard assembled without reading
anything current is a battlecard about last year's competitor, which is the
failure this app exists to prevent.

MIT.
