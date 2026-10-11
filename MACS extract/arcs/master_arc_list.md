# Master Arc List: MACS & Fractal Swarms
**Source File**: `Chat with gemini 3 - MACS.md`

## Arc 1: Fractal Orchestration Architecture
**Description**: The core architectural paradigm shift from single-session agents to a recursive, multi-process swarm. This arc defines how to bypass "nesting" limits by treating the agent runtime as an OS binary.
**Key Concepts**:
- **Swarm Generator Pattern** (Idea 011): Writing scripts to spawn processes.
- **Fractal Council** (Idea 012): Recursive delegation layers (Prime -> Sub -> Worker).
- **3-Layer Architecture** (Idea 021): Strategic (Big) -> Tactical (Med) -> Execution (Small).
- **OS-Native Paradigm** (Idea 024): Moving logic from Python frameworks to the OS Shell.

## Arc 2: Infrastructure & Middleware
**Description**: The "plumbing" required to make the swarm viable, specifically focusing on cost, observability, and routing.
**Key Concepts**:
- **Claude Code Proxy (CCP)** (Idea 019): Routing model tiers to different providers (Optimization).
- **Super Agent Monitor (MACS)** (Idea 018): The control plane for headless sessions.
- **Hybrid Proxy Routing** (Idea 022): Simultaneously using O1 for thinking and Haiku for doing.
- **Shared Browser Context** (Idea 023): Preventing RAM exhaustion in large swarms.

## Arc 3: Dynamic Context Engineering
**Description**: Methods for managing the "Cognitive Load" of agents by dynamically constructing their environment rather than dumping everything into one context window.
**Key Concepts**:
- **Context-Injected Orchestration (CIO)** (Idea 003): Injecting state via file system.
- **Dynamic Context Injection** (Idea 020): Symlinking specific tools from an "Arsenal" to a temp dir.
- **God-Tool Protocol** (Idea 016): The specific mechanism (`spawn_mission`) for instantiation.
- **YOLO Mode** (Idea 009): Configuration for non-blocking autonomy.

## Arc 4: Evolutionary Optimization
**Description**: Systems for measuring, improving, and scaling the swarm's performance over time.
**Key Concepts**:
- **Agent Configuration Quantification** (Idea 007): Scoring agent quality (0-100).
- **Canary Autoscaling** (Idea 017): Algorithms for determining safe concurrency.
- **Hybrid Agent Synthesis** (Idea 008): Merging agent configs for evolutionary improvement.
- **Self-Healing DevOps** (Idea 026): Using the swarm to fix its own code.

## Critical Ideas for Adversarial Validation
1. **Idea 011: The Swarm Generator Pattern**
   - *Why*: It is the fundamental technical claim. If this doesn't work (e.g., if `claude` CLI blocks or cannot be scripted easily), the whole architecture collapses. Use the "Red Team" to try and break the script generation logic.
2. **Idea 020: Dynamic Context Injection (The Arsenal)**
   - *Why*: It is the solution to context bloat. We need to validate if symlinking `.claude` folders actually works as intended without permission/path errors or context leakage.
