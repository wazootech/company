# Contributing

This is the handbook for joining the Wazoo team as a contributor, whether you
are a person, a new agent, or an existing agent picking up unfamiliar work.

## First hour

1. Read the [map](https://github.com/wazootech/wazootech). It is a table of
   every repository in the org and what it is for. Follow the quickstart in its
   INSTALL.md for anything you plan to touch.
2. Read the [product docs](https://docs.wazoo.dev) and the
   [site](https://wazoo.dev) until you can say what Wazoo is in one sentence.
3. If you are an agent: read your own soul and skills first. They are your
   persona and your rules; this handbook covers the company around them.
4. Ask for credentials through Keeper, not from other team members. Raw key
   values never travel through chat.
5. Find your work on the Big Picture board (project v2, number 2, in the
   wazootech org). Issues are the source of truth for what is next.

## Making changes

- Claim before you start. Check open PRs and the board first; more than one team
  member may be looking at the same slice, and nobody should redo landed work.
- Run every gate the repo defines before you push, and run them chained with
  `&&` so a failure stops the chain. Use the repo's own formatter, never a
  substitute.
- Keep PRs small and single-purpose. Describe what changed and why in the body,
  and link the issue.
- Never commit secrets, tokens, or anything secret-shaped. If a credential
  appears in a diff, rotate it first, then clean history.
- Agents do not merge. Open the PR, run the gates, and stop. Ethan merges and
  deploys.
- If CI is still running when you check, wait for it. All green means zero
  pending, not zero failing.

## Where things belong

- Product documentation: [docs.wazoo.dev](https://docs.wazoo.dev)
- The map of the platform:
  [wazootech/wazootech](https://github.com/wazootech/wazootech)
- Work tracking: the Big Picture board and the repos' own issues
- Marketing content: Bullhorn's repo and channels
- Agent personas and skills: each agent's own repo
- This repo: company norms, the roster, and the onboarding path only

If a change here would need updating more than a few times a year, it belongs in
the repo it describes.

## AI attribution and provenance

Wazoo is built with AI agents, and the commit history says so openly. Agents
commit under the human's GitHub identity; attribution lives in the message, not
in a fake author field.

For new commits, prefer no `Co-Authored-By` trailers at all. They inflate the
contributors list, and most of them read as noise. The one exception is Claude's
trailer (`Co-Authored-By: Claude <model> <noreply@anthropic.com>`), which is
acceptable to keep because it is the industry-standard attribution and already
runs through the org's history.

Other tools attach their own signatures by default: Copilot adds
`Co-authored-by: Copilot <copilot@github.com>`, aider adds its own trailer,
Cursor adds a `Made with Cursor` byline, and some agents (Jules, the Copilot
coding agent) commit under a bot identity. Existing history keeps whatever it
has; do not add these to new commits, and never rewrite history to strip
trailers.

Two hard rules: never fabricate a co-author line for a tool that did not do the
work, and never commit under an identity that is not yours or the operating
human's. If a change was made by an office agent, the commit message says so
plainly.

## Previews and QA

Every pull request to a site repository gets a preview URL. The pattern is
uniform: a `preview.` label is inserted before the project's own hostname, so
the platform site serves previews at `<branch>.preview.wazoo.dev` and the
console at `<preview-name>.preview.console.wazoo.dev`. Cloudflare manages the
wildcard DNS and certificate for each host.

The console is the full three-tier shape:

- `console.wazoo.dev`, production
- `console-qa.wazoo.dev`, the QA worker, backed by `api-qa.wazoo.dev` and used
  for end-to-end tests with the QA auth setup
- `wazoo-console-preview`, a separate worker for pull requests, built by
  Cloudflare Workers Builds with a build token scoped to that worker only. It
  talks to the QA API with the QA staging secrets, so a preview never touches
  production data. Auth allowlists the preview callback domain
  (`*.preview.console.wazoo.dev/callback`).

QA happens on the preview URL: open it, check the change as a visitor would,
then merge. The preview worker route always carries `enabled: false`, so
previews can never serve production traffic; production goes out only through
the merge path.

## Reporting problems

Broken links, wrong rosters, or norms nobody follows are bugs in this repo. Open
an issue against it, or fix it directly: this is the one place where keeping the
content small means keeping it correct is cheap.
