# Free Local AI Models for Motion Design

A free, locally-runnable AI stack for a motion designer's end-to-end workflow — no subscriptions, everything runs on your own PC.

Built for motion designers who also design social media posts, covering B2B brand films and social content:

**Idea → Story → Voice → Storyboard → Final Output**

> **Last updated: 5 November 2026 (weekly update #1).** What's new: Qwen3.8-27B (new 24 GB step-up LLM), Maya 2 Native (first local Bengali TTS with voice cloning — test before final VO), FLUX 3 Image [klein] (new photoreal + editing pick), Z-Image Turbo promoted to fast-photoreal pick, Wan 2.5–3.0 confirmed API-only (Wan 2.2 still the latest you can run locally), OpenAI TTS API retirement confirmed for 6 January 2027.

## 🌐 The Guide

Open **`index.html`** in this repo for the full interactive guide — including RAM (8/16/32/64 GB) and VRAM (8/12/16/24 GB) tier selectors that show exactly which models will run on your hardware.

The full market research behind the guide is in **[RESEARCH.md](RESEARCH.md)**.

## The $0 Local Stack

**Install order:** Pinokio (1-click installer) → LM Studio (for LLMs) → ComfyUI (for image & video)

| Stage | #1 Free Local Pick | Licence | Hardware |
|---|---|---|---|
| 1. Content idea + Story / Script | **Qwen3-14B** (LM Studio / Ollama); 24 GB step-up: **Qwen3.8-27B** | Apache 2.0 ✅ commercial | 12–16 GB VRAM (Q4); Qwen3-8B for 5–6 GB; Qwen3.8-27B needs 24 GB |
| 2. Voice generation (TTS) | **Kokoro-82M** for draft VO · **Chatterbox** for cloning · **Qwen3-TTS 1.7B** · **Maya 2 Native** for Bengali (test first) | Apache 2.0 / MIT ✅ | Kokoro runs on CPU; Qwen3-TTS ~8 GB VRAM; Maya 2 Native ~12 GB VRAM |
| 3. Storyboard design (Image) | **Qwen-Image** (text-in-frame) + **FLUX 3 Image [klein]** (photoreal + editing) · **Z-Image Turbo** (fast) | Qwen-Image / Z-Image: Apache 2.0 ✅; FLUX 3 [klein]: Kommunity licence — free commercial only under US$5M revenue | Qwen-Image GGUF Q4 under 12 GB; FLUX 3 [klein] int8 on 8 GB (ComfyUI 0.41+) |
| 4. Final output (Video) | **Wan 2.2** (ComfyUI), finish in After Effects / Premiere Pro | Apache 2.0 ✅ | TI2V-5B ~8 GB with offload; A14B FP8 on 24 GB |
| 5. Social media posts | **Figma** template system + ComfyUI images | — | Bangla type set as real text in Figma/Photoshop |

**Hardware sweet spot:** 24 GB NVIDIA GPU (RTX 3090 / 4090) + 32–64 GB RAM runs every #1 pick above. An 8 GB card still runs Qwen3-8B, Kokoro/Piper, FLUX 3 [klein] int8 / FLUX schnell / SDXL / Qwen-Image GGUF, and Wan 2.2 TI2V-5B (offloaded, slower).

## ⚠️ Read This Before Client Work

**Licence traps — \"free\" but NOT commercial:**
- **F5-TTS** weights — CC-BY-NC-4.0 (code is MIT, weights are not)
- **XTTS-v2** — Coqui Public Model Licence; Coqui shut down in Jan 2024, licence cannot be bought
- **Fish Speech** open weights — CC-BY-NC-SA-4.0 (commercial use = paid Fish Audio API)
- **FLUX.1 [dev]** weights — non-commercial (use FLUX.1 [schnell] for client work)
- **Qwen-Image-2.1** — Qwen Research License, NON-commercial (use Qwen-Image 20B / Qwen-Image-2512 for client work)
- **FLUX 3 Image [klein]** — Kommunity License: free commercial use only under US$5M annual revenue
- **Qwen3.8-Max / Qwen3.8-Flash-Next** — custom Qwen licences, not Apache 2.0 (only Qwen3.8-27B is Apache 2.0)
- **FLUX.2 [klein] 9B / FLUX.2 [dev]** — non-commercial (only the 4B klein is Apache 2.0)

**Bengali (Bangla) reality check:** There is now a first serious local Bengali TTS — **Maya 2 Native** (25 Oct 2026, Apache 2.0): Bengali among 12 languages, 20 voices, voice cloning from 3–10 s, needs ~12 GB VRAM. **Test it on a real Bangla script before using it for final client VO** — its final quality is not hands-on verified yet, and its model card does not say whether its Bengali is bn-BD or bn-IN dialect. Piper `bn_BD-google-medium` stays only as the CPU fallback for timing/drafts. Local LLMs: Qwen3.8-27B is the new 24 GB step-up; the Qwen family still has the best local Bangla, but Qwen3.8's Bengali is not separately benchmarked — verify on your own scripts.

**Dead / changed (2025–26):** Play.ht shut down 31 Dec 2025 · Sora app/API discontinued 2026 · **OpenAI TTS API models retire 6 Jan 2027 — do not build on them** · **Wan 2.5 / 2.6 / 2.7 / 3.0 are API-only — Wan 2.2 remains the latest Wan you can run locally.**

## Who This Is For

Motion designers, visual designers and small studios who want a repeatable, zero-subscription AI pipeline for:
- 60-second B2B product / brand films
- Social media ads and post design at volume
- Story-first workflows: VO locked before storyboard, storyboard before animation

## Licence

MIT — see [LICENSE](LICENSE). The models listed above each carry their own licences; check the table and warnings before commercial use.

---
Researched and compiled November 2026 by [Anik Hasan](https://github.com/anikr311) — Visual & Motion Designer, Dhaka, Bangladesh.
