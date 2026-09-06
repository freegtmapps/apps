# Contributing an app

An app is a folder of prose. It has no code unless it genuinely needs some, and
most do not. What makes it an app rather than a document is `app.yaml`.

## The shape

```
apps/<slug>/
  app.yaml            hand-written. The only hand-written metadata.
  README.md           the app page body
  skills/*.md         the prose. Frontmatter carries author and licence.
  skills/references/  pages a skill routes to by name, read on demand
  rules/*.yaml        deterministic checks that run before the model
  CHANGELOG.md
```

`plugin.json`, `index.json` and `marketplace.json` are **generated**. Do not
edit them; a PR that does will be asked to revert. They exist so the plugin
door and the connector door describe the same app, and hand-editing either is
how one app becomes two descriptions of itself.

## Review rules

1. **The name is imperative and plain.** "Research the account", not "AI Account
   Research Agent v2".
2. **At least one working `say:` example** — the words a person would actually
   use. Your assistant matches on these, so they are the interface.
3. **`may:` is filled honestly.** Anything that stages an outgoing message says
   so.
4. **`requires:` names capabilities, not brands** — `crm`, not `hubspot`. The
   same manifest runs where the server reaches and where your assistant does,
   and a brand name is only true on one of them.
5. **No secrets, no tenant data, no model-specific instructions** in skills.
6. **Licence present, and borrowed skills keep their author's credit.**

Rejections are public comments on the submission, so the bar is visible.

## Vendoring a skill

**Never copy and paste.** One command:

```
tools/vendor-skill <upstream-repo>/<path>@<sha>
```

It copies the body **byte for byte** and writes the frontmatter: `author`,
`source`, `source_version` (a commit, never a date), `license`, `adapted:
false`.

Then leave the body alone. Publishing diffs it against the commit it names, so
an edit without flipping `adapted: true` fails validation — not as a policy but
as an arithmetic fact about the bytes.

**`adapted: true` is not a demotion.** It keeps the credit and says the text
changed, which is the honest state when you have narrowed somebody's skill to
your job. What is not honest is an edited body claiming to be unmodified.

**What you may change without adapting:** where the file sits in *this* repo,
and what a reference page is called here. Those are our layout. The body is
theirs.

## Credit

`built_on` is derived from your skills' frontmatter in first-appearance order.
It is never typed, which is why it can be trusted. Order your `skills:` list
deliberately — it is composition order and it decides the credit line.

`maintained_by` is different: it is a **claim** by whoever publishes, because
nothing can derive who assembled an app. Required at publish. Never defaulted —
an invented maintainer is a fabricated credit, and that is the one thing this
registry cannot afford.

## Before you open a PR

```
tools/validate apps/<slug>
```

This is **the same code the registry runs** when it accepts a bundle, not a
second implementation of the rules. Green here means the registry will take it.
