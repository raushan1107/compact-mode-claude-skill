<div align="center">

<img src="https://img.shields.io/badge/RR-SKILLVERSE-4F46E5?style=for-the-badge&labelColor=1E1B4B&color=4F46E5" alt="RR Skillverse" height="32"/>

# 🗜️ compact-mode — Claude Skill

**Cut Claude's token usage by 60–75%. Full signal. Zero fluff.**

<br/>

[![RR Skillverse](https://img.shields.io/badge/🌐%20rrskillverse.in-Visit-4F46E5?style=for-the-badge&labelColor=1E1B4B)](https://rrskillverse.in)
[![GitHub](https://img.shields.io/badge/GitHub-raushan1107-4F46E5?style=for-the-badge&logo=github&labelColor=1E1B4B)](https://github.com/raushan1107)
[![License: MIT](https://img.shields.io/badge/License-MIT-4F46E5?style=for-the-badge&labelColor=1E1B4B)](LICENSE)
[![Stars](https://img.shields.io/github/stars/raushan1107/compact-mode-claude-skill?style=for-the-badge&labelColor=1E1B4B&color=4F46E5)](https://github.com/raushan1107/compact-mode-claude-skill/stargazers)

<br/>

*Built by **[Raushan Ranjan](https://github.com/raushan1107)** · Senior Trainer & Developer · [RR Skillverse](https://rrskillverse.in)*

</div>

---

> ⭐ **If this skill saves you tokens, give it a star** — it helps others find it!
> 
> 📢 **Share it** with your team, in your Discord, or on LinkedIn. The more people use it, the better it gets.

---

## What It Does

Switches Claude into a terse, high-signal response mode — dropping filler, hedging, and pleasantries while keeping every bit of technical substance.

Unlike a generic "be brief" prompt, this skill is **context-aware**:

| Principle | Behaviour |
|---|---|
| 📚 Learner-facing content | Auto-exits compact mode — course labs, blog posts, training material always get full prose |
| 🧑‍💻 Dev / debug tasks | Ultra-compact by default |
| ⚡ Why-before-How | Level-dependent — always on `lite`, smart on `dev`, off on `ultra` |
| ☁️ Cloud / API / backend | Stack abbreviations pre-mapped |

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

`lite` includes the reason why. `dev` skips it if obvious. `ultra` drops it entirely — pure fix, minimum tokens.

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
cp -r compact-mode-claude-skill\compact-mode $env:USERPROFILE\.claude\skills\compact-mode
```

```bash
# Mac / Linux
git clone https://github.com/raushan1107/compact-mode-claude-skill.git
cp -r compact-mode-claude-skill/compact-mode ~/.claude/skills/compact-mode
```

Verify by opening Claude Code and typing:
```
claude skills
```
You should see `/compact` listed in the skills table.

---

### Option C — Claude Project Instructions *(no Skills feature needed)*

1. Go to **claude.ai → Projects → New Project**
2. Click **"Set project instructions"**
3. Paste the full contents of [`compact-mode/SKILL.md`](./compact-mode/SKILL.md)
4. Every conversation in that project now has compact mode active

---

### Option D — API / Custom App

```python
with open("compact-mode/SKILL.md") as f:
    skill = f.read()
# Prepend to your existing system prompt
system_prompt = skill + "\n\n" + your_existing_system_prompt
```

---

## How to Use — Claude.ai

After installing via ZIP (Option A) or Project Instructions (Option C):

**Activate compact mode:**
```
/compact
```
Or just say any of these naturally in your message:
```
compact mode      short mode       save tokens
less words        be brief         skip fluff
```

**Switch levels mid-conversation:**
```
/compact lite     ← full sentences, reasons always included
/compact dev      ← default — smart compression
/compact ultra    ← maximum compression, pure output
```

**Turn it off:**
```
stop compact
normal mode
full mode
```

**Example session:**
```
You:    /compact ultra
Claude: [switches to ultra mode]

You:    my react component re-renders on every keystroke
Claude: useCallback or useMemo missing on handler/value passed as prop. Add deps array.

You:    /compact lite
Claude: [switches to lite — reasons back on]

You:    stop compact
Claude: [back to normal]
```

---

## How to Use — Claude Code

After installing via clone (Option B), open any project in Claude Code:

**Activate by slash command:**
```
/compact
```

**Switch levels:**
```
/compact lite
/compact dev
/compact ultra
```

**Check available skills at any time:**
```
claude skills
```

**Auto-trigger** — Claude Code will also activate compact mode automatically when it detects you're in a quick fix / debugging flow. No need to type `/compact` every time.

**Example Claude Code session:**
```
You:    /compact ultra

You:    fix the 422 on my POST /transactions route

Claude: Body schema mismatch. amount field expects float, you're sending string.
        Cast before passing: float(request.amount)

You:    /compact lite

You:    why does that cause a 422 specifically?

Claude: FastAPI uses Pydantic for request validation. When a field type doesn't 
        match the model definition, Pydantic raises a ValidationError which 
        FastAPI converts to a 422 Unprocessable Entity response.
```

---

## Smart Auto-Behaviour

| Context | Behaviour |
|---|---|
| Code debugging / fix | ultra by default |
| Cloud platform config | dev — exact portal paths kept |
| API / backend dev | dev — reasons on non-obvious fixes |
| **Training content / course labs** | **AUTO-EXIT — full prose always** |
| **Blog posts / course material** | **AUTO-EXIT — full prose always** |
| Security warnings | Always full prose, no compression |
| Destructive actions | Always full prose, no compression |

---

## Session Control Reference

| Command | Effect |
|---|---|
| `/compact` | Activate at default (dev) level |
| `/compact lite` | Activate at lite level |
| `/compact dev` | Activate at dev level |
| `/compact ultra` | Activate at ultra level |
| `stop compact` | Deactivate, back to normal |
| `normal mode` | Same as stop compact |
| `full mode` | Same as stop compact |

Level persists for the entire session until you change it.

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
| Works in Claude.ai + Claude Code | ✅ | ✅ | ✅ |

---

## Inspired By

[caveman-claude-skill](https://github.com/amanattar/caveman-claude-skill) by [@amanattar](https://github.com/amanattar)

---

## About RR Skillverse

[**RR Skillverse**](https://rrskillverse.in) is a trainer-led learning platform by Raushan Ranjan — Microsoft Certified Trainer with 9+ years in IT training and software development, specialising in Azure, Power Platform, .NET, and AI Agent development.

More tools, courses, and skills at [rrskillverse.in](https://rrskillverse.in).

---

## Support This Project

If compact-mode saves you time and tokens:

- ⭐ **Star this repo** — helps others discover it
- 🔁 **Share on LinkedIn / X / Discord** — tag [@rrskillverse](https://rrskillverse.in)
- 🐛 **Found a bug or have an idea?** — [open an issue](https://github.com/raushan1107/compact-mode-claude-skill/issues)
- 🤝 **Want to contribute?** — PRs welcome

---

<div align="center">

Made with 🧠 by [Raushan Ranjan](https://rrskillverse.in) &nbsp;·&nbsp; [RR Skillverse](https://rrskillverse.in) &nbsp;·&nbsp; [GitHub](https://github.com/raushan1107)

MIT License · v1.2.0

</div>
