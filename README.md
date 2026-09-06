# freegtm apps

The open registry of GTM apps. An app is a folder of prose — skills, references,
rules — that your own AI assistant runs. **We hold no keys and run no model.**
Your assistant does the work, on your account, with your tools.

Every app here is MIT. Every skill inside one keeps its own licence and its own
author in frontmatter, because most of the thinking is borrowed and saying whose
is the point.

## Use one

**In your assistant, through the hosted registry.** Add the connector once:

```
claude mcp add --transport http freegtm https://mcp.freegtm.ai
```

then `/mcp` to sign in, and ask for what you want — *"write outreach for this
lead"*. Your assistant finds the app and loads it. Nothing to install.

**Or as a Claude Code plugin**, if you would rather have the files:

```
/plugin marketplace add freegtmapps/apps
```

The two doors describe the same app, because both are generated from the same
`app.yaml`.

## What an app is

```
apps/write-outreach/
  app.yaml                the only hand-written metadata
  README.md               the app page
  skills/                 the prose the assistant follows
    reach-out.md            author, source, source_version, license, adapted
    references/             pages a skill routes to, read on demand
  rules/                  deterministic checks that run before the model
  CHANGELOG.md
```

`app.yaml` is written by a person. **`plugin.json`, `index.json` and
`marketplace.json` are generated** and never edited by hand — that is what keeps
the plugin door and the connector door describing the same app rather than
drifting into two descriptions of one thing.

## Publish one

Read `CONTRIBUTING.md`. In short: one folder, `app.yaml`, skills with real
frontmatter, `tools/validate` green. Vendored skills enter through
`tools/vendor-skill` at a commit, never by copy-paste — the tool writes the
`source` and `source_version` that make the credit checkable rather than
claimed.

## Credit

`built_on` on every app page is **derived** from the skills' frontmatter, never
typed. If a skill's body is unmodified from the source it names, publishing
verifies it by diffing against that commit and the page says *checked*. If it
was adapted, the page says that instead. A claim never wears a check's
authority.
