# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Documentation site for the Nordic Financial News API, built on [Mintlify](https://mintlify.com). Pages are MDX files with YAML frontmatter. Configuration lives in `docs.json`. The API spec is in `openapi.yaml` (OpenAPI 3.0.1), and Mintlify auto-generates API reference pages from it.

The main Rails application lives at `~/code/nordic-news`. Its design system (`docs/design-system.md`) defines the visual tokens used across both the app and these docs.

## Common commands

- `mint dev` — preview locally at http://localhost:3000
- `mint broken-links` — check for broken links
- `mint update` — update the Mintlify CLI if dev isn't working
- Install CLI: `npm i -g mint`

## Architecture

The site has three navigation tabs configured in `docs.json`:

1. **Documentation** — `index.mdx`, `quickstart.mdx`, and `guides/*.mdx`
2. **API reference** — auto-generated from `openapi.yaml`, with `api-reference/introduction.mdx` as overview
3. **MCP Server** — `mcp-server/*.mdx`

API reference pages are defined by OpenAPI path strings in `docs.json` navigation (e.g., `"GET /api/v1/articles"`). Mintlify generates the actual pages from `openapi.yaml`.

## Style guide

- Active voice, second person ("you")
- One idea per sentence
- Sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- API example languages: bash, python, ruby, javascript (configured in `docs.json`)

## Branding

- Primary color: `#01B2FF`
- Default appearance: dark mode
- Theme: palm

## Mintlify documentation

### Working relationship

- You can push back on ideas-this can lead to better documentation. Cite sources and explain your reasoning when you do so
- ALWAYS ask for clarification rather than making assumptions
- NEVER lie, guess, or make up anything

### Project context

- Format: MDX files with YAML frontmatter
- Config: docs.json for navigation, theme, settings
- Components: Mintlify components

### Content strategy

- Document just enough for user success - not too much, not too little
- Prioritize accuracy and usability
- Make content evergreen when possible
- Search for existing content before adding anything new. Avoid duplication unless it is done for a strategic reason
- Check existing patterns for consistency
- Start by making the smallest reasonable changes

### docs.json

- Refer to the [docs.json schema](https://mintlify.com/docs.json) when building the docs.json file and site navigation

### Frontmatter requirements for pages

- title: Clear, descriptive page title
- description: Concise summary for SEO/navigation

### Writing standards

- Second-person voice ("you")
- Prerequisites at start of procedural content
- Test all code examples before publishing
- Match style and formatting of existing pages
- Include both basic and advanced use cases
- Language tags on all code blocks
- Alt text on all images
- Relative paths for internal links

### Git workflow

- NEVER use --no-verify when committing
- Ask how to handle uncommitted changes before starting
- Create a new branch when no clear branch exists for changes
- Commit frequently throughout development
- NEVER skip or disable pre-commit hooks

### Do not

- Skip frontmatter on any MDX file
- Use absolute URLs for internal links
- Include untested code examples
- Make assumptions - always ask for clarification
