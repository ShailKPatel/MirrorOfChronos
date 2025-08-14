# MirrorOfChronos: AI-Powered Conversational Time Capsule

> “Chat with the person you used to be.”

---

## 📌 Project Overview

**MirrorOfChronos** is a personalized AI system that enables users to have conversations with a simulation of their past selves. Using a combination of personal writing, messages, social data, and optionally a custom-trained voice model, the system offers a nostalgic and emotional experience — like flipping through a diary, but interactive and alive.

---

I was curious about how I had changed as a person, how my past self would see me now, how my ideals and morals had shifted, and how they might evolve in the future. This project became my way to explore that question.

I chose to solve it by building a mirror of chronology, a system that captures the contours of personality through a detailed form and then feeds that data, along with relevant facts, to a language model for analysis. GPT-OSS-20B was the perfect choice for this purpose because it is open source, lightweight, and capable of strong reasoning, making it ideal for distilling the story of a person’s evolution from raw, structured input.


## 🎯 Objectives

- Recreate a user’s past communication style and personality using their historical data.
- Allow users to “talk” to their younger self through a conversational interface.
- Optionally generate a synthetic voice to simulate how they used to sound.
- Provide users with emotional insights and life reflections via AI-driven interactions.

---

## 🛠️ Tech Stack

| Component           | Tech Used                      |
|---------------------|--------------------------------|
| NLP Model           | GPT-2 / DistilGPT + Fine-tuning |
| Voice Model         | Bark / ElevenLabs / Coqui TTS (optional) |
| Data Processing     | Python, Pandas, Regex, NLTK     |
| Frontend UI         | Streamlit / Gradio             |
| Text-to-Speech      | TTS + voice cloning (optional) |
| Backend             | Flask / FastAPI (optional)     |
| Storage             | Local / Firebase / SQLite      |

---

## 🧩 System Components

### 1. 🗃️ **Data Collection**

We’ll gather data from the following sources:

#### a. Social Media Exports (Text Data)
- Twitter (`https://twitter.com/settings/download_your_data`)
- Facebook (`https://www.facebook.com/dyi`)
- Instagram (captions, comments, DMs)
- WhatsApp/Telegram chat exports

#### b. Journals / Notes
- Manual text uploads or scanned text (OCR)
- Markdown, TXT, DOCX formats accepted

#### c. Emails (Optional)
- Gmail export via [Google Takeout](https://takeout.google.com/)

#### d. Custom Questionnaire
- Heavy personality questionnaire to extract worldview, writing tone, and habits.
- Includes questions like:
  - “What was your biggest insecurity at 18?”
  - “Describe your ideal weekend at 21.”
  - “Write a letter to your future self.”

#### e. Voice Recording (Optional)
- Guided script for users to read 30–60 sentences aloud
- Used for training a basic voice model
- Text-to-Speech Tools: Bark / ElevenLabs / Coqui TTS

---

### 2. 🧼 **Data Preprocessing**

- Clean and anonymize personal data
- Normalize text (remove emojis, excessive punctuation)
- Label datasets with timestamps if available (to track “age” or time period)
- Create prompts + responses from chat histories (fine-tuning format)

---

### 3. 🤖 **Model Training & Tuning**

#### a. Text Model (Past Self Simulation)
- Fine-tune GPT-2 or DistilGPT on:
  - Cleaned journals, chat data, questionnaire responses
- Pre-trained embeddings (optionally from SentenceTransformers) to simulate semantic memory

#### b. Voice Cloning (Optional)
- Use Bark / Coqui TTS for lightweight training
- User reads guided scripts to build a voice profile
- Output: TTS engine that generates audio of the “past voice” based on AI text

---

### 4. 💬 **Conversational Interface**

#### a. Chat Frontend
- Built with Streamlit or Gradio
- Customizable UI with:
  - “Talk to 16-Year-Old Me”
  - “Ask Me in 2019”
  - “Life Advice from My Past Self”

#### b. Voice Mode (Optional)
- Toggle TTS output in user’s cloned voice
- Option to export chatlogs as audio files

---

### 5. 📈 Additional Features (Optional)

- **Mood Drift Visualization**: Analyze sentiment changes over time
- **Lexical Changes**: Show how vocabulary evolved
- **Memory Highlights**: Summarize themes from the past (e.g., “2018 was a year of self-doubt”)
- **Chat Time Simulation**: AI mimics your attitude from specific years

---

## 🔐 Privacy & Ethics

- Data is stored locally by default or securely on encrypted cloud.
- Option to delete all data at any time.
- Only user-owned or consent-based data allowed.
- No data is shared externally or used for training other models.


---

## 📦 Example Use Case

**Sarah, 25**, uploads her journals and chat logs from high school and fills out a personal survey. A week later, she logs into *MirrorOfChronos* and starts a conversation with *“17-Year-Old Sarah.”* She types:
> “Hey, do you still worry about college stuff?”

And gets a reply in her younger voice:
> “Ugh yeah… I keep thinking I’ll screw up my SATs. But I *really* wanna go to NYU.”

---


All in a way that’s *memorable, impactful,* and technically solid.

---
