# 🎵 AI Music Studio
### *Create, edit, and export full songs with AI — directly from your browser.*

---

## 🚀 Overview
**AI Music Studio** is a full-stack music creation platform powered by artificial intelligence.  
It’s designed to feel like FL Studio — but built for the web and mobile.  
Users can generate **lyrics**, **beats**, and **vocals**, edit them via natural language prompts, and export **studio-quality** WAV or MP3 files.

---

## 🧠 Features
- 🎶 **Beat Generation** – Create full instrumentals from text prompts  
- ✍️ **Lyric Writing** – Generate custom song lyrics in any genre or emotion  
- 🎤 **AI Vocals** – Choose artist styles or upload references for vocal tone  
- 🎚️ **Auto Mixing & Mastering** – Studio-quality sound using Waves-style chains  
- 🔉 **Audio Playback Feed** – Listen to AI creations before export  
- 💾 **Download Options** – Export WAV, MP3, and individual stems  
- 🧩 **Remaster Mode** – Reprocess finished songs with improved loudness + clarity  
- 🛠️ **Built-in Studio** – Edit vocals or beats via new prompts  
- 🤝 **Collaboration** – Work together on projects in real time or asynchronously  

---

## 🏗️ Architecture
Frontend (React / Next.js)
│
├── Prompt inputs, lyric editor, playback controls, studio interface
│
Backend (Node.js + Express)
│
├── Routes for AI generation, file upload, mastering, and exports
│
├── Integrations:
│     ├─ OpenAI (lyrics)
│     ├─ Replicate (beats/vocals)
│     ├─ LALAL.ai (stem separation)
│     ├─ Dolby.io (mastering)
│
Storage:
│     ├─ PostgreSQL (users, projects, sessions)
│     └─ AWS S3 (audio/stems)

---

## 🧰 Tech Stack

| Layer | Technology |
|-------|-------------|
| **Frontend** | React / Next.js |
| **Backend** | Node.js (Express) |
| **Database** | PostgreSQL (Neon.tech or Supabase) |
| **Storage** | AWS S3 |
| **AI APIs** | OpenAI, Replicate, LALAL.ai, Dolby.io |
| **Auth** | Firebase Auth or Clerk.dev |
| **Hosting** | Vercel (frontend) + Render / Railway (backend) |

---

## ⚙️ Installation

### 1️⃣ Clone the repo
```bash
git clone https://github.com/yourusername/ai-music-studio.git
cd ai-music-studio
```

### 2️⃣ Backend Setup
```bash
npm install express cors axios dotenv multer pg aws-sdk openai
```

**Create `.env`**
```env
OPENAI_API_KEY=your_key_here
REPLICATE_API_TOKEN=your_key_here
AWS_ACCESS_KEY_ID=your_key_here
AWS_SECRET_ACCESS_KEY=your_key_here
AWS_BUCKET_NAME=your_bucket
DOLBY_API_KEY=your_key_here
PORT=5000
```

**Start the server**
```bash
node server.js
```

---

### 3️⃣ Frontend Setup
```bash
cd ai-music-frontend
npm install
npm install axios wavesurfer.js
npm start
```

Your frontend runs on **`http://localhost:3000`**  
Backend runs on **`http://localhost:5000`**

---

## 🧩 Folder Structure
```
/ai-music-studio
 ├── server.js
 ├── /controllers
 │    ├── lyricController.js
 │    ├── beatController.js
 │    └── fileController.js
 ├── /routes
 │    ├── lyricRoutes.js
 │    ├── beatRoutes.js
 │    └── uploadRoutes.js
 ├── /uploads
 └── .env

/ai-music-frontend
 ├── /src
 │    ├── /components
 │    │    ├── PromptInput.jsx
 │    │    ├── AudioPlayer.jsx
 │    ├── /pages
 │    │    ├── Studio.jsx
 │    ├── App.jsx
 └── package.json
```

---

## 🧠 Example API Endpoints

### Generate Lyrics (OpenAI)
**POST** `/api/lyric/generate`
```json
{
  "prompt": "Write a pop chorus about confidence and freedom"
}
```

### Generate Beat (Replicate)
**POST** `/api/beat/generate`
```json
{
  "prompt": "Create a 90 BPM R&B beat with warm pads and smooth drums"
}
```

### Upload Reference Audio
**POST** `/api/upload`
(form-data: `file`)

---

## 🎚️ Audio Flow
1. User enters prompts for **lyrics** + **beats**  
2. Backend sends them to **OpenAI** and **Replicate** APIs  
3. AI audio is returned and uploaded to **S3**  
4. Playback via **Wavesurfer.js** in browser  
5. Mastering and export options available (Dolby.io or internal mix chain)

---

## 📦 Environment Variables
```
OPENAI_API_KEY=sk-xxxxxxxx
REPLICATE_API_TOKEN=r8_xxxxxxxx
AWS_ACCESS_KEY_ID=xxxx
AWS_SECRET_ACCESS_KEY=xxxx
AWS_BUCKET_NAME=my-audio-bucket
DOLBY_API_KEY=dby_xxxxxx
PORT=5000
```

---

## 💽 Future Features
- 🎤 **Voice cloning** (ElevenLabs / OpenVoice)
- 🧑‍🤝‍🧑 **Live collaboration** (Socket.io)
- 🎛️ **Visual mixer UI** (EQ, compression, reverb)
- 📊 **Project history + version control**
- 📱 **Mobile PWA** for song creation on-the-go
- 🎵 **Genre preset packs** (lo-fi, trap, EDM, pop, R&B)
- ☁️ **AI mastering presets** (Radio, Club, Chill)

---

## 🛠️ Example Prompts

**Beat Prompt:**
> “Create a 95 BPM trap beat with hard 808s, layered snares, and dark piano chords.”

**Lyric Prompt:**
> “Write a hook about chasing your dreams, in a melodic R&B tone.”

**Edit Prompt:**
> “Make the vocals more energetic with double tracking and slight reverb.”

**Remaster Prompt:**
> “Remaster for streaming with warmer bass, brighter highs, and -14 LUFS target.”

---

## 🧩 Integration Diagram
```plaintext
[ User Prompt ]
     ↓
[ React Frontend ]
     ↓
[ Node.js Backend ]
     ├── OpenAI → Lyrics
     ├── Replicate → Beats/Vocals
     ├── Dolby.io → Mastering
     ├── AWS S3 → Storage
     ↓
[ Playback / Download ]
```

---

## ☁️ Deployment
| Component | Service | Description |
|------------|----------|--------------|
| **Frontend** | [Vercel](https://vercel.com) | Deploy React app |
| **Backend** | [Render](https://render.com) / [Railway](https://railway.app) | Run Node server |
| **Database** | [Neon.tech](https://neon.tech) / [Supabase](https://supabase.com) | PostgreSQL |
| **Storage** | [AWS S3](https://aws.amazon.com/s3/) | Audio files |
| **Domain** | [Namecheap](https://namecheap.com) / [Cloudflare](https://cloudflare.com) | Custom domain |

---

## 🧑‍💻 Contributing
1. Fork this repo  
2. Create a new branch: `feature/your-feature-name`  
3. Commit your changes  
4. Push and submit a pull request

---

## 📄 License
MIT License © 2025 [Your Name or Organization]

---

## 🌟 Credits
- [OpenAI](https://openai.com) – Lyrics + text generation  
- [Replicate](https://replicate.com) – Music and vocal generation  
- [Dolby.io](https://dolby.io) – Audio mastering  
- [LALAL.ai](https://www.lalal.ai/) – Stem separation  
- Inspired by digital audio workstations like FL Studio, Logic, and Ableton Live

---

## 🧭 Roadmap (Phased Development)

| Phase | Goal | Description |
|-------|------|-------------|
| **1. MVP** | Text-to-Lyric & Beat Generation | Generate songs with playback and export |
| **2. Studio** | Prompt-based Editing | Regenerate sections, vocal edits |
| **3. Mastering** | Add remaster & mixing chains | Auto-engineered audio |
| **4. Collaboration** | Realtime Sessions | Multi-user editing |
| **5. Monetization** | Subscription & Cloud Credits | Unlock advanced AI models |

---

**Built with ❤️ for musicians, producers, and creators everywhere.**
