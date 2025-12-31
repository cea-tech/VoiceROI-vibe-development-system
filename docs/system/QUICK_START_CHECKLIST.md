# VoiceROI Voice Agent – Quick Start Checklist

Use this when you’re ready to build the **voiceroi-voice-agent** repo with Claude Code.

---

## 0. Setup (you do this)

text
# VoiceROI Voice Agent – Quick Start Checklist

Use this when you’re ready to build the **voiceroi-voice-agent** repo with Claude Code.

---

## 0. Setup (you do this)

cd ~
mkdir -p voiceroi-voice-agent
cd voiceroi-voice-agent

mkdir -p src/agents src/rag src/config logs models/knowledge_base tests

touch src/init.py
touch src/agents/init.py
touch src/rag/init.py
touch src/config/init.py
touch tests/init.py

touch src/config/settings.py
touch src/rag/knowledge_base.py
touch src/agents/voice_agent.py
touch src/agents/livekit_handler.py
touch main.py
touch Dockerfile
touch cerebrium.toml
touch requirements.txt
touch .env.example
touch README.md

text

Create `.gitignore`:

cat > .gitignore << 'EOF'
.env
venv/
pycache/
*.pyc
logs/
.DS_Store
.vscode/
.idea/
EOF

text

Create `.env.example` (fill real values later):

cat > .env.example << 'EOF'
LIVEKIT_URL=...
LIVEKIT_API_KEY=...
LIVEKIT_API_SECRET=...

DEEPGRAM_API_KEY=...
CARTESIA_API_KEY=...

OPENROUTER_API_KEY=...
KB_PATH=./models/knowledge_base

LOG_LEVEL=DEBUG
LOG_FILE=./logs/voice_agent.log
EOF

text

Init git:

git init
git add .
git commit -m "Phase 0: skeleton"

text

---

## 1. requirements.txt (Claude Code)

1. Open **new Claude Code chat**.
2. Prompt:

   - “Create a production requirements.txt for a VoiceROI Voice Agent using:
     - Python 3.10
     - livekit, livekit-agents, livekit-agents-deepgram, livekit-agents-cartesia
     - llama-index, sentence-transformers
     - pydantic, pydantic-settings, python-dotenv
     - aiohttp, python-json-logger
     - Pin ALL versions (`name==X.Y.Z`). Output **only** requirements.txt.”

3. Paste result into `requirements.txt`.
4. Quick check:

cat requirements.txt

text

5. Commit:

git add requirements.txt
git commit -m "Phase 1: requirements"

text

---

## 2. cerebrium.toml (Claude Code)

New Claude chat. Prompt summary:

- “Create cerebrium.toml for project `voiceroi-voice-agent` with:
  - python-3.10
  - GPU A100
  - min/max replicas, timeout, etc.
  - Output only TOML.”

Paste → `cerebrium.toml` → commit.

---

## 3. settings.py (Claude Code)

New chat. Prompt summary:

- “Create `src/config/settings.py` using Pydantic Settings with:
  - LiveKitSettings (url, api_key, api_secret)
  - STTSettings (Deepgram api_key, model)
  - TTSSettings (Cartesia api_key, voice)
  - LLMSettings (provider, api_key, model, temperature)
  - KnowledgeBaseSettings (path)
  - LoggingSettings (level, file)
  - Top‑level Settings class aggregating them.
  - Load from `.env`. Provide `validate_settings()` that raises if keys missing.
  - Output only the file content.”

Paste → `src/config/settings.py` → quick `python -m py_compile` if you want → commit.

---

## 4–7. Core files (same pattern)

Repeat the same pattern for:

- `src/rag/knowledge_base.py`
- `src/agents/voice_agent.py`
- `src/agents/livekit_handler.py`
- `main.py`

Each:

1. New Claude chat.  
2. Very specific prompt (“Implement X file, using LiveKit + Deepgram + Cartesia + KB, output only file”).  
3. Paste → file → quick `python -m py_compile` if you care → commit.

---

## 8. Dockerfile (Claude Code)

New chat. Prompt:

- “Create a Dockerfile for a Python 3.10 app with requirements.txt, running `python main.py` on start. Output only Dockerfile.”

Paste → `Dockerfile` → commit.

---

## 9. Code README

New chat. Prompt:

- “Write README.md for a project called `VoiceROI Voice Agent` explaining:
  - What it does
  - How to run locally
  - How to configure `.env`
  - How to deploy on Cerebrium with `cerebrium deploy`.
  - Output only README.md.”

Paste → `README.md` in **voiceroi-voice-agent** → commit.

---

## 10. (Optional) Tests

New chat. Prompt:

- “Create `tests/test_imports.py` that just imports all main modules and asserts no error. Output only that file.”

Paste → commit.

---

## Golden Rules (Short Version)

- New Claude chat **per file**.
- One file per chat.
- You paste, then commit.
- If it breaks: new chat, same prompt.

That’s it.
