# Super Agent Monitor (MACS) README
**Source**: `Chat with gemini 3 - MACS.md`

## Overview
Super Agent Monitor transforms Claude Code from a single-session tool into an intelligent orchestration platform capable of managing autonomous agent swarms with persistent memory and real-time monitoring.

## Features
- 🤖 Headless Execution
- 👁️ Real-Time Monitoring (WebSocket)
- 🧠 RAG Memory System (PGVector)
- 🔄 Stall Detection (Watchdog)
- 💰 Cost Tracking

## Architecture
- **Frontend**: Vue 3 + Tailwind + Pinia
- **Backend**: Bun + Express + TypeScript
- **Database**: PostgreSQL 14+ (pgvector)
- **Services**: SessionLauncher, SessionMonitor, MemoryIngestion

## Component System
- Agents (.md)
- Skills (.md)
- Hooks (.py, .sh)
- Scripts (.py)
- Orchestrators (.md)

[See full file content in original source lines 2603-3009]
