# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this workspace is

This file lives in the `Concept` repo but describes the whole Swiss DePa workspace. In a multi-repo session it is copied to the parent directory; keep both copies identical.

The working directory holds separate git repositories (each its own clone with its own `origin`, no git repo at the parent level): five from the **Swiss DePa** (Swiss Decentralized Party) organisation, plus `DAOmanagement` and `IOTAstammtischSchweiz.github.io` from other accounts. The goal of the project is to run a Swiss political party as a DAO (Decentralized Autonomous Organization), with decisions taken by proposals and liquid-democracy voting instead of a Vorstand. A Verein is planned only as the legal shell (candidacies, initiatives, finances).

Decisions already taken (do not reopen without being asked):
- Voting logic: multi-option with Stichfrage as in `technical-system/Subnet Governance Network.md`, section 4.2.
- Legal form: Verein as legal shell, DAO for internal decisions.
- Soonaverse, the originally planned DAO platform, was shut down in 2024. Replacement: the DAO lives in the Git repo `Swiss-DePa/dao` (GitHub for the start, later a decentralised/self-hosted Git server), voting and member identity via an own voting app/service, and a KI-Sekretariat (AI agent without a vote) that works only through issues and PRs (`Concept/KI-Sekretariat.md`).

**Almost everything is Markdown.** The repos hold planning documents, many of them stubs or headings without body text; work here mostly means writing and structuring concept documents. The only code is the merge check in `dao/` (Python standard library, no dependencies, no test suite). Run it locally against a PR branch:

```sh
cd dao && PR_NUMBER=12 BASE_SHA=$(git rev-parse origin/main) PR_LABELS="" python3 scripts/pruefe_abstimmung.py
```

Exit code 0 = merge allowed, 1 = blocked; the reason is printed. `REPO_ROOT` defaults to the current directory.

| Directory | GitHub repo | Content |
|---|---|---|
| `Concept/` | Swiss-DePa/Concept | The core concept (`README.md`): what Swiss DePa is, current build-up phase (Landing Area, Working Groups), liquid democracy (diagrams in `images/`), reputation system, split rules, DAO vs. Verein/demonstration. `Kategorien.md`: criteria catalogue (Level 1 = Kriterium, Level 2 = Sub-Kriterium) for voting, identity, roles, representatives, initiatives. `Roadmap.md`: phases 0–5 with times relative to start (T0, "T+3 Monate"), deliberately no calendar dates. `KI-Sekretariat.md`: role and limits of the DAO's AI agent. Also holds this `CLAUDE.md`. |
| `DAOmanagement/` | petter1/DAOmanagement | How the DAO is run: constitution, task/goal tracking (via GitHub), member onboarding (Discord intro + Soonaverse join request → Soonaverse role), proposal voting options (now: multi-option with Stichfrage), TangleHub for decentralized data storage, community token / NFT ideas. |
| `Identity-Verification/` | Swiss-DePa/Identity-Verification | Placeholders for IOTA DID integration and a tag system. |
| `Puplic-Relation/` | Swiss-DePa/Puplic-Relation | Website requirements (domain, content, links) and social-media responsibilities. All stubs. |
| `technical-system/` | Swiss-DePa/technical-system | `Subnet Governance Network.md`: English concept paper (draft v0.6) for a feeless network of sovereign subnets with cluster governance, ZK identity and multi-option voting. Its section 12 maps the idea onto Swiss democracy. |
| `dao/` | Swiss-DePa/dao | The living DAO: `verfassung/Verfassung.md` (draft constitution, open values marked **[offen]**), `SEKRETARIAT.md` (operating instructions for the KI-Sekretariat, addressed to the agent, not to you), `abstimmungen/` (vote results `pr-<n>.json` written by the voting app), issue/PR templates, and the workflow «Abstimmung prüfen» which runs `scripts/pruefe_abstimmung.py` from the base branch via `pull_request_target` (so a PR cannot weaken its own check; only the JSON data comes from the PR). Merge is allowed if the constitution does not yet exist on the base branch (founding), the PR has label `aufbauphase` (Verfassung Art. 10), or `abstimmungen/pr-<n>.json` says `"ergebnis": "angenommen"`. Changing the check rules means changing the constitution and `abstimmungen/README.md` together. |
| `IOTAstammtischSchweiz.github.io/` | IOTAstammtischSchweiz/IOTAstammtischSchweiz.github.io | GitHub Pages site of the IOTA Stammtisch Schweiz: a single `index.html` with AddEvent calendar links. Not part of the party concept. |

`Swiss-DePa/party` (only a title README) exists on GitHub but is not cloned into these sessions.

## Conventions

- Documents are written primarily in **German** (Swiss spelling: "ss" instead of "ß"); the Concept intro is bilingual DE/EN and `DAOmanagement` is in English. Keep the language a document already uses.
- `Puplic-Relation` is the actual repository name. Do not "correct" the spelling in paths, links or remotes.
- File names may contain spaces (`Social Media.md`, `IOTA DID Integration.md`, `Tag System.md`); quote paths in shell commands.
- History so far consists of small commits made through the GitHub web UI on `main`. Claude may mark its own PRs ready and merge them (squash) unless a rule here forbids it. Each repo has its own branch to work on; commit and push per repository (`git -C <dir> ...`), since the parent directory is not itself a git repo.
- **At the end of every session, `CLAUDE.md` must be brought to `main` of `Swiss-DePa/Concept`** (this is explicit permission to push this one file directly to `main`). Commit only `CLAUDE.md` there; other changes stay on the session branch and go through a PR.
- The repos replace the former shared OneNote notebook «Swiss Decentralized Party». Its content (Liquid-Democracy diagrams, Kategorien) has been moved to `Concept/`; new content goes into the repos, not OneNote.
- Technology referenced in the docs: Soonaverse (former DAO platform, discontinued), IOTA / Tangle (DID identity, TangleHub storage), Discord (community entry point).
