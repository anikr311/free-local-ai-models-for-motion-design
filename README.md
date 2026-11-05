# Free Local AI Models for Motion Design

A free, locally-runnable AI stack for a motion designer's end-to-end workflow — no subscriptions, everything runs on your own PC.

Built for motion designers who also design social media posts, covering B2B brand films and social content:

**Idea → Story → Voice → Storyboard → Final Output**

## 🌐 The Guide

Open **`index.html`** in this repo for the full interactive guide — including RAM (8/16/32/64 GB) and VRAM (8/12/16/24 GB) tier selectors that show exactly which models will run on your hardware.

The full market research behind the guide is in **[RESEARCH.md](RESEARCH.md)**.

## The $0 Local Stack

**Install order:** Pinokio (1-click installer) → LM Studio (for LLMs) → ComfyUI (for image & video)

| Stage | #1 Free Local Pick | Licence | Hardware |
|---|---|---|---|
| 1. Content idea + Story / Script | **Qwen3-14B** (LM Studio / Ollama) | Apache 2.0 ✅ commercial | 12–16 GB VRAM (Q4); Qwen3-8B for 5–6 GB |
| 2. Voice generation (TTS) | **Kokoro-82M** for draft VO · **Chatterbox** for cloning · **Qwen3-TTS 1.7B** | Apache 2.0 / MIT ✅ | Kokoro runs on CPU; Qwen3-TTS ~8 GB VRAM |
| 3. Storyboard design (Image) | **Qwen-Image** + **FLUX.1 [schnell]** (ComfyUI) | Apache 2.0 ✅ | Qwen-Image GGUF Q4 under 12 GB; FLUX schnell 6–8 GB |
| 4. Final output (Video) | **Wan 2.2** (ComfyUI), finish in After Effects / Premiere Pro | Apache 2.0 ✅ | TI2V-5B ~8 GB with offload; A14B FP8 on 24 GB |
| 5. Social media posts | **Figma** template system + ComfyUI images | — | Bangla type set as real text in Figma/Photoshop |

**Hardware sweet spot:** 24 GB NVIDIA GPU (RTX 3090 / 4090) + 32–64 GB RAM runs every #1 pick above. An 8 GB card still runs Qwen3-8B, Kokoro/Piper, FLUX schnell / SDXL / Qwen-Image GGUF, and Wan 2.2 TI2V-5B (offloaded, slower).

## ⚠️ Read This Before Client Work

**Licence traps — "free" but NOT commercial:**
- **F5-TTS** weights — CC-BY-NC-4.0 (code is MIT, weights are not)
- **XTTS-v2** — Coqui Public Model Licence; Coqui shut down in Jan 2024, licence cannot be bought
- **Fish Speech** open weights — CC-BY-NC-SA-4.0 (commercial use = paid Fish Audio API)
- **FLUX.1 [dev]** weights — non-commercial (use FLUX.1 [schnell] for client work)

**Bengali (Bangla) reality check:** There is currently **no quality free local Bengali TTS**. The only local Bangla voice is Piper `bn_BD-google-medium` — usable for timing/draft only, not final VO. For final Bangla voiceover, cloud options (ElevenLabs v3, Azure Speech bn-BD voices) are still ahead. Local LLMs: Qwen3 has the best Bangla of any local model, but no rigorous Bengali creative benchmark exists yet.

**Dead tools (2025–26):** Play.ht shut down 31 Dec 2025 · Sora app/API discontinued 2026.

## Who This Is For

Motion designers, visual designers and small studios who want a repeatable, zero-subscription AI pipeline for:
- 60-second B2B product / brand films
- Social media ads and post design at volume
- Story-first workflows: VO locked before storyboard, storyboard before animation

## Licence

MIT — see [LICENSE](LICENSE). The models listed above each carry their own licences; check the table and warnings before commercial use.

---
Researched and compiled November 2026 by [Anik Hasan](https://github.com/anikr311) — Visual & Motion Designer, Dhaka, Bangladesh.
