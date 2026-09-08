# vendor/

Upstream's bytes, exactly as upstream wrote them, at the commit each skill names.

Nothing here is loaded, installed, or composed. It exists so that one question —
**is this vendored skill still the text its author wrote?** — can be answered
from files on disk instead of from the internet.

## Why the app copies are not enough

An app's `SKILL.md` is not a copy of upstream's file. Vendoring rewrites the
frontmatter into our vocabulary: upstream carries `title` and `category`, ours
carries `author`, `source`, `license` and `adapted`. That is deliberate — a
whole-file comparison would call every honestly vendored skill "adapted", which
is a check that fails on its first real input in the direction of accusing
people.

So `adapted: false` is a claim about the **body**, and until this directory
existed the only way to check it was to fetch the source at publish time.

## What it does not protect against

The frontmatter, which is where our own tooling has done its damage: 116
descriptions truncated to roughly 256 characters, and nine files left carrying
YAML that no spec-compliant parser accepts. `skills.lock` pins the content of
what we ship; this pins what we were given. They answer different questions and
you want both.

## Regenerating

    go run ./cmd/vendorfetch ../apps/apps ../apps/vendor          # fetch what is missing
    go run ./cmd/vendorfetch -check ../apps/apps ../apps/vendor   # compare, no network

Files are keyed `skills/<org>/<repo>/<skill>/` — org and repo included because a
skill name is not an address. `deal-qualification-gates` is vendored from two
different upstreams at different commits with different content, and so is
`icp-score-and-route`.

An existing file is never refetched: a pin that could change under you is not a
pin. Delete it to re-fetch it.
