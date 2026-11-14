# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this workspace is

This file lives in the `Concept` repo but describes the whole Swiss DePa workspace. In a multi-repo session it is copied to the parent directory; keep both copies identical.

The working directory holds seven separate git repositories (each its own clone with its own `origin`) belonging to the **Swiss DePa** (Swiss Decentralized Party) project, plus `DAOmanagement` from a personal account. The goal of the project is to turn a Swiss political party into a DAO (Decentralized Autonomous Organization) on [Soonaverse](https://soonaverse.com/space/0xfb239ac24ef62fcf7093a455c531ecd038cac412/overview), with decisions taken by proposals and liquid-democracy voting instead of a classic Verein with a Vorstand.

**There is no code yet.** Every repository contains only Markdown planning documents, most of them stubs or headings without body text. There is nothing to build, lint or test; work here means writing and structuring concept documents.

| Directory | GitHub repo | Content |
|---|---|---|
| `Concept/` | Swiss-DePa/Concept | The core concept (`README.md`): what Swiss DePa is, current build-up phase (Landing Area, Working Groups), liquid democracy (diagrams in `images/`), reputation system, split rules, DAO vs. Verein/demonstration. `Kategorien.md`: criteria catalogue (Level 1 = Kriterium, Level 2 = Sub-Kriterium) for voting, identity, roles, representatives, initiatives. Also holds this `CLAUDE.md`. |
| `DAOmanagement/` | petter1/DAOmanagement | How the DAO is run: constitution, task/goal tracking (via GitHub), member onboarding (Discord intro + Soonaverse join request → Soonaverse role), proposal voting options (Yes / minor change / major change / discard), TangleHub for decentralized data storage, community token / NFT ideas. |
| `Identity-Verification/` | Swiss-DePa/Identity-Verification | Placeholders for IOTA DID integration and a tag system. |
| `Puplic-Relation/` | Swiss-DePa/Puplic-Relation | Website requirements (domain, content, links) and social-media responsibilities. All stubs. |
| `technical-system/` | Swiss-DePa/technical-system | `Subnet Governance Network.md`: English concept paper (draft v0.6) for a feeless network of sovereign subnets with cluster governance, ZK identity and multi-option voting. Its section 12 maps the idea onto Swiss democracy. |
| `dao/`, `party/` | Swiss-DePa/… | Only a title README. |

## Conventions

- Documents are written primarily in **German** (Swiss spelling: "ss" instead of "ß"); the Concept intro is bilingual DE/EN and `DAOmanagement` is in English. Keep the language a document already uses.
- `Puplic-Relation` is the actual repository name. Do not "correct" the spelling in paths, links or remotes.
- File names may contain spaces (`Social Media.md`, `IOTA DID Integration.md`, `Tag System.md`); quote paths in shell commands.
- History so far consists of small commits made through the GitHub web UI on `main`. Each repo has its own branch to work on; commit and push per repository (`git -C <dir> ...`), since the parent directory is not itself a git repo.
- **At the end of every session, `CLAUDE.md` must be brought to `main` of `Swiss-DePa/Concept`** (this is explicit permission to push this one file directly to `main`). Commit only `CLAUDE.md` there; other changes stay on the session branch and go through a PR.
- The repos replace the former shared OneNote notebook «Swiss Decentralized Party». Its content (Liquid-Democracy diagrams, Kategorien) has been moved to `Concept/`; new content goes into the repos, not OneNote.
- Technology referenced in the docs: Soonaverse (DAO platform), IOTA / Tangle (DID identity, TangleHub storage), Discord (community entry point).
