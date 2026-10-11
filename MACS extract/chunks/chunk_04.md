# Chunk 4 Extraction: Fractal Swarms & Infrastructure
**Source**: `Chat with gemini 3 - MACS.md` (Lines 2401-3200)

## Ideas

### Idea 016: "God-Tool" Protocol (spawn_orchestrator)
**Type**: Tooling
**Description**: A standardized tool definition used by the Prime Orchestrator to spawn sub-swarms.
**Mechanism**:
1. **Isolate**: Create temp dir `/tmp/swarm/mission_ID`.
2. **Inject**: Symlink specific skills/agents from `~/agent-arsenal/pool/` (Dynamic Context Injection).
3. **Ignite**: Exec `claude -p "objective" --headless`.
4. **Bridge**: Stream output back to parent.
**Context**: Lines 2444-2472.

### Idea 017: Canary Autoscaling Algorithm
**Type**: Algorithm
**Description**: A safe-ramp algorithm for determining optimal swarm concurrency.
- **Start**: 2 agents.
- **Loop**: Check health.
- **Success**: Double count.
- **Failure (429/Timeout)**: Halve count & wait.
**Context**: Lines 2533-2545.

### Idea 018: Super Agent Monitor (MACS)
**Type**: Infrastructure
**Description**: A comprehensive web-based platform (Node/Vue/PGVector) for managing headless `claude` sessions. Features include RAG memory, stall detection (watchdog), cost tracking, and real-time visualization. It acts as the "Control Plane" for the swarm.
**Context**: Lines 2603-3009.

### Idea 019: Claude Code Proxy (CCP)
**Type**: Infrastructure
**Description**: A middleware that creates a "Hybrid Model" environment for Claude Code. It intercepts API calls and routes them to different providers (OpenRouter, Gemini, Ollama) based on the "tier" (Big/Medium/Small). This enables massive cost savings and access to "Reasoning Models" (O1/R1) within the customized agent flow.
**Context**: Lines 3013-3200.

### Idea 020: Dynamic Context Injection
**Type**: Architecture
**Description**: Instead of monolithic `.claude` folders, the system maintains a `~/agent-arsenal/pool` of granular components (skills, agents, hooks). The Orchestrator dynamically assembles a custom `.claude` environment for each task by symlinking only the necessary components, keeping the context window clean/efficient.
**Context**: Lines 2425-2442.

## Agent Commentary
The introduction of MACS and CCP completes the ecosystem.
- **Orchestrator**: The Brain (Logic)
- **Swarm Generator**: The Arms (Execution)
- **MACS**: The Eyes (Monitoring/Memory)
- **CCP**: The Heart (Model Power/Cost Efficiency)

The "Dynamic Context Injection" is particularly potent; it solves the "Jack of all trades, master of none" problem by creating bespoke agent environments on the fly.

## Embedded Content
- `spawn_sub_orchestrator` Tool Def (Lines 2450-2460).
- Mermaid Graph of Fractal Swarm (Lines 2496-2525).
- MACS README (Lines 2603-3009).
- CCP README (Lines 3013-3200).

## Checkpoint
- **Last Line Processed**: 3200
- **Next Step**: Continue reading from 3201.
