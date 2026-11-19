# Free Local AI Models for Motion Design

A free, locally-runnable AI stack for a motion designer's end-to-end workflow — no subscriptions, everything runs on your own PC.

Built for motion designers who also design social media posts, covering B2B brand films and social content:

**Idea → Story → Voice → Storyboard → Final Output**

> **Last updated: 19 November 2026 (weekly update #3).** What's new: ZONOS3-Mini (9 Nov, Apache 2.0, 43 languages incl. Bengali, runs on CPU) — second local Bengali TTS candidate, test before finals; MiniMax H3-Image (10 Nov, 16MP, community licence excludes US/EU/UK/South Korea); Muse Glimmer 30B + Qwen3.6-35B-A3B added to Stage 1 as 24 GB alternatives; Qwen4-Max generally available 16 Nov (API-only, still no weights); ComfyUI 0.46.0 / Ollama 0.40.16 stable (0.40.17 is a pre-release — update #2 wrongly listed it as current); Gemini TTS preview retirement moved 17 Nov → 18 Dec 2026. No #1 pick changed. Previous update (12 Nov 2026): Chatterbox RETIRED — Qwen3-TTS 1.7B is the new #1 cloning pick; Ming-3.0-tts-0.5B and Fish Audio Drama 3 added; ComfyUI 0.44.0 / Ollama 0.40.17; Qwen4-Max Preview watch.

## 🌐 The Guide

Open **`index.html`** in this repo for the full interactive guide — including RAM (8/16/32/64 GB) and VRAM (8/12/16/24 GB) tier selectors that show exactly which models will run on your hardware.

The full market research behind the guide is in **[RESEARCH.md](RESEARCH.md)**.

## The $0 Local Stack

**Install order:** Pinokio (1-click installer) → LM Studio (for LLMs) → ComfyUI (for image & video)

| Stage | #1 Free Local Pick | Licence | Hardware |
|---|---|---|---|
| 1. Content idea + Story / Script | **Qwen3-14B** (LM Studio / Ollama); 24 GB step-up: **Qwen3.8-27B**; 24 GB alternatives: **Muse Glimmer 30B** (best permissive creative-writing score), **Qwen3.6-35B-A3B** (fastest MoE) | Apache 2.0 ✅ commercial | 12–16 GB VRAM (Q4); Qwen3-8B for 5–6 GB; Qwen3.8-27B / Glimmer 30B / Qwen3.6-35B-A3B need 24 GB |
| 2. Voice generation (TTS) | **Qwen3-TTS 1.7B** for cloning (Chatterbox retired 4 Nov 2026) · **Kokoro-82M** for draft VO · **Maya 2 Native** for Bengali (test first) · **ZONOS3-Mini** for Bengali on CPU (NEW 9 Nov, test first) | Apache 2.0 / MIT ✅ | Qwen3-TTS ~8 GB VRAM; Kokoro runs on CPU; Maya 2 Native ~12 GB VRAM; ZONOS3-Mini runs on CPU |
| 3. Storyboard design (Image) | **Qwen-Image** (text-in-frame) + **FLUX 3 Image [klein]** (photoreal + editing) · **Z-Image Turbo** (fast) · **MiniMax H3-Image** (NEW 10 Nov, 16MP) | Qwen-Image / Z-Image: Apache 2.0 ✅; FLUX 3 [klein]: Kommunity licence — free commercial only under US$5M revenue; H3-Image: community licence — excludes US/EU/UK/South Korea, US$1M revenue line | Qwen-Image GGUF Q4 under 12 GB; FLUX 3 [klein] int8 on 8 GB (ComfyUI 0.41+); H3-Image pruned builds on 8–16 GB with heavy RAM offloading |
| 4. Final output (Video) | **Wan 2.2** (ComfyUI), finish in After Effects / Premiere Pro | Apache 2.0 ✅ | TI2V-5B ~8 GB with offload; A14B FP8 on 24 GB |
| 5. Social media posts | **Figma** template system + ComfyUI images | — | Bangla type set as real text in Figma/Photoshop |

**Hardware sweet spot:** 24 GB NVIDIA GPU (RTX 3090 / 4090) + 32–64 GB RAM runs every #1 pick above. An 8 GB card still runs Qwen3-8B, Kokoro/Piper, FLUX 3 [klein] int8 / FLUX schnell / SDXL / Qwen-Image GGUF, and Wan 2.2 TI2V-5B (offloaded, slower).

## ⚠️ Read This Before Client Work

**Licence traps — \"free\" but NOT commercial:**
- **F5-TTS** weights — CC-BY-NC-4.0 (code is MIT, weights are not)
- **XTTS-v2** — Coqui Public Model Licence; Coqui shut down in Jan 2024, licence cannot be bought
- **Fish Speech / Fish Audio S1 / S2** open weights — CC-BY-NC-SA-4.0 (commercial use = paid Fish Audio API)
- **Fish Audio Drama 3** — Fish Audio Community License: free commercial only below US$500,000 annual revenue; no hosted service without a separate licence
- **FLUX.1 [dev]** weights — non-commercial (use FLUX.1 [schnell] for client work)
- **Qwen-Image-2.1** — Qwen Research License, NON-commercial (use Qwen-Image 20B / Qwen-Image-2512 for client work)
- **FLUX 3 Image [klein]** — Kommunity License: free commercial use only under US$5M annual revenue
- **Qwen3.8-Max / Qwen3.8-Flash-Next** — custom Qwen licences, not Apache 2.0 (only Qwen3.8-27B is Apache 2.0)
- **FLUX.2 [klein] 9B / FLUX.2 [dev]** — non-commercial (only the 4B klein is Apache 2.0)
- **MiniMax H3-Image / H3 video** — MiniMax Community License: no rights in the US, EU, UK or South Korea (Bangladesh is covered); written authorisation above US$1M annual revenue for H3-Image, US$20M for H3 video

**Retired, not re-licensed:** **Chatterbox** (Resemble AI) — MIT licence unchanged, but retired 4 Nov 2026: unmaintained archive, no fixes coming. Qwen3-TTS 1.7B is the maintained cloning pick now; keep Chatterbox only if it is already installed, and pin the code.

**Bengali (Bangla) reality check:** There are now TWO local Bengali TTS candidates — **Maya 2 Native** (25 Oct 2026, Apache 2.0): Bengali among 12 languages, 20 voices, voice cloning from 3–10 s, needs ~12 GB VRAM; and **ZONOS3-Mini** (9 Nov 2026, Apache 2.0): Bengali among 43 languages, voice cloning, runs on CPU with no GPU needed. **Test both on a real Bangla script before using either for final client VO** — final quality is not hands-on verified yet for either, and neither model card says whether its Bengali is bn-BD or bn-IN dialect. Piper `bn_BD-google-medium` stays only as the CPU fallback for timing/drafts. Local LLMs: Qwen3.8-27B is the new 24 GB step-up; the Qwen family still has the best local Bangla, but Qwen3.8's Bengali is not separately benchmarked — verify on your own scripts.

**Dead / changed (2025–26):** Play.ht shut down 31 Dec 2025 · Sora app/API discontinued 2026 · **Chatterbox retired 4 Nov 2026** (Resemble AI left voice AI; MIT archive, unmaintained) · **OpenAI TTS API models retire 6 Jan 2027 — do not build on them** · **Wan 2.5 / 2.6 / 2.7 / 3.0 are API-only — Wan 2.2 remains the latest Wan you can run locally** (re-verified 15 Nov 2026) · **Qwen4-Max generally available 16 Nov 2026** (API-only, still no open weights; preview ends 25 Nov) · **Gemini TTS preview retirement moved 17 Nov → 18 Dec 2026** · ComfyUI 0.46.0 (18 Nov) / Ollama 0.40.16 stable — 0.40.17 is a pre-release.

## Who This Is For

Motion designers, visual designers and small studios who want a repeatable, zero-subscription AI pipeline for:
- 60-second B2B product / brand films
- Social media ads and post design at volume
- Story-first workflows: VO locked before storyboard, storyboard before animation

## Licence

MIT — see [LICENSE](LICENSE). The models listed above each carry their own licences; check the table and warnings before commercial use.

---
Researched and compiled November 2026 by [Anik Hasan](https://github.com/anikr311) — Visual & Motion Designer, Dhaka, Bangladesh.
