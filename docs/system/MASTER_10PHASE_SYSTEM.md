# 🎯 MASTER 10‑PHASE SYSTEM – VoiceROI Voice Agent  
## VoiceROI Vibe Development System

**Goal**: Build a production‑ready VoiceROI Voice Agent (LiveKit + Deepgram + Cartesia + Llama + KB) deployed on Cerebrium, using Claude Code under a strict 10‑phase process.

This document is the **playbook**. It tells you:

- Exactly what YOU do (as CEO / non‑programmer).
- Exactly what Claude Code does (per phase).
- How to verify each step.
- How to reuse this system for future VoiceROI projects.

---

## ⚡ Critical Success Factors (Read First)

1. **One phase = one Claude Code chat.**  
   Never ask Claude to do two phases in one conversation.

2. **Copy the prompts exactly.**  
   No paraphrasing, no “also add…”. Paste verbatim.

3. **One file per phase.**  
   Each phase produces a single file (requirements.txt, settings.py, etc.).

4. **Immediate verification.**  
   After each phase, run the commands shown to confirm it works.

5. **Git commit after every phase.**  
   `git add . && git commit -m "Phase X: …"` – gives you rollback points.

6. **Never iterate inside a broken chat.**  
   If something fails, start a **new** Claude Code chat with the same prompt.

7. **Always show Claude reference code.**  
   For voice, that means Cerebrium + LiveKit examples.

If you follow these, you’ll get ~80–85% success on a very complex build, even as a non‑programmer.

---

## PHASE 0 – Your Local Setup (NO Claude Yet)

**Owner**: You  
**Time**: ~15 minutes  
**Goal**: Create a clean project skeleton for the *code* repo: `voiceroi-voice-agent`.

> This is separate from the system repo (`VoiceROI-vibe-development-system`).  
> Phase 0 prepares the **actual code project** where the voice agent will live.

### 0.1 – Create the project folder

```bash
cd ~
mkdir -p voiceroi-voice-agent
cd voiceroi-voice-agent
