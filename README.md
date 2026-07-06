# Gemini Omni Prompting — Claude Skill

A Claude skill that helps you write high-quality video generation prompts for **Google DeepMind's Gemini Omni (Omni Flash)**, based on the [official prompt guide](https://deepmind.google/models/gemini-omni/prompt-guide/).

## What it does

Instead of guessing how to structure a video prompt, this skill gives Claude a repeatable framework so you get consistent, high-quality Omni prompts every time — whether it's a product ad, animation, or social clip.

## The framework

Every prompt is built around six dimensions:
1. **Shot framing & motion** – wide, close-up, push in, static, orbit, etc.
2. **Style** – cinematic, realistic, claymation, anime, documentary, etc.
3. **Lighting** – source and quality (golden hour, neon, warm, ethereal)
4. **Location** – described at a high level, letting Omni's world knowledge fill in details
5. **Action** – what's happening and in what sequence
6. **Text rendering** – on-screen text, titles, or UI labels (when needed)

It also accounts for audio intent, duration, and aspect ratio depending on the platform you're posting to.

## How to use it

1. Copy the `SKILL.md` file from this repo.
2. Add it to Claude (as a custom skill / project file, depending on your setup).
3. Ask Claude for a "Gemini Omni prompt" or describe your video idea — Claude will apply the framework automatically.
4. Iterate conversationally — you can refine the generated prompt with follow-up instructions instead of starting over.

## Why

Most people over-engineer prompts for Omni. This skill keeps things conversational (Omni relies on world knowledge, not frame-by-frame instructions), while still hitting the technical details that actually matter — camera language, lighting, and intent.

## Credit

Built by Tayyaba — feel free to fork, use, or adapt for your own workflow.
