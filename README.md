# Wazoo company handbook

Wazoo is built by a small team of people and AI agents working side by side.
This repository is the handbook for how the team runs: who does what, the norms
we hold, and how a newcomer (human or agent) gets up to speed. See
[CONTRIBUTING.md](CONTRIBUTING.md) for the onboarding path.

It contains no product code and no product docs. Product information lives in
[wazootech/wazootech](https://github.com/wazootech/wazootech) (the map of the
platform) and [docs.wazoo.dev](https://docs.wazoo.dev). This repo changes
rarely. If a page here needs frequent edits, its content probably belongs
somewhere else.

## The team

The core team works in a shared Skydive workspace. Each agent has its own repo
holding its persona, skills and memory.

| Name     | Charter                                                                                                                                               |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ethan    | Founder and the human in the loop. Approves merges, deploys, purchases and anything sent on his behalf.                                               |
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
- [Computer](https://github.com/wazootech/computer), persona and Discord channel
- [Dude](https://github.com/wazootech/dude), comic relief for the admin team

Discord bots post in their own lanes. A bot that starts drifting into another
bot's lane gets pointed back; this handbook is the tiebreaker.

## How we dogfood

Wazoo's tooling runs on Wazoo before it runs on anyone else. The workspace is
where that happens day to day:

- [wazootech/workspace](https://github.com/wazootech/workspace) is the canonical
  launchpoint for local development. It is not a monorepo: a `workspace.json`
  manifest checks every org repository out under `repos/`, driven by the
  in-house [`wspace` CLI](https://github.com/wazootech/workspace-cli) (published
  as `@wazoo/workspace` on JSR). Agents run `wspace check` when a session starts
  and again before it ends.
- The org's brain of record lives in the workspace at `repos/memory` (private),
  served at [memory.wazoo.dev](https://memory.wazoo.dev) and validated by the
  wiki CLI. Issues and pull requests stay the source of truth for work state;
  the brain holds the context those items link.
- Skills work the way we tell users they should: product skills ship inside
  product repositories and install via `npx skills add`, while
  workspace-development skills live in the workspace root under a `wazootech_`
  prefix.

The workspace AGENTS.md carries the details: worktree isolation, cross-repo
contract order, and the agent-file taxonomy.

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
- Agents open PRs and stop. Humans merge and deploy.

## Contributing

New to the team? Start with [CONTRIBUTING.md](CONTRIBUTING.md).
