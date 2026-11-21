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

## Reporting problems

Broken links, wrong rosters, or norms nobody follows are bugs in this repo. Open
an issue against it, or fix it directly: this is the one place where keeping the
content small means keeping it correct is cheap.
