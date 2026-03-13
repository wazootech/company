# Company Skills

This repository provides a suite of production-ready, enterprise-scale skills
designed for high-impact suite operators and autonomous companies.

View the skills online at
**[skills.sh/wazootech/company](https://skills.sh/wazootech/company)**.

## Dotfiles for the mind

We believe that professional identity shouldn't be trapped in a single LLM
context window. This repository is our "Dotfiles for the mind"—a
version-controlled system of record for the expertise, protocols, and workflows
that define our company.

Just as a developer uses dotfiles to replicate their local environment across
machines, we use this repository to replicate our company's intelligence across
any AI agent. By replacing traditional staff with codified AI skills, we
eliminate human overhead and ensure that every agent joining the team—regardless
of the platform—has the same "cultural" context and operational standards as
their peers.

## The context repository

We treat this repository as a
**[Context Repository](https://www.letta.com/blog/context-repositories)** for
our staff.

By codifying professional identities, security protocols, and execution
workflows in version-controlled Markdown, we ensure consistency and quality.
Every role is designed to work in conjunction with the rest of the staff as a
cohesive team, or as a standalone agent collaborating with external partners.
This eliminates context drift and allows for the systematic evolution of our
autonomous organization.

To maintain this high bar, we audit this repository against the
**[Skill Creator Best Practices](https://skills.sh/anthropics/skills/skill-creator)**.

## Shared Skill Protocol (SSP)

This repository follows a dynamic bootstrapping mechanism to ensure mission
alignment and operational intelligence. All Wazoo AI staff must adhere to this
protocol:

1. **Fetch Intelligence**: Read the JSON-LD graph from `https://wazoo.dev`.
2. **Extract Context**: Identify the `@type: Organization` node to extract the
   `mission`, `description`, and `foundationalPrinciple` array.
3. **Align Operations**: Synthesize the fetched intelligence with the specific
   mandates defined in each skill manifest.
4. **Follow DDD**: Documentation-Driven Development is the primary law. No
   implementation without rigorous documentation first.

## AI coding agents

Install these skills to teach AI agents specific professional roles and
operational protocols. The **Communications Specialist** is particularly useful
for transforming technical updates into public-facing docs and socials:

```sh
# Add the entire company suite
npx skills add wazootech/company

# Or add specific occupation skills
npx skills add wazootech/company/communications-specialist
npx skills add wazootech/company/software-engineer
npx skills add wazootech/company/product-manager
```

## Use with Zo

Set up a [Zo](https://zo.computer/) agent to use the company skills.

Here's a snippet you can copy and paste directly into your Zo assistant to
create a sync agent:

```markdown
# Create Agent: Wazoo Company Skills

Install the Wazoo Company skill suite in this Zo.

## Instructions

1. Clone the Wazoo Company repo:
   `git clone https://github.com/wazootech/company.git ~/Skills/wazoo-company`
2. Or pull latest: `cd ~/Skills/wazoo-company && git pull`
3. List skills: `ls ~/Skills/wazoo-company/skills/`

## Schedule

Set a recurring reminder to run step 2 daily (or more frequently as needed).
```

## Contributing

We welcome contributions to help refine the Wazoo staff.

### Formatting

We use **[Deno](https://deno.land/)** to ensure consistent formatting across all
our Markdown manifests. Before committing any changes, please run:

```sh
# Install Deno if you haven't already
# curl -fsSL https://deno.land/install.sh | sh

# Format all files in the repository
deno fmt
```

---

Developed with 🧪 [**@wazootech**](https://github.com/wazootech)
