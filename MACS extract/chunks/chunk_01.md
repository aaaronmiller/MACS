# Chunk 1 Extraction: MACS Architecture & Claude Code Basics
**Source**: `Chat with gemini 3 - MACS.md` (Lines 1-800)

## Ideas

### Idea 001: Synthetic Cortex Architecture
**Type**: Architecture
**Description**: A macro-cognitive architecture that conceptualizes an AI agent system as an OS-native, recursive biological organism ("Synthetic Cortex"). It moves beyond simple abstraction layers to a homeostatic system.
**Context**: Introduction (Lines 10-28).
**Verification**: Critical. Needs validation of the "biological/metabolic" analogy's practical utility vs. just metaphor.

### Idea 002: Semantic Mixture of Experts (SMoE) & Global Workspace
**Type**: Pattern
**Description**: Implementation of SMoE leveraging massive-context models as a conscious "Global Workspace" for adversarial collaboration. Based on Global Workspace Theory and IFS (Internal Family Systems).
**Context**: Lines 30-43.
**Verification**: High. Test if "adversarial collaboration" in a single context actually yields better results than separate contexts.

### Idea 003: Context-Injected Orchestration (CIO) Pattern
**Type**: Methodology
**Description**: A headless agentic architecture separating **Capability** (Static, pre-provisioned in `.claude/` templates) from **Intent** (Dynamic, runtime prompt). The "Solution" is the environment; the "Action" is the user prompt.
**Context**: Lines 59-78.
**Verification**: Critical. This is the core execution logic proposed.

### Idea 004: Agent "Arsenal" & Factory Pattern
**Type**: Implementation
**Description**: A "Factory Script" (`deploy-agent.sh`) that dynamically spins up ephemeral sessions by copying templates from an `~/agent-arsenal/` directory (Coder, Writer, Auditor) into a temp folder, injecting the user prompt.
**Context**: Lines 78-92.
**Related Checkpoints**: `CIO Pattern`.

### Idea 005: Claude Code Subagent Architecture
**Type**: Tool_Documentation
**Description**: Detailed taxonomy of Claude Code's subagent capabilities: Isolated context, YAML configuration, inability to spawn nested subagents, and Model Context Protocol (MCP) inheritance.
**Context**: Lines 119-291.
**Status**: Reference Material (High utility for implementation).

### Idea 006: Project Folder Architecture Standard
**Type**: Standard
**Description**: A comprehensive directory structure for agentic projects:
- `CLAUDE.md`: Project memory.
- `.claude/settings.json`: Config.
- `.claude/agents/*.md`: Subagent definitions.
- `.claude/skills/*/SKILL.md`: Modular knowledge packages.
- `.claude/commands/*.md`: Slash commands.
**Context**: Lines 361-564.
**Verification**: High. Validate if this structure is supported natively or requires custom tooling.

## Agent Commentary
The text transitions significantly from high-level theoretical "Synthetic Cortex" constructs to extremely granular, almost copy-pasted documentation for "Claude Code" (Anthropic's CLI tool). The "CIO Pattern" (Idea 003) is the bridge: using the specific features of Claude Code (headless mode, workspace isolation) to implement the "Cortex".

The concept of "Metabolic Constraints" (Idea 001) is mentioned but not detailed in this chunk—likely appears later. The "Factory" pattern (Idea 004) is a very practical DevOps approach to agent management.

## Embedded Content
- `deploy-agent.sh` logic (Lines 81-85).
- Directory Structure Tree (Lines 363-392).
- Example `CLAUDE.md` and `settings.json` (Lines 406-471).

## Checkpoint
- **Last Line Processed**: 800
- **Next Step**: Continue reading from 801.
