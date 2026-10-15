# Framelink docs

Public, user-facing documentation for Framelink, published by Mintlify from this repo. `docs.json` holds site config and navigation; each page is an `.mdx` file.

This repo is public, including branches and history. Don't document unannounced features here.

## Rules

- Run `npx mint validate` before committing. MDX parses `<anything>` as a JSX tag and `{anything}` as an expression, so keep them out of prose — code blocks are fine. Don't backslash-escape them: the `.md` twin agents read is the raw source, so the backslash ships. Use `YOUR-KEY`-style placeholders instead.
- Use Mintlify's built-in components (`Tabs`, `Accordion`, `Steps`, `CodeGroup`, `Prompt`), not custom React components. Built-ins render on the server, so hidden tab and accordion content stays in the HTML and the `.md` twin that agents read; custom components render client-side and vanish for agents.
- Write every setup path out in full under its own heading or tab. Never "use the picker above" — an agent reading the markdown has no picker.
- `npx mint dev` previews locally, but only renders HTML in the browser. `.md` twins, `llms.txt`, and `Accept: text/markdown` exist only on the deployed site.
