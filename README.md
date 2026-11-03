# ChatGPT — Live Transcription (MVP)

**Live demo:** https://himanshibhambhani.github.io/ChatGpt-LiveTranscription/

A working MVP of the "ChatGPT Live Transcription" concept — built from the four Google Stitch
wireframes. Speak → see a live transcript → edit it → send → get a reply. One HTML file, no build step.

Our solution lets you **dictate hands-free with a live, editable transcript** — you see the text as
you speak, can tweak it before sending, and switch between live-view and a clean inline recorder,
across OpenAI/Groq/Gemini.

Plain ChatGPT voice just transcribes into the box (or does full voice-chat) with no
live-while-speaking view, no pre-send edit step, and no provider choice.

## Run it

Try the **[live demo](https://himanshibhambhani.github.io/ChatGpt-LiveTranscription/)**, or open
`mvp/index.html` in **Chrome or Edge** (the Web Speech API that powers live transcription
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
- **Off** — the input bar turns into a ChatGPT-style inline recorder (cancel ✕ / stop ■ / send)
  with an animated waveform and **no live text**; on stop it transcribes into the editable review
  box so you can still edit before sending.

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
