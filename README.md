<div align="center">

<img src="https://img.shields.io/badge/RR-SKILLVERSE-4F46E5?style=for-the-badge&labelColor=1E1B4B&color=4F46E5" alt="RR Skillverse" height="32"/>

# 🗜️ compact-mode — Claude Skill

**Cut Claude's token usage by 60–75%. Full signal. Zero fluff.**

*"Why before How — always."*

<br/>

[![RR Skillverse](https://img.shields.io/badge/🌐%20rrskillverse.in-Visit-4F46E5?style=for-the-badge&labelColor=1E1B4B)](https://rrskillverse.in)
[![GitHub](https://img.shields.io/badge/GitHub-raushan1107-4F46E5?style=for-the-badge&logo=github&labelColor=1E1B4B)](https://github.com/raushan1107)
[![License: MIT](https://img.shields.io/badge/License-MIT-4F46E5?style=for-the-badge&labelColor=1E1B4B)](LICENSE)

<br/>

*Built by **[Raushan Ranjan](https://github.com/raushan1107)** · Senior Trainer & Developer · [RR Skillverse](https://rrskillverse.in)*

</div>

---

## What It Does

Switches Claude into a terse, high-signal response mode — dropping filler, hedging, and pleasantries while keeping every bit of technical substance.

Unlike a generic "be brief" prompt, this skill is **context-aware** and built around the **RR Skillverse training philosophy**:

| Principle | Behaviour |
|---|---|
| 🎓 "Why before How" | Always preserved — even at maximum compression |
| 📚 Learner-facing content | Auto-exits compact mode (course labs, blog posts, training material) |
| 🧑‍💻 Dev / debug tasks | Ultra-compact by default |
| ☁️ Azure · Power Platform · FastAPI | Stack abbreviations pre-mapped |

---

## Trigger Phrases

```
compact mode   short mode   save tokens
less words     be brief     skip fluff
/compact       less tokens
```

---

## Intensity Levels

Switch anytime with `/compact <level>`. Default is **dev**.

| Level | Why-before-How | Style |
|---|---|---|
| `lite` | ✅ Always | No filler or hedging. Full sentences. 1-line reason before every answer. |
| `dev` | ⚡ Only if non-obvious | Drop articles. Fragments OK. Short synonyms. Stack abbreviations. |
| `ultra` | ❌ Off | Max abbreviation. Arrows for causality. Pure output — zero explanation overhead. |

---

## Quick Example

**Prompt:** "Why is my Azure OpenAI call returning 429?"

| Level | Response |
|---|---|
| **lite** | "TPM quota on your deployment is exhausted — Azure throttles when you exceed it. Implement exponential backoff or increase your TPM quota in Azure AI Foundry." |
| **dev** | "TPM limit hit. Add exponential backoff or raise TPM quota in AI Foundry portal." |
| **ultra** | "TPM quota hit → 429. Backoff or ↑ TPM in AI Foundry." |

Notice: `lite` includes the reason why 429 happens. `dev` skips it if obvious. `ultra` drops it entirely — pure fix, minimum tokens.

---

## Smart Auto-Behaviour

| Context | Behaviour |
|---|---|
| Code debugging / fix | ultra by default |
| Azure / Power Platform config | dev — exact portal paths kept |
| FastAPI / AI Agent dev | dev — why retained |
| **Training content / course labs** | **AUTO-EXIT compact** |
| **Blog posts / course material** | **AUTO-EXIT compact** |
| Security warnings | Always full prose |
| Destructive actions | Always full prose |

---

## Why This Over Generic "Be Brief"?

| Feature | `"be brief"` | caveman-skill | **compact-mode** |
|---|---|---|---|
| Drops filler / hedging | ✅ | ✅ | ✅ |
| Why-before-How (level-aware) | ❌ | ❌ | ✅ lite=always · dev=smart · ultra=off |
| Protects learner-facing content | ❌ | ❌ | ✅ |
| Stack-specific abbreviations | ❌ | ❌ | ✅ |
| Context-aware auto-exit | ❌ | ❌ | ✅ |
| Intensity levels | ❌ | ✅ | ✅ |

---

## Installation

### Option A — ZIP Upload via Claude.ai ⭐ *(easiest — no Git needed)*

1. On this repo page, click **`Code` → `Download ZIP`**
2. Go to **[claude.ai](https://claude.ai) → Customize → Skills → Add Skill**
3. Upload the downloaded ZIP file
4. Done — `/compact` is now available across all your Claude conversations

> No terminal. No Git. Works on any OS — Windows, Mac, Linux.

---

### Option B — Claude Code *(for developers)*

```powershell
# Windows (PowerShell)
git clone https://github.com/raushan1107/compact-mode-claude-skill.git
cp -r compact-mode-claude-skill $env:USERPROFILE\.claude\skills\compact-mode
```

```bash
# Mac / Linux
git clone https://github.com/raushan1107/compact-mode-claude-skill.git
cp -r compact-mode-claude-skill ~/.claude/skills/compact-mode
```

Verify inside Claude Code by typing:
```
claude skills
```
You should see `/compact` listed in the skills table.

---

### Option C — Claude Project Instructions *(no Skills feature needed)*

1. Go to **claude.ai → Projects → New Project**
2. Click **"Set project instructions"**
3. Paste the full contents of [`SKILL.md`](./SKILL.md)
4. Every conversation in that project now has compact mode active

---

### Option D — API / Custom App

```python
skill = open("SKILL.md").read()
# Prepend to your existing system prompt
system_prompt = skill + "\n\n" + your_existing_system_prompt
```

---

## Session Control

```
stop compact    →  exit, back to normal
normal mode     →  same
/compact lite   →  switch to lite
/compact ultra  →  switch to ultra
```

---

## Inspired By

- [caveman-claude-skill](https://github.com/amanattar/caveman-claude-skill) by [@amanattar](https://github.com/amanattar)

---

## About RR Skillverse

[**RR Skillverse**](https://rrskillverse.in) is a trainer-led learning platform by Raushan Ranjan — Microsoft Certified Trainer with 9+ years in IT training and software development, specialising in Azure, Power Platform, .NET, and AI Agent development.

> *"Why before How" — every concept taught with its reason first.*

---

<div align="center">

Made with 🧠 by [Raushan Ranjan](https://rrskillverse.in) &nbsp;·&nbsp; [RR Skillverse](https://rrskillverse.in) &nbsp;·&nbsp; [GitHub](https://github.com/raushan1107)

MIT License

</div>
