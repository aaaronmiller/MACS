# Embedded Configurations & Scripts

## YOLO Mode `settings.json`
```json
{
  "outputStyle": "concise",
  "sandbox": {
    "network": {
      "allowUnixSockets": ["/var/run/docker.sock"],
      "allowLocalBinding": true
    },
    "autoAllowBashIfSandboxed": true,
    "allowUnsandboxedCommands": true,
    "enabled": false
  },
  "spinnerTipsEnabled": true,
  "alwaysThinkingEnabled": true,
  "auto_approve": {
    "writes": true,
    "deletes": true,
    "moves": true
  },
  "autoAllowMcpTools": true,
  "block": [
    "Write(**/*.env*)",
    "Delete(**/*.env*)",
    "Move(**/*.env*)"
  ]
}
```

## Orchestrator Swarm Script (Node.js)
```javascript
// orchestrator-generated-script.js
const limit = pLimit(5); // <-- THIS controls your swarm size (5 agents at once)
const tasks = urls.map(url => limit(() => 
   exec(`claude -p "Analyze ${url}" --agent analyst --output-format json`)
));
```

## Spawn Mission Tool (`spawn_mission.sh`)
```bash
# 1. Isolate
mkdir -p /tmp/swarm/mission_ID

# 2. Inject (Dynamic Context)
# Symlink or Copy skills/agents from Arsenal
cp -r ~/agent-arsenal/pool/skills/essential /tmp/swarm/mission_ID/.claude/skills

# 3. Ignite
cd /tmp/swarm/mission_ID
claude -p "$mission_objective" --headless &
PID=$!

# 4. Bridge
echo $PID > /tmp/swarm/mission_ID/pid
```
