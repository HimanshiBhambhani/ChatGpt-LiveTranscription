# ChatGPT — Live Transcription (MVP)

A working MVP of the "ChatGPT Live Transcription" concept — built from the four Google Stitch
wireframes. Speak → see a live transcript → edit it → send → get a reply. One HTML file, no build step.

## Run it

Open `mvp/index.html` in **Chrome or Edge** (the Web Speech API that powers live transcription
is Chromium-only). No install, no server required.

> On first use the browser asks for microphone permission — allow it.

## The flow (maps 1:1 to the wireframes)

| Screen | State in the app |
|---|---|
| 1 — Default chat | Idle input bar with mic + Live Transcript toggle |
| 2 — Active recording | Animated waveform + real-time interim transcript ("LISTENING…") |
| 3 — Review & edit | Editable transcript (`contenteditable`) |
| 4 — Ready to send | Send → message posts and a reply comes back |

## Live Transcript toggle

- **On** — recording shows the transcript live as you speak (screen 2).
- **Off** — voice still works, but in a dark "black box" mode with no live transcript (like
  ChatGPT voice mode); the captured text appears only on the review screen before you send.

## Real vs. demo responses

- **Demo mode (default):** no key needed — replies are simulated so the full flow is usable.
- **Real replies:** tap the settings circle (top-right), pick a provider, and paste its key.
  Keys are stored only in your browser's `localStorage` and called directly from your device.

  | Provider | Model | Get a key |
  |---|---|---|
  | OpenAI | `gpt-4o-mini` | platform.openai.com |
  | Groq | `llama-3.3-70b-versatile` | console.groq.com |
  | Google Gemini | `gemini-1.5-flash` | aistudio.google.com |

## What's intentionally out of scope (V2)

Streaming responses, conversation memory across turns, auth/accounts, server-side key proxy,
multi-language transcription, and the Cut/Copy/Replace polish from screen 3.

---
*Concept + MVP only. Not affiliated with OpenAI.*
