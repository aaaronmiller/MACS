# Initial Thoughts for Item 1: MACS Deployment Method Definition

## Core Understanding from Document 1 Analysis

### Key Components Identified:

1. **CLAUDE.md (Root Identity)**
   - Must be at project root, NOT in `.claude/agents/`
   - Defines the Prime Orchestrator identity
   - Contains static behavioral constraints
   - Uses BIG_MODEL tier
   - CRITICAL: Cannot be a subagent - architectural constraint

2. **.claude/agents/ (Subagent Definitions)**
   - Stateless workers only
   - Receive payload → Execute → Return JSON → Terminate
   - Use SMALL_MODEL tier for efficiency
   - Three primary types documented: Scout, Mapper, Submitter
   - Must NOT have autonomy or awareness of larger system

3. **.claude/skills/ (Knowledge Modules)**
   - Procedural memory templates
   - Reusable knowledge without prompt repetition
   - Examples: dom.md, swarm_dispatch.md, adversarial_debate.md
   - Biomimetic function: "muscle memory"

4. **.claude/settings.json (Runtime Config)**
   - Tool permissions and MCP access
   - autoAllowMcpTools: true is CRUCIAL for headless execution
   - Proxy tier configuration for model swapping

5. **.claude/hooks/ (Autonomic Regulation)**
   - Bash/Python scripts for pre/post tool execution
   - Biomimetic: "Endocrine System"
   - Examples: budget_governor.js, post_error.sh, pre_spawn.sh
   - Automatic regulation without conscious orchestration

### Architectural Insights:

**The "One Swarm" Pattern:**
- Hub-and-spoke topology is essential
- Root orchestrator stays alive
- Subagents are ephemeral
- Leaves cannot branch (workers can't spawn workers)

**Dynamic Context Injection:**
- Resource pool approach vs static folders
- Symlink required skills/agents from pool to mission-specific directories
- Creates sandboxed, scoped environments
- Pattern: Isolate → Inject → Ignite

**File System as Shared Memory:**
- `/.claude/state/` - Mission state
- `/.claude/reports/` - Worker outputs
- `/.claude/logs/` - Execution history
- `/.claude/budget.json` - Resource constraints
- Provides persistence, concurrency, auditability

### Structure for Item 1:

1. **Introduction**
   - What is MACS deployment method
   - Why it differs from traditional agentic frameworks
   - Core principle: OS-native recursive architecture

2. **The .claude Folder Architecture**
   - Complete structural overview
   - Each component type with purpose and usage
   - File templates and examples

3. **Deployment Methodology**
   - Resource pool approach
   - Dynamic injection process
   - Headless execution pattern
   - Validation and troubleshooting

4. **Design Principles**
   - Stateless workers principle
   - Hub-and-spoke topology
   - Filesystem as nervous system
   - Model tier optimization

5. **Implementation Guide**
   - Step-by-step deployment checklist
   - Configuration examples
   - Common patterns and anti-patterns

## Questions to Address with Searches:

- What are other agentic deployment patterns? (LangChain, AutoGen, CrewAI)
- How do production systems typically handle agent orchestration?
- What are best practices for filesystem-based inter-process communication?
- Are there other OS-native agentic frameworks?
- What are MCP servers and their role in Claude ecosystem?

## Potential Issues to Resolve:

- Need to clarify "fin layers" concept (mentioned but never fully explained)
- Layer naming inconsistency (Council as Layer 1 vs Layer 2)
- Skill vs Agent boundary criteria needs explicit definition
- Need concrete examples of when to use each hook type

## Notes for Writing:

- Focus ONLY on subagent orchestration + subagent layer (NOT prime layer)
- Be technical and precise - this is a specification document
- Include file structure diagrams
- Provide code examples for each component type
- Create decision trees for implementation choices
- Keep biomimetic analogies but ground in technical reality
