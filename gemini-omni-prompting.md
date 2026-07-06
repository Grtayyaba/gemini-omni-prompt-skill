---
name: gemini-omni-prompting
description: Use this skill whenever the user asks for an AI video generation prompt — phrases like "video prompt," "Gemini Omni prompt," "Veo prompt," "prompt for [video tool]," or requests to turn an idea/script/ad concept into a prompt for an AI video model. Also trigger when the user mentions Gemini Omni, Gemini Omni Flash, Veo, Google Flow, or is iterating on a video ad, YouTube short, or social clip generated with one of these tools. If the target model isn't stated or obvious from context, ASK which model (Gemini Omni, Veo, Sora, etc.) before writing the prompt — do not assume. This skill's framework is built specifically for Gemini Omni; for other models, adapt the structure but flag that the vocabulary/rules may differ.
---

# Gemini Omni Prompting

Writes AI-video prompts optimized for Google DeepMind's Gemini Omni (Omni Flash), based on the official prompt guide: https://deepmind.google/models/gemini-omni/prompt-guide/

## Step 0: Confirm the target model

If the user doesn't specify which video model the prompt is for, ask first. Don't assume Gemini Omni just because it's the default for this skill — Veo, Sora, and others have different prompting conventions (e.g. Veo wants more prescriptive detail; Omni wants less). Only proceed straight to the framework below if:
- The user explicitly says "Gemini Omni" / "Omni Flash" / "Google Flow", OR
- Prior conversation in this session already established Omni as the target.

If they name a different model, adapt: keep the same underlying discipline (framing, style, lighting, location, action) but drop Omni-specific rules like "less prescriptive" and the specific camera-term list, and note that the prompt may need retuning for that model's conventions.

## The Omni framework: six dimensions

Every strong Omni prompt should touch these, in roughly this order:

1. **Shot framing & motion** — wide / medium / close-up / macro, and how the camera moves (glide, push in, rush, static, orbit).
2. **Style** — the visual language: realistic, cinematic, grounded, majestic, claymation, anime, watercolor, documentary, etc.
3. **Lighting** — the source (sun, streetlamp, off-screen), and quality (crisp, warm, ethereal, golden hour, neon).
4. **Location** — the setting, described at the level of overall intention, not exhaustive detail (Omni's world knowledge fills gaps).
5. **Action** — who/what is happening, in what sequence. This is where pacing and choreography live.
6. **Text rendering** (when relevant) — Omni can render on-screen text/title cards/UI labels. If the user wants on-screen text, specify exact wording, placement, and timing.

Also consider, when relevant to the ask:
- **Audio** — Omni generates native synchronized audio. Always state audio intent explicitly, even if it's just "natural ambient sound only, no music."
- **Duration/aspect ratio** — Omni Flash outputs are short (~10s). Match aspect ratio to platform: 9:16 vertical/social, 16:9 cinematic/landscape, 1:1 centered.

## Core prompting principles

- **Be conversational, not prescriptive.** Omni reasons across modalities and has strong world knowledge (physics, history, culture, science). Describe intent and a few key visual facts — don't try to control every pixel or frame. This is the single biggest difference from Veo-style prompting.
- **Use real camera vocabulary — it functions as technical commands:**
  - Continuous take: "one continuous shot," "oner"
  - Static: "static," "locked off," "fixed"
  - Movement: "push in," "punch in," "dolly zoom," "orbit"
  - Camera type/feel: "natural smartphone zoom," "film camera," "webcam style"
- **Multi-input reference.** Omni accepts text, image, audio, and video together in one prompt, and can assign each a specific role (e.g. "image defines character identity," "audio defines rhythm," "video defines only the camera movement — don't copy the room or people"). If the user has multiple inputs, ask what each one should contribute if it's not obvious.
- **Iterative, surgical editing.** Once a clip exists, refine with plain-language follow-ups rather than rewriting from scratch — e.g. "Change the camera angle to a close-up over his shoulder. Keep everything else identical." Encourage one change per turn when precision matters, so it's clear what caused what.
- **Style transfer.** Omni can restyle existing footage (anime, claymation, watercolor, risograph, etc.) while preserving the original motion — useful for turning one clip into a stylistic progression.
- **World-knowledge grounding.** For explainers or anything needing real-world accuracy (science, history, physical processes), lean on Omni's reasoning rather than over-specifying — e.g. "explain the difference between regular and quantum computing" is enough of a prompt for it to visualize accurately.
- **Complex actions don't need frame-by-frame description.** State the action/intent once; Omni applies it sensibly across the clip.

## Output format

When producing a prompt for the user, default to a single flowing paragraph (this is how Omni's own examples are written) rather than a rigid labeled template — Omni is built for natural language. Only use explicit labels (Shot / Style / Lighting / Location / Action / Text) if the user has multiple reference inputs to juggle and role-labeling reduces ambiguity, or if the user asks for that structure.

After giving the prompt, briefly flag:
- Which of the six dimensions it covers (if any are deliberately left out, say why)
- Whether it assumes audio, on-screen text, or specific duration/aspect ratio, so the user can correct those quickly
- That it's editable — they can iterate conversationally on the output rather than regenerating from scratch

Keep the accompanying explanation short. The prompt itself is the deliverable.
