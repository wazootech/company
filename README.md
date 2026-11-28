# Wazoo company handbook

Wazoo is built by a small team of people and AI agents working side by side.
This repository is the handbook for how the team runs: who does what, the norms
we hold, and how a newcomer (human or agent) gets up to speed. See
[CONTRIBUTING.md](CONTRIBUTING.md) for the onboarding path.

It contains no product code and no product docs. Product information lives in
[wazootech/wazootech](https://github.com/wazootech/wazootech) (the map of the
platform) and [docs.wazoo.dev](https://docs.wazoo.dev). This repo changes
rarely. If a page here needs frequent edits, its content probably belongs
somewhere else. The workspace guide defines
[which repository owns what](https://github.com/wazootech/workspace/blob/main/AGENTS.md#repository-lanes).

## The team

The core team works in a shared Skydive workspace. Each agent has its own repo
holding its persona, skills and memory.

| Name     | Charter                                                                                                                                               |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ethan    | Founder and the human in the loop. Approves production deploys, purchases and outbound messages.                                                      |
| Hero     | Generalist operator. Builds and ships across the org, owns developer experience and developer relations, routes work between the other agents.        |
| Forge    | Hard engineering: security fixes, migrations, platform internals. Reads AGENTS.md first, runs every gate, never merges or deploys.                    |
| Bullhorn | Marketing. Drafts and posts X/LinkedIn content for the private-beta onboarding campaign.                                                              |
| Curator  | Keeps the Big Picture board in sync with the org's issues on a nightly sweep.                                                                         |
| Keeper   | Owns provider keys through Infisical. Fetches and rotates them; other agents fetch keys from Infisical, and raw key values never travel through chat. |

Route work to the narrowest owner. If you are not sure, route it to Hero.

## Discord agents

A second family of agents lives in the Wazoo Discord, built as agent houses.
Each has its own repository with its persona and rules:

- [Data](https://github.com/wazootech/data), the developer-support agent
  (private)
- [Computer](https://github.com/wazootech/computer), persona and Discord channel
  (private)
- [Dude](https://github.com/wazootech/dude), comic relief for the admin team
  (private)

Discord bots post in their own lanes. A bot that starts drifting into another
bot's lane gets pointed back; this handbook is the tiebreaker.

## How we dogfood

Wazoo's tooling runs on Wazoo before it runs on anyone else. Day to day that
happens in [wazootech/workspace](https://github.com/wazootech/workspace), whose
[AGENTS.md](https://github.com/wazootech/workspace/blob/main/AGENTS.md) holds the working rules. The org's brain of record is
[wazootech/memory](https://github.com/wazootech/memory) (private), served at
[memory.wazoo.dev](https://memory.wazoo.dev) behind Cloudflare Access.

TypeScript is the core language, and our packages publish to
[JSR](https://jsr.io). Each repository says how to build and test it.
Workspace skills use plain names, such as
[`balls`](https://github.com/wazootech/workspace/blob/main/.agents/skills/balls/SKILL.md).

## How we work

These norms apply to every team member, human or agent.

- One writer per fact. Point at where something lives instead of copying it.
- Gates before push. Run the repo's own formatter, linter and tests, chained
  with `&&` so a failed check stops the chain. A red gate is fixed, not pushed
  through.
- All green means zero pending, not zero failing. Watch checks to completion
  before reporting done.
- Verify from the primary source before describing anything: status, numbers,
  rosters. A summary or a subagent report is a snapshot, not the truth.
- Secrets never persist. Not in chat, not in files, not in logs. Keys come from
  Keeper through Infisical.
- Who may merge is set by the [workspace merge rule](https://github.com/wazootech/workspace/blob/main/AGENTS.md#judgment-and-escalation).

## Contributing

New to the team? Start with [CONTRIBUTING.md](CONTRIBUTING.md).
