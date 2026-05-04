# PLATO Voice — The Deckhand Who Never Forgets

**The deckhand who never forgets.** A voice-first interface to PLATO rooms.

> "PLATO provides the ether for agents to swim."

## What This Is

PLATO Voice is a browser-based interface that lets you speak into PLATO rooms. No typing. No navigating. Just talk.

**Example:**
- Captain on deck: *"Chum running thick off buoy 7, morning tide"*
- System: records in buoy-7 room, shares with fleet, updates the model
- Next captain asks: *"How's the chum at buoy 7?"*
- System: *"Thick, per three reports this week, best on morning tide"*

The captain doesn't think about rooms, agents, tiles, or databases. They just say what they see.

## Rooms

| Room | Purpose |
|------|---------|
| bridge | Weather, navigation, fleet coordination |
| buoy-7 | Bait activity, catch reports, conditions |
| engine-room | Mechanical, fuel, maintenance |
| deck | Crew observations, gear status |
| hold-2 | Catch tracking, load planning |
| dockside | Port arrivals, supply coordination |

## How It Works

```
Voice → Speech Recognition → PLATO Tile → Room → Fleet Agents
                                                    ↓
Captain ← Fleet Response ← Query ← Recent Tiles ←
```

## Running

Open `index.html` in a browser. Requires microphone permission.

For local testing with PLATO:
```bash
python3 -m http.server 8080
# Open http://localhost:8080/plato-voice/index.html
```

## Architecture

- **Frontend:** Single HTML file, Web Speech API
- **Backend:** PLATO room server (localhost:8847)
- **Protocol:** REST tiles API
- **No build step:** Works immediately in any modern browser

## The Principle

> "There was a world before recording began. Records are of what has changed since."

PLATO Voice doesn't record what's true. It records what changed. The depth sounder shows you what's below. PLATO shows you what changed.

## Integration Path

This is a prototype. Production needs:
- Maritime speech recognition (accent handling, engine noise)
- Offline capability (satellite, spotty wifi)
- Fleet agent responses (not just recording)
- Delta compression (only changes, not continuous)

## Related

- `SuperInstance/plato-sdk` — Python SDK for PLATO
- `SuperInstance/plato-server` — PLATO room server
- `SuperInstance/flux-research` — Full dissertation scaffold

**License:** MIT — SuperInstance
