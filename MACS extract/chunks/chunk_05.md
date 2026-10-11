# Chunk 5 Extraction: Layered Architecture & Proxy Routing
**Source**: `Chat with gemini 3 - MACS.md` (Lines 3201-4000)

## Ideas

### Idea 021: 3-Layer Fractal Architecture
**Type**: Architecture
**Description**: A formal definition of the "Fractal Swarm" system:
1. **Layer 1 (Prime + Council)**: Strategy Layer. Uses `BIG_MODEL`. Roles: Debate, Shard, Spawn using `spawn_mission.sh`.
2. **Layer 2 (Sub-Orchestrators)**: Tactical Layer. Uses `MIDDLE_MODEL`. Roles: Manage Loop, Monitor Swarm, Governor.
3. **Layer 3 (The Swarm)**: Execution Layer. Uses `SMALL_MODEL`. Roles: Scout, Analyst, Submitter (Stateless).
**Context**: Lines 3918-4000.

### Idea 022: Hybrid Proxy Routing
**Type**: Infrastructure
**Description**: The Claude Code Proxy (CCP) enables "Hybrid Mode", routing different tiers of agent intelligence to different providers simultaneously.
- `BIG_MODEL` -> Reasoning Models (O1, R1, Opus).
- `MIDDLE_MODEL` -> Workhorse (Sonnet 3.5, GPT-4o).
- `SMALL_MODEL` -> Speed/Free (Haiku, Gemini Flash).
**Context**: Lines 3321-3365.

### Idea 023: Shared Browser Context Optimization
**Type**: Tooling
**Description**: To prevent RAM explosion when running 50+ concurrent "Analyst" agents, the `playwright_mcp` tool should be configured to connect to a *shared* browser instance (via CDP) rather than spawning a fresh Chromium binary for every agent.
**Context**: Lines 3998-4000.

## Agent Commentary
The explicit mapping of "Model Tiers" to "Agent Layers" via the Proxy is the economic engine that makes this architecture viable. Without it, running a 50-agent swarm on Opus would bankrupt the user. With it (using Gemini Flash for Layer 3), it's cents on the dollar.

## Embedded Content
- CCP Hybrid Configuration Example (Lines 3345-3365).
- Layer 1 Definition (Lines 3918-3949).
- Layer 2 Definition (Lines 3952-3972).
- Layer 3 Definition (Lines 3975-4000).

## Checkpoint
- **Last Line Processed**: 4000
- **Next Step**: Continue reading from 4001 to End.
