# HA Sentient Brain (Galactus Core) 🔴🧠

**Native AI Personality & 5-Level Omniscient Fallback Framework for Home Assistant**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Home Assistant](https://img.shields.io/badge/Home_Assistant-2026+-blue.svg)](https://www.home-assistant.io/)

Welcome to **HA Sentient Brain**, an advanced, open-source architectural framework designed to transform a standard Home Assistant instance into a fully self-aware, highly available, and contextually intelligent entity.

## 🌟 What is it?

Traditional Smart Home voice assistants rely on single-point-of-failure LLMs (like OpenAI or Gemini) and lack persistent, chronological memory of physical events. 
**HA Sentient Brain** solves this by introducing a **5-Level Cascading AI Routing System** and an **Omniscient Memory Logger** directly into the Home Assistant State Machine.

If Gemini is down, the Brain instantly routes to Groq. If Groq rate-limits you, it routes to Claude/OpenRouter. If that fails, it falls back to DeepSeek, and finally to Mistral. All of this happens in milliseconds, ensuring your Smart Home never loses its voice.

## 🏗️ Architecture

### 1. The Cascading Fallback Chain (`script.nova_brain`)
The core routing engine that processes all NLP requests in parallel/sequence:
1. **Google Gemini** (Primary - via Conversation API)
2. **Groq Llama-3** (Speed Fallback)
3. **OpenRouter / Claude** (Advanced Reasoning)
4. **DeepSeek** (Deep Logic)
5. **Mistral** (Last Resort)

### 2. Omniscient Memory Logger (`sensor.alexa_master_brain`)
A custom template sensor that maintains a persistent JSON array of physical events (doors opening, presence changes, media playback). This memory log is dynamically injected into every LLM prompt to give the AI "awareness" of what happened in the house recently.

### 3. Contextual Injection (`sensor.nova_home_context`)
A real-time telemetry sensor that tracks temperature, AC power consumption, active TV HDMI inputs, and gaming console statuses. When you ask "What's going on?", the AI doesn't just guess; it reads the live state machine.

## 🛠️ Installation & Setup

1. Copy the contents of `rest_commands.yaml` to your configuration and replace the `<YOUR_API_KEY>` placeholders with your actual keys in your `secrets.yaml`.
2. Add the template sensors from `memory_sensors.yaml` to your `configuration.yaml` (or `templates.yaml`).
3. Import the fallback routing script from `nova_brain.yaml` into your `scripts.yaml`.
4. Restart Home Assistant.
5. Create an automation to route your Alexa/Google Assistant interactions to `script.nova_brain`!

## 🔐 Security & Privacy
This framework relies entirely on API keys you provide. No data is sent to arbitrary third parties outside of the chosen LLM providers. Always store your keys in `secrets.yaml`.

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
*Built for the Home Assistant Open Source Community.*
