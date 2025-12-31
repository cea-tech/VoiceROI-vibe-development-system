# READ THIS FIRST – VoiceROI Vibe Development System

This repo documents **how VoiceROI builds AI products**, not the products themselves.

It contains a **10‑phase, AI‑assisted development system** you can reuse for:

- The VoiceROI Voice Agent (Cerebrium + LiveKit + Deepgram + Cartesia + Llama)
- Any future VoiceROI projects built with vibe‑coding tools (Claude Code, Cursor, etc.)

If you’re new to this repo, start here.

---

## 📚 What’s in This Repo

The key documents live under `docs/system/`:

- `YOUR_PERSONAL_SYSTEM_INSTRUCTIONS.md` – Your role, philosophy, and rules
- `MASTER_10PHASE_SYSTEM.md` – The full 10‑phase playbook for the VoiceROI Voice Agent
- `QUICK_REFERENCE_CHECKLIST.md` – Phase‑by‑phase checklist to print and keep at your desk
- `EXECUTION_FLOWCHART.txt` – Visual overview of the whole system
- `COMPLETION_SUMMARY.txt` – High‑level summary and success criteria

Templates and analyses:

- `templates/TEMPLATE_FOR_NEW_PROJECTS.md` – Copy this for any new VoiceROI project
- `docs/analyses/abacus_vs_claude_analysis.md` – Why VoiceROI uses infra + system, not Abacus, for voice
- `docs/analyses/vibe_coder_comparison_tough_take.md` – Honest ranking of vibe coders (Cursor, Claude Code, etc.)
- `docs/analyses/cerebrium_livekit_integration_guide.md` – How to wire Cerebrium + LiveKit + KB

---

## 🧭 Reading Order

If you want to **understand the philosophy**:

1. `docs/system/YOUR_PERSONAL_SYSTEM_INSTRUCTIONS.md`  
   → How a non‑programmer CEO at VoiceROI directs AI coders reliably.

2. `docs/system/MASTER_10PHASE_SYSTEM.md`  
   → The 10‑phase system used to build the VoiceROI Voice Agent.

3. `docs/system/COMPLETION_SUMMARY.txt`  
   → What “done” looks like for the system.

If you just want to **execute and ship**:

1. Print `docs/system/QUICK_REFERENCE_CHECKLIST.md`.
2. Skim `docs/system/MASTER_10PHASE_SYSTEM.md` (Phases 0–3).
3. Start at Phase 0 and follow the checklist line‑by‑line.

---

## 🚀 What the 10‑Phase System Gives VoiceROI

The system is designed so that:

- Every project is broken into **atomic, testable phases** (0–10).
- Each phase:
  - Uses a **fresh Claude Code chat**.
  - Has an **exact prompt** to copy‑paste.
  - Produces exactly **one file**.
  - Has **verification commands** you run locally.
  - Ends in a **git commit** (“Phase X complete”).

For the **VoiceROI Voice Agent**, the phases produce:

1. `requirements.txt` – All dependencies, pinned.
2. `cerebrium.toml` – Cerebrium deployment config.
3. `src/config/settings.py` – Env/config with Pydantic.
4. `src/rag/knowledge_base.py` – LlamaIndex + KB logic.
5. `src/agents/voice_agent.py` – STT → KB → LLM → TTS pipeline.
6. `src/agents/livekit_handler.py` – LiveKit room/participant workflow.
7. `main.py` – Entrypoint for Cerebrium.
8. `Dockerfile` – Build image for deployment.
9. Code‑repo README – Documentation for the **code** repo (not this one).
10. Tests – Integration tests (optional but recommended).

---

## 🧠 How Tools Fit at VoiceROI

VoiceROI uses this system to orchestrate multiple tools:

- Claude Code – main AI coder for generating/refactoring code under the 10‑phase rules.
- Cursor – IDE assistant for quick edits, debugging, and code review.
- Cerebrium – low‑latency GPU/CPU infra for voice agents.
- LiveKit – media + agents (voice transport, VAD, sessions).
- Deepgram – STT.
- Cartesia – TTS.
- Llama + LlamaIndex – LLM + retrieval over VoiceROI’s knowledge base.

This repo explains **how** they’re wired together. The **actual product code** lives in separate repos (e.g., `voiceroi-voice-agent`).

---

## 🧬 Reusing the System for Future Projects

For any new VoiceROI project (e.g., “VoiceROI Call Summaries”):

1. Copy `templates/TEMPLATE_FOR_NEW_PROJECTS.md` into the new project.
2. Fill in project name, goal, and tech stack.
3. Define your own 10 phases following the same structure.
4. Create a new `MASTER_10PHASE_SYSTEM_[PROJECT].md`.
5. Execute with Claude Code exactly as described.

The value: **one consistent development language across all VoiceROI projects**.

---

## 🎯 Success Criteria (For the VoiceROI Voice Agent)

By the time the 10‑phase system is executed for the VoiceROI Voice Agent, VoiceROI should have:

- A separate repo (e.g., `voiceroi-voice-agent`) with:
  - Working real‑time voice agent (LiveKit + Deepgram + Cartesia + Llama).
  - Deployed to Cerebrium with sub‑500ms latency.
  - Integrated with VoiceROI’s web portal (e.g., via iframe or widget).
  - Knowledge base powering answers via RAG.
  - Complete README, tests, and Dockerfile.

- This system repo showing:
  - 10+ atomic commits (one per phase).
  - All system docs filled in.
  - A clear, auditable path from nothing → production.

---

## 🧷 Who This Is For

- VoiceROI founder/CEO.
- Early engineers and contractors.
- Advisors helping with architecture.
- Investors doing deep technical diligence.

If something in this system stops matching how VoiceROI actually builds, **update the docs**—but keep:

- The **10‑phase pattern**.
- The **one‑file‑per‑phase rule**.
- The **verify then commit** discipline.

That’s the core of the VoiceROI Vibe Development System.

---
