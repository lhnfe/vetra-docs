# Vetra documentation

The public documentation for the **Vetra** suite of Garry's Mod addons, published at
**<https://docs.vetrasuite.com>**.

It covers two audiences:

- **server owners** running or evaluating Vetra Blueprints;
- **developers** integrating their own addon through the Adapter SDK.

Built with [Mintlify](https://mintlify.com). Configuration lives in `docs.json`; pages are
MDX.

## Layout

```text
docs.json          navigation, theme, branding, redirects
index.mdx          the landing page
blueprints/        the product: install, workflow, integrations
sdk/               the Adapter SDK
support/           licensing, data, troubleshooting, availability
logo/              the Vetra mark, light and dark
favicon.svg
```

Navigation is three tabs: **Blueprints**, **Adapter SDK**, **Support**. The structure is built
for a suite rather than for one addon, so a second product slots in as another tab without
rearranging anything.

## Local preview

Install the CLI once:

```sh
npm install -g mint
```

Then, from the repository root:

```sh
mint dev
```

That serves the site locally and reloads as you edit.

## Validation

```sh
mint validate        # strict build validation; exits non-zero on warnings or errors
mint broken-links    # link checking
```

Run both before opening a pull request. `mint validate` is the one that must pass.

Other useful commands:

```sh
mint a11y            # accessibility checks
mint format          # format MDX files
mint --version
```

## Editing

1. Branch from `main`.
2. Edit the MDX. Add a page by creating the file **and** listing it in `docs.json`; a page
   that is not in the navigation is not published.
3. Run `mint validate` and `mint broken-links`.
4. Open a pull request.

### House style

- Second person, active voice. Say "you", not "the user".
- Sentence case headings.
- Every page carries a `title` and a `description` in its frontmatter. The description is the
  search and social summary, so write it as a sentence rather than a label.
- Backticks for file names, commands, paths, console commands and code references.
- Document **what is true now**. Planned behaviour is labelled as planned, or left out.
- No em dashes.

### Accuracy

Every Lua example in `sdk/` describes a real, public API. If you change one, check it against
the shipped implementation first. A plausible-looking signature that does not exist is worse
than no example.

The same applies to product claims: licensing terms, retention, supported object types and the
availability commitment are all statements Vetra is held to. Do not adjust one to resolve an
inconsistency; report the inconsistency.

## Branding

The palette, typography and mark come from the Vetra design system.

| | |
| --- | --- |
| Citron | `#c5e258` |
| Citron dim | `#8fa343` |
| Void | `#0b0a08` |
| Type | IBM Plex Sans Condensed, IBM Plex Sans |

Two rules carry over from the product: **zero radius**, and **no shadow, blur or glow**. Depth
comes from surface value, not from effects.

Do not introduce another logo, another accent colour, or another typeface.
