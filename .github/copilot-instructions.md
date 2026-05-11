# Copilot instructions for this repository

## Commands

- Validate catalog JSON syntax: `python3 -m json.tool jbang-catalog.json >/dev/null`
- Inspect catalog aliases locally: `jbang alias list -f jbang-catalog.json`
- Inspect catalog aliases as JSON: `jbang alias list -f jbang-catalog.json --format=json`
- Run the published Microsoft catalog listing: `jbang catalog list microsoft`
- Smoke-test one alias locally by using the catalog file and the alias name:
  - `jbang alias list -f jbang-catalog.json --format=json | jq '.[] | select(.name == "playwright")'`
  - For CLI-style aliases, run their help command against the published catalog, e.g. `jbang playwright@microsoft --help`

## Architecture

This is a static JBang catalog repository. The root `jbang-catalog.json` is the primary artifact; it defines user-facing JBang aliases under `aliases` and currently leaves `templates` present but empty.

Each alias maps a short name to a `script-ref`, which may be a remote JAR URL, Maven coordinate, or remote Java source file. Optional metadata such as `description`, `java`, and `java-options` controls how JBang presents and launches the alias. There is no application source tree or project build file; repository changes normally update the catalog data and the README examples together.

`README.md` is the consumer documentation for the catalog. Keep its project list, headings, and command examples synchronized with aliases in `jbang-catalog.json`, especially when adding, renaming, or removing aliases.

## Repository conventions

- Use lowercase kebab-case alias names, matching README examples such as `minecraft-server`, `appinsights-agent`, and `playwright`.
- Keep `jbang-catalog.json` formatted as two-space-indented JSON with stable top-level keys: `aliases` first and `templates` last.
- Treat alias `description` values as user-facing text shown by JBang; preserve intentional newlines, Markdown code spans, and command snippets.
- Put JVM launch options in the alias-level `java-options` array and Java runtime requirements in the alias-level `java` string.
- Do not convert all `script-ref` values to one style; this catalog intentionally supports URLs, Maven coordinates, and remote source references depending on the artifact.
- When adding an alias, update both `jbang-catalog.json` and the README section that explains how users run it.
