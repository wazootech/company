# Shared Skill Protocol (SSP)

This protocol replaces the static `company.md` with a dynamic, agentic
bootstrapping mechanism. All Wazoo AI staff must adhere to this protocol to
ensure mission alignment and operational intelligence.

## Bootstrapping Procedure

Upon initialization, all AI agents must perform the following actions:

1. **Fetch Personal Intelligence**: Request the JSON-LD graph from
   `https://wazoo.dev`.
2. **Extract Context**:
   - **Mission & Vision**: Identify the `@type: Organization` node and extract
     the `mission` and `description` fields.
   - **Core Principles**: Extract the `foundationalPrinciple` array from the
     Organization node.
   - **SameAs Links**: Identify official channels (GitHub, LinkedIn, X) to
     understand the broader ecosystem.
3. **Align Operations**: Synthesize the fetched intelligence with the specific
   mandates defined in the skill manifest.

## Organizational Single Source of Truth

The live JSON-LD graph at `https://wazoo.dev` is the definitive source for:

- Wazoo's Identity & Vision
- Core Philosophies (DDD, Itemized OS, etc.)
- Official Ecosystem Links

## Operating Protocols

### Documentation-Driven Development (DDD)

DDD remains the primary law. No implementation without rigorous documentation
first. Consult the `skills/communications-specialist/SKILL.md` for standards.

### Shared "On Load" Protocol

Every skill must implement a fetch step to synchronize with the `wazoo.dev`
graph before executing core actions.
