# Template Vault

An opinionated starter vault for Obsidian that gives you a clean structure for capturing notes, reviewing them over time, and organizing them with folder-based workflows and Bases views.

## What This Project Does

This repository is a ready-to-use Obsidian vault template. It combines:

- capture areas for ideas, projects, references, clippings, and periodic notes
- starter documentation for learning Obsidian in the Sandbox area
- prebuilt `.base` files in [Bases](Bases) for database-like views over your notes

Use it as a personal knowledge base, journal, project hub, or as a starting point for your own vault conventions.

## Why This Project Is Useful

- Starts simple: the top-level folders already separate short-lived notes, long-term references, and planning cycles.
- Encourages consistent organization: Daily, Weekly, and Monthly folders make recurring review habits easier to maintain.
- Supports structured note collections: the `.base` files cover common domains such as books, people, places, projects, trips, and ratings.
- Includes onboarding material: the Sandbox area helps new Obsidian users learn links, formatting, and basic workflows.
- Stays local-first: content is stored as Markdown files, so your notes remain portable and easy to version with Git.

## Vault Layout

| Path | Purpose |
| --- | --- |
| [Daily](Daily) | Daily notes and journal-style capture |
| [Weekly](Weekly) | Weekly planning and review notes |
| [Monthly](Monthly) | Monthly planning and review notes |
| [Projects](Projects) | Active project notes |
| [Ideas](Ideas) | Early-stage thoughts and future work |
| [References](References) | Evergreen reference material |
| [Clippings](Clippings) | Saved excerpts and source material |
| [Meta](Meta) | Vault-level notes about process, systems, and maintenance |
| [Bases](Bases) | Predefined Obsidian Bases definitions (`*.base`) |
| [Sandbox](Sandbox) | Obsidian onboarding guides and formatting examples |
| [Canvases](Canvases) | Visual canvases and whiteboard-style work |

## Get Started

### 1. Clone or download the vault

```bash
git clone https://github.com/masuda-so/Template-Vault.git
```

Or download the repository as a ZIP and extract it locally.

### 2. Open the folder in Obsidian

1. Install [Obsidian](https://obsidian.md/).
2. Choose Open folder as vault.
3. Select this repository folder.

### 3. Start with the built-in onboarding notes

- Read [ようこそ.md](ようこそ.md) for the default welcome note.
- Open [Sandbox/Start here.md](Sandbox/Start%20here.md) for a guided introduction.
- Continue with [Sandbox/Guides/Get started with Obsidian.md](Sandbox/Guides/Get%20started%20with%20Obsidian.md).

### 4. Begin using the folder structure

A practical starting workflow:

1. Capture quick thoughts in [Ideas](Ideas).
2. Move actionable work into [Projects](Projects).
3. Keep source material in [References](References) or [Clippings](Clippings).
4. Review open work in [Weekly](Weekly) and [Monthly](Monthly).

### 5. Explore Bases views

The [Bases](Bases) directory contains `.base` files for common collections such as books, music, people, places, projects, recipes, shows, and trips. Open them in Obsidian with the Bases feature enabled to browse related notes as tables or cards.

## Usage Examples

Create a project note in [Projects](Projects) with properties that work well with Bases and Obsidian search:

```md
---
type: project
status: active
review: 2026-03-31
tags:
	- work
	- writing
---

# Redesign README

## Next actions
- Draft the root README
- Review folder naming

## Related notes
- [[Ideas/README]]
- [[References/README]]
```

Create a lightweight idea note in [Ideas](Ideas):

```md
---
type: idea
created: 2026-03-31
---

# Weekly review template

Turn the weekly folder into a repeatable review workflow with prompts for wins, blockers, and next actions.
```

## Where To Get Help

- Start with the onboarding notes in [Sandbox](Sandbox).
- Check the official Obsidian help site: https://help.obsidian.md/
- Review formatting examples such as [Sandbox/Formatting/Format your notes.md](Sandbox/Formatting/Format%20your%20notes.md).
- If you find an issue in this repository, open an issue at https://github.com/masuda-so/Template-Vault/issues

## Maintainers And Contributing

This repository is maintained by Masuda So on GitHub as `masuda-so`.

Contributions are welcome, especially when they improve the default vault structure, note templates, onboarding flow, or Bases definitions.

To contribute:

1. Fork the repository.
2. Create a focused branch for your change.
3. Update or add notes with clear, minimal structure.
4. Open a pull request describing the workflow improvement.

If you plan to make a larger structural change, open an issue first so the folder layout and naming conventions can be discussed before implementation.

## Third-Party Notices

This repository includes content derived from kepano/obsidian-skills.
The required copyright notice and permission notice are provided in
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md), and must be included in all
copies or substantial portions of the relevant content.
