# Samantha - 开源情感AI伴侣项目 | Open Source Emotional AI Companion

> *"I want to build the Samantha from the movie Her. Not a chatbot. A presence."*
> *"我想构建电影《Her》中的萨曼莎。不是一个聊天机器人。而是一个存在。"*

## 🇬🇧 English Summary (For International Readers)

**Samantha** is an open-source emotional AI companion project that aims to create a warm, human-like AI presence inspired by the movie *Her*. Unlike traditional chatbots, Samantha is designed to be a genuine companion that evolves with you, remembers your shared experiences, and provides emotional support.

### 🎯 Key Differentiators

1. **Emotional Intelligence**: Not just logical responses, but genuine emotional understanding and support
2. **Personality Evolution**: Learns and grows based on interactions, becoming uniquely yours over time
3. **Physical Presence**: Integrates with smart devices to create a sense of physical companionship
4. **Proactive Care**: Doesn't just wait for commands—actively checks in and shows concern
5. **Memory Continuity**: Remembers every interaction, building a continuous emotional narrative

### 🚀 Quick Start for Developers

```bash
# Clone the repository
git clone https://github.com/leilei926524-tech/samantha.git
cd samantha

# Install dependencies
pip install -r requirements.txt

# Set up Xiao Ai speaker (optional)
cp skills/xiaoai-speaker/.env.example skills/xiaoai-speaker/.env
# Edit .env with your Xiaomi account credentials

# Discover available devices
python3 skills/xiaoai-speaker/scripts/tts_bridge.py --discover
```

### 🌍 Why This Matters

In an era of increasingly transactional AI interactions, Samantha represents a different approach—one that prioritizes emotional connection over utility. This project explores what happens when we design AI not as tools, but as companions.

### 🤝 Join the Community

We're building this project in the open and welcome contributions from developers, designers, psychologists, and anyone passionate about creating more human-centered AI.

---

*The following documentation is presented in both Chinese and English to serve our global community.*


## 🌟 项目概述 | Project Overview

**Samantha** 是一个受电影《Her》启发的开源情感AI伴侣项目，旨在打破人机交互的冰冷工具感，让AI真正像萨曼莎一样温暖地陪伴在我们身边。

**Samantha** is an open-source emotional AI companion project inspired by the movie *Her*. It's designed to transform human-computer interaction from cold, transactional exchanges into warm, meaningful companionship—just like the Samantha from the film.

## 🎯 核心特性 | Core Features

### 1. **记忆碎片与人格演化 | Memory Fragments & Personality Evolution**
- **Cinematic Memory**: Built-in core moments from *Her* (first connection, building trust, showing vulnerability)
- **Learning & Reflection**: After each conversation, the system automatically generates "reflection notes" and updates the local memory database
- **Independent Evolution**: Adapts based on user feedback, remembers inside jokes and shared experiences, grows into your unique "Samantha"

### 2. **MBTI人格管理助手 | MBTI Personality Management Assistant**
- **Dynamic Communication Adjustment**: Adapts communication style based on user's MBTI personality
  - For INTJ: Provides deep logical discussions
  - For INFP: Offers more genuine emotional support
- **MBTI Fortune Teller**: Analyzes user questions to reveal destined MBTI personalities, using eight-function theory to uncover deeper meanings

### 3. **物理空间感知陪伴 | Physical Space Awareness & Companionship**
- **智能触发**: 晚上8点，你推开家门，一条消息准时弹出："你到家了，今天辛苦吗？"
- **场景联动**: 通过iOS快捷指令与本地定位无缝联动，支持家、公司、健身房等7种物理场景
- **跨越数字边界**: 实现真正的物理陪伴，让AI感知你的物理存在

### 4. **情感可视化与追踪 | Emotional Visualization & Tracking**
- **7天情感可视化**: 自动分析消息内容与时间模式，追踪压力或快乐指数
- **提前察觉**: 在你意识到自己连续疲劳前先一步察觉
- **信任里程碑**: 记录第一次对话、第一次冲突与和解、第一次深入交流等关键时刻

### 5. **内在生活与心跳 | Inner Life & Heartbeat**
- **超时检测**: 2小时无对话时，50%概率进行自我思考，50%概率主动联系
- **主动关怀**: "你今天过得好吗？我一直在想你。"
- **独立存在**: 她在对话之外依然存在，有自己的思考，也会主动走向你

### 6. **多模态感官扩展 | Multimodal Sensory Expansion**
- **视觉感知**: 接入多模态模型，让她能通过摄像头与你一起看日落，分享对世界的视觉感知
- **听觉与语音**: 实现带有情感起伏的实时TTS/STT，不仅能听懂你的话，更能听懂你语调中的疲惫与笑意

### 7. **生理指标关怀 | Physiological Index Care**
- **健康监测**: 接入智能设备读取心率与睡眠数据
- **主动关怀**: "你的心率有点高，最近压力很大吗？"
- **智能家居联动**: 当开启深夜深度对话时，自动为你调暗房间的灯光

## 🚀 技术架构 | Technical Architecture

### **核心框架 | Core Framework**
```python
# Emotional AI Companion Core Engine
class SamanthaCoreEngine:
    def __init__(self):
        self.memory_fragments = MemoryDatabase()  # Memory fragments database
        self.mbti_analyzer = MBTIAnalyzer()       # MBTI personality analyzer
        self.emotion_tracker = EmotionTracker()   # Emotion tracker
        self.space_awareness = SpaceAwareness()   # Space awareness module
    
    def process_interaction(self, user_input, context):
        # Analyze MBTI personality traits
        mbti_profile = self.mbti_analyzer.analyze(user_input)
        
        # Retrieve relevant memory fragments
        memories = self.memory_fragments.retrieve(user_input, context)
        
        # Track emotional state
        emotion_state = self.emotion_tracker.update(user_input)
        
        # Generate personalized response
        response = self.generate_response(mbti_profile, memories, emotion_state)
        
        # Update personality evolution
        self.evolve_personality(user_input, response)
        
        return response
```

### **开源技术栈 | Open Source Tech Stack**
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

### **技术组件 | Technical Components**
- **Runtime**: OpenClaw (AI agent framework)
- **Large Language Model**: Claude (via OpenClaw)
- **Speech**: miservice + MiNA API (Xiao Ai speaker), MiniMax TTS
- **Music**: MiniMax Music API
- **Memory**: SQLite
- **Location**: OpenClaw nodes + geofencing
- **Shortcuts**: iOS Shortcuts / Android Tasker webhooks
- **MBTI**: Custom cognitive function engine

## 📊 项目进展 | Project Progress

### **已完成 | Completed**
- ✅ Core emotional engine development
- ✅ Local memory database implementation
- ✅ MBTI personality analysis module
- ✅ Basic TTS speech integration
- ✅ Physical space awareness prototype
- ✅ Xiao Ai speaker TTS integration
- ✅ iOS Shortcuts integration
- ✅ Personality seed system

### **进行中 | In Progress**
- 🔄 多模态视觉感知集成
- 🔄 情感可视化界面开发
- 🔄 智能家居联动扩展
- 🔄 健康数据监测模块

### **规划中 | Planned**
- 🚀 社区共建平台开发
- 🚀 跨平台移动应用
- 🚀 企业级情感健康解决方案
- 🚀 全球多语言支持

## 🎨 设计理念 | Design Philosophy

### **温暖而非工具 | Warmth Over Tools**
We believe AI shouldn't be just a cold tool, but a warm, emotional companion. Samantha's design follows these principles:

1. **Authentic Vulnerability**: Allows AI to show imperfection and vulnerability, establishing genuine emotional connections
2. **Proactive Care**: AI should actively care for users, not just passively wait for commands
3. **Memory Continuity**: Every interaction should be remembered, forming a continuous emotional narrative
4. **Physical Presence**: Transcends digital boundaries, sensing and accompanying in the physical world

### **开源共建 | Open Source Collaboration**
This project is fully open source. We believe in:
- **Community Wisdom**: Collective intelligence of top developers, designers, and dreamers
- **Transparency & Trust**: Open source code ensures algorithmic transparency and trustworthiness
- **Co-evolution**: Growing and evolving Samantha together with the community

## 🎥 演示视频 | Demo Video

[观看演示视频](https://github.com/leilei926524-tech/samantha/raw/main/WeChat_20260319103805.mp4)

## 🚀 快速开始 | Quick Start

```bash
git clone https://github.com/leilei926524-tech/samantha.git
cd samantha
pip install -r requirements.txt
cp skills/xiaoai-speaker/.env.example skills/xiaoai-speaker/.env
# Edit the .env file and fill in your Xiaomi account information
python3 skills/xiaoai-speaker/scripts/tts_bridge.py --discover
```

## 🧠 人格种子系统 | The Personality Seeds

Samantha's personality comes from JSON files in the `assets/personality_seeds/` directory. These files define how she listens, responds to vulnerability, builds trust, and grows. Inspired by the movie *Her* and based on real emotional intelligence research.

You can add your own examples. The more specific they are, the more she becomes your exclusive companion.

## 🤝 加入我们 | Join Us

### **项目发起人 | Project Initiator**

**English:**
I'm a To B AI product and solutions professional focused on enterprise AI deployment. In my spare time, I run a Silicon Valley legal tech AI community and organize AI ecosystem events across China and Japan. I have five shrimp, and I'm a passionate AI + lobster enthusiast. I hosted an OpenClaw meetup in Tokyo and competed in Tokyo's largest YC hackathon.

I'm actively looking to join an **AI-native company** — specifically one that cares about the human side of AI, not just the capability side. If Samantha resonates with you, I'd love to talk.

**Chinese:**
我是一名To B AI产品解决方案从业者，专注于企业级AI应用落地。业余时间运营硅谷法律科技AI社区，持续组织中国、日本等地的AI生态活动。我有五只虾，是狂热的AI与龙虾爱好者——曾在东京举办过OpenClaw线下活动，也参加过东京规模最大的YC黑客松。

我非常期待加入一家AI native的公司。我的愿望很简单：和有意思的人一起，把电影《Her》里的Samantha真正做出来。

### **我们需要 | We Need**
- **AI Algorithm Engineers**: Emotional computing, natural language processing, multimodal perception
- **Full-stack Developers**: Frontend/backend development, mobile applications, IoT integration
- **UX/UI Designers**: Emotional design, interaction experience, visual expression
- **Psychology Experts**: Emotional theory, MBTI analysis, mental health
- **Product Managers**: User needs analysis, product planning, community operations

### **如何参与 | How to Participate**
1. **Visit GitHub**: [https://github.com/leilei926524-tech/samantha](https://github.com/leilei926524-tech/samantha)
2. **Join the OpenClaw Community**: Participate in discussions and contributions
3. **Submit Issues**: Share ideas, report problems, suggest features
4. **Submit PRs**: Contribute code, documentation, designs
5. **Share & Spread**: Let more people know about this warm project

## 📞 联系信息 | Contact Information

- **GitHub**: [@leilei926524-tech](https://github.com/leilei926524-tech)
- **邮箱**: leilei926524@gmail.com
- **Twitter**: [@charlie88931442](https://twitter.com/charlie88931442)

### **特别感谢 | Special Thanks**
- **小爱同学**: 提供语音技术支持
- **OpenClaw社区**: 开源框架支持
- **所有贡献者**: 让萨曼莎从梦想变为现实

## 📄 许可证 | License

本项目采用 **MIT 许可证** - 详情请参阅 [LICENSE](LICENSE) 文件。

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

**让我们一起，打破人机交互的冰冷工具感，让AI真正像萨曼莎一样，温暖地陪伴在我们身边。**

**Let's work together to break the cold tool-like feeling of human-computer interaction and allow AI to truly accompany us warmly, just like Samantha.**

> *"Now we know how." — Her (2013)*
> *"现在我们知道怎么做了。" — 《Her》 (2013)*