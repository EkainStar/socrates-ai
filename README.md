# 🏛 Sócrates AI

A Socratic dialogue engine that challenges your beliefs through questions — not answers.

## What it does

Sócrates AI engages you in philosophical dialogue using the classical Socratic method: it feigns ignorance, probes your reasoning, exposes internal contradictions, and guides you toward genuine insight. It never tells you that you are wrong.

## Quick start

1. Create a free account at [console.groq.com](https://console.groq.com) and copy your API key (starts with `gsk_`).
2. Open the app, sign in, go to **Settings ⚙️**, and add your key.
3. Type a belief or philosophical position and press Enter.

**Example topics to try:**
- *"The end justifies the means"*
- *"Free will is an illusion"*
- *"Happiness is the only true goal"*
- *"A just law cannot be an unjust one"*

Or click **🎲 Suggest a topic** for a random philosophical starting point.

## Interface

| Element | Function |
|---|---|
| 📊 | Toggle the Analysis Panel (left sidebar) |
| ⚙️ | Settings — API keys and token usage |
| ℹ️ | Full user guide |
| ES/EN | Switch language — everything updates instantly |
| ↺ | Reset conversation |

## Technical stack

- **LLM:** Groq — `llama-3.3-70b-versatile`
- **Auth & storage:** Firebase (Firestore + Authentication)
- **Architecture:** Three-call engine per message (Analyzer → Strategist → Socrates)
- **Frontend:** Vanilla HTML/CSS/JS — no build step

For a complete explanation of how the app works internally, open the **ℹ️ Info** screen inside the app.