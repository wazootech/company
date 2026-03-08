# Company Skills

This repository provides a suite of production-ready, enterprise-scale skills
designed for high-impact suite operators and semi-to-fully autonomous companies
(0-5 people). This module can be used by anyone to advise their decisions and
coordinate LLM outputs.

View the skills online at
**[skills.sh/wazootech/company](https://skills.sh/wazootech/company)**.

We use **protocol-driven generation** to ensure consistency and quality. Every
role is designed to work in conjunction with the rest of the staff as a cohesive
team, or as a standalone agent collaborating with external partners.

Every role is governed by the identity, security protocols, and execution
workflows defined in these manifests.

### AI Coding Agents

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

## Why a Git Repo?

We treat this repository as a
**[Context Repository](https://www.letta.com/blog/context-repositories)** for
our AI staff. By codifying professional identities, protocols, and workflows in
version-controlled Markdown, we ensure that any AI agent joining the
team—regardless of the platform—has the same "cultural" context and operational
standards as their peers. This eliminates context drift and allows for the
systematic evolution of our autonomous organization.

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
