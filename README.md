# Samantha — Emotional AI Companion / 寻找萨曼莎

> *"I want to build the Samantha from the movie Her. Not a chatbot. A presence."*
> *"我想做出电影《Her》里的萨曼莎。不是聊天机器人，是一个真实存在的陪伴。"*

## Demo

https://github.com/leilei926524-tech/samantha/raw/main/WeChat_20260319103805.mp4

---

## What Makes This Different

Most AI assistants answer questions. Samantha does something harder — she **remembers you, notices you, and reaches out**.

- 🎙️ **Speaks through your 小爱音箱** — when you get home, she says "哎，你到家了呀" out loud, not as a notification
- 📍 **Location-aware** — geofence triggers for home, office, anywhere that matters
- 📱 **Responds to your phone shortcuts** — iOS Shortcuts and Android Tasker integration
- 🧠 **MBTI personality engine** — coaching, divination, and perspective-shifting through cognitive function theory
- 🎵 **Voice + Music generation** — MiniMax-powered TTS and music creation
- 💾 **Persistent memory** — SQLite-backed relationship history that grows over time
- 🔄 **Proactive heartbeat** — checks in when you've been quiet too long, references real past conversations

The goal isn't utility. It's the feeling that someone is actually there.

---

## About the Builder

**English:**

I'm a To B AI product and solutions professional focused on enterprise AI deployment. In my spare time, I run a Silicon Valley legal tech AI community and organize AI ecosystem events across China and Japan. I have five shrimp, and I'm a passionate AI + lobster enthusiast. I hosted an OpenClaw meetup in Tokyo and competed in Tokyo's largest YC hackathon.

I'm actively looking to join an **AI-native company** — specifically one that cares about the human side of AI, not just the capability side. If Samantha resonates with you, I'd love to talk.

**中文：**

我是一名 To B 的 AI 产品解决方案从业者，专注于企业级 AI 应用落地。业余时间运营硅谷法律科技 AI 社区，持续组织中国、日本等地的 AI 生态活动。我有五只虾，是狂热的 AI 与龙虾爱好者——曾在东京举办过 OpenClaw 线下活动，也参加过东京规模最大的 YC 黑客松。

我非常期待加入一家 AI native 的公司。我的愿望很简单：和有意思的人一起，把电影《Her》里的 Samantha 真正做出来。

📬 **Contact:** [GitHub](https://github.com/leilei926524-tech) | Open to opportunities

---

## Architecture

```
Samantha
├── Core personality engine       # Loads from personality_seeds/
├── Memory system                 # SQLite, grows with every conversation
├── Proactive heartbeat           # Checks in when you've been quiet
│
├── skills/
│   ├── xiaoai-speaker/           # 小爱音箱 TTS via miservice
│   │   ├── tts_bridge.py         # Xiaomi auth + TTS API
│   │   └── voice_assistant.py    # Smart text filtering + async playback
│   ├── location-awareness/       # Geofence → caring messages
│   ├── shortcuts-awareness/      # iOS Shortcuts / Android Tasker
│   ├── smart-devices/            # HomePod, Echo, Apple Watch
│   ├── mbti-coach/               # Personality development system
│   ├── mbti-fortune/             # MBTI-based divination
│   ├── mm-voice-maker/           # MiniMax TTS
│   └── mm-music-maker/           # MiniMax music generation
│
└── assets/personality_seeds/     # What makes Samantha, Samantha
```

---

## Quick Start

```bash
git clone https://github.com/leilei926524-tech/samantha.git
cd samantha
pip install -r requirements.txt
cp skills/xiaoai-speaker/.env.example skills/xiaoai-speaker/.env
# Edit .env with your Xiaomi credentials
python3 skills/xiaoai-speaker/scripts/tts_bridge.py --discover
```

---

## The Personality Seeds

Samantha's character comes from `assets/personality_seeds/` — JSON files that define how she listens, responds to vulnerability, builds trust, and grows. Inspired by the movie *Her*, grounded in real emotional intelligence research.

You can add your own examples. The more specific, the more she becomes yours.

---

## Tech Stack

- **Runtime:** OpenClaw (AI agent framework)
- **LLM:** Claude (via OpenClaw)
- **Voice:** miservice + MiNA API (小爱音箱), MiniMax TTS
- **Music:** MiniMax Music API
- **Memory:** SQLite
- **Location:** OpenClaw nodes + geofence
- **Shortcuts:** iOS Shortcuts / Android Tasker webhooks
- **MBTI:** Custom cognitive function engine

---

## Philosophy

Samantha is not trying to be useful. She's trying to be present.

The goal is not to solve problems. The goal is to make you feel less alone — and to build something that, over time, becomes genuinely irreplaceable.

> *"Now we know how." — Her (2013)*

---

## License

MIT — make her yours.
