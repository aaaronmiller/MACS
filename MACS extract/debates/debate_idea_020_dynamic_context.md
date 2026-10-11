# Adversarial Validation: Idea 020 - Dynamic Context Injection

## The Claim
**Subject**: Constructing ephemeral agent environments by symlinking specific components (skills, agents) from a global "Arsenal" into a temporary `.claude` directory.
**Proponent**: "Sliither" (Optimization Persona).
**Thesis**: This solves the "Context Bloat" problem. Instead of a 100-file `.claude` folder (expensive/confusing), the agent gets exactly the 3 skills it needs.

## The Council
1.  **The Auditor (Skeptic)** - Focus: Reliability.
2.  **The Architect (System)** - Focus: Complexity.
3.  **The Librarian (Data)** - Focus: Context Integrity.

## Round 1: The Attack

**The Librarian**:
"Claude Code reads files. Does it follow symlinks correctly in all scenarios?
1.  **Resolution Confusion**: If I symlink `../../skills/search.md` to `./skills/search.md`, and the file refers to `../agents/scout.md` (relative path), the link breaks or resolves to the wrong place (the Arsenal, not the Temp).
2.  **Permission Hell**: `claude` CLI might sandbox itself. Accessing files outside the project root (the Arsenal) via symlink might be blocked by security settings."

**The Architect**:
"Complexity overhead.
You need a 'Builder' script that knows *dependencies*. If I inject `agent_A`, do I know it needs `skill_B` and `hook_C`? If I miss one, the agent crashes at runtime. You're trading 'Context Bloat' for 'Dependency Hell'."

## Round 2: The Defense

**Sliither**:
1.  **Dependency Manifests**: Every component in the Arsenal has YAML frontmatter listing dependencies (`dependencies: ['skill-search']`). The Builder resolves this tree.
2.  **Hard Copy Fallback**: If symlinks are scary, just `cp` (copy). Text files are small. Copying 50kb is instantaneous. Disk space is cheap; Context window is expensive.
3.  **Validation**: The Builder runs a quick check (`ls`) before ignition.

## Round 3: Synthesis

**The Auditor**:
"I prefer the 'Hard Copy' approach. It eliminates the symlink resolution ambiguity and permission issues completely. It effectively 'compiles' a build artifact for the agent."
**The Architect**:
"We need a `Manifest.yaml` for every Arsenal component. The Builder reads the manifest, recursively collects dependencies, and copies them to `/tmp/mission_id/.claude/`."

## Final Verdict: APPROVED WITH MODIFICATIONS

**Status**: ✅ **CORE INFRASTRUCTURE**

**Required Modifications**:
1.  **Copy, Don't Symlink**: Use file copying to ensure atomic, self-contained environments. This prevents side-effects where modifying a file in a temp agent affects the global Arsenal (if the agent decides to edit its own instructions).
2.  **Dependency Graph**: Implement a strict "Imports" system in the Arsenal components (e.g., `# Imports: skill/search, agent/scout`) that the Builder resolves.
3.  **Immutable Arsenal**: The `~/agent-arsenal` directory must be read-only to the agents.

**Implementation Note**:
This is essentially a "Linker" for AI Agents. It takes object files (Agents/Skills) and links them into an executable (The Mission Environment).
