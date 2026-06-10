# 👻 SPECTR-OS — AI-Powered Paranormal Investigation Web App

> An interactive ghost-hunting simulator powered by the **Claude AI (Anthropic)** API — featuring live camera scanning, real-time generative AI responses, and animated paranormal sensor readouts.

🔗 **Live Demo:** [spectr-os.netlify.app](https://spectr-os.netlify.app) *(update with your actual URL)*  
🛠️ **Tech Stack:** HTML · CSS · JavaScript · Claude API (Anthropic) · WebRTC · Netlify

---

## 🧠 What Makes This a GenAI Project

This project is a **real-world demonstration of LLM API integration**:

- Calls the **Anthropic Claude API** in real time to generate context-aware, dynamic responses
- Implements **prompt engineering** — crafting structured prompts that guide Claude to respond in character as a "Spectral Oracle"
- Processes **live environmental inputs** (camera feed, sensor states) and passes them as context to the LLM
- Handles **asynchronous API calls**, streaming responses into the UI without page reloads

---

## ✨ Features

| Feature | Description |
|---|---|
| 🎥 **Live Camera Scanning** | WebRTC camera access for real-time environment capture |
| 🤖 **Spectral Oracle (Claude AI)** | LLM-powered entity that generates unique, context-aware spirit responses |
| 📡 **EMF / EVP / Motion Sensors** | Animated sensor readouts reacting to simulated paranormal activity |
| 👁️ **Entity Classification** | AI-driven detection and categorisation of paranormal entities |
| 🌐 **Deployed on Netlify** | Live, publicly accessible web application |

---

## 🏗️ Architecture

```
User Input / Camera Feed
        ↓
Sensor State Engine (JS)
        ↓
Prompt Builder → Claude API (Anthropic) → Spectral Oracle Response
        ↓
Animated UI (EMF / EVP meters + entity readout)
```

---

## 🔧 How It Works

### 1. Prompt Engineering
The app constructs dynamic prompts based on sensor readings and user interactions:

```javascript
const prompt = `
  You are a Spectral Oracle — an ancient AI entity that perceives paranormal activity.
  Current sensor readings: EMF Level: ${emfLevel}, Motion Detected: ${motionDetected}
  Respond in 2-3 sentences as the Oracle, describing what entity is present.
`;
```

### 2. Claude API Integration
```javascript
const response = await fetch("https://api.anthropic.com/v1/messages", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    model: "claude-sonnet-4-20250514",
    max_tokens: 200,
    messages: [{ role: "user", content: prompt }]
  })
});
const data = await response.json();
const oracleResponse = data.content[0].text;
```

### 3. WebRTC Camera Access
```javascript
const stream = await navigator.mediaDevices.getUserMedia({ video: true });
videoElement.srcObject = stream;
```

---

## 🚀 Getting Started

### Prerequisites
- A modern browser (Chrome / Firefox / Edge)
- Anthropic API key → [Get one here](https://console.anthropic.com)

### Run Locally
```bash
git clone https://github.com/monishasreerama/spectr-os.git
cd spectr-os
# Open index.html in your browser
# Add your Anthropic API key in config.js
```

### Deploy on Netlify
```bash
# Drag and drop your project folder to netlify.com/drop
# Or connect your GitHub repo for auto-deploy
```

---

## 📁 Project Structure

```
spectr-os/
├── index.html          # Main app UI
├── style.css           # Animations & sensor styling
├── app.js              # Core logic — API calls, WebRTC, sensor engine
├── config.js           # API key configuration
└── README.md
```

---

## 💡 Key Learnings & Skills Demonstrated

- ✅ **LLM API Integration** — Real Anthropic Claude API calls in a production web app
- ✅ **Prompt Engineering** — Dynamic, context-aware prompt construction
- ✅ **Async JavaScript** — Handling API responses without blocking the UI
- ✅ **WebRTC** — Browser-based camera access without any backend
- ✅ **Deployment** — Live app hosted on Netlify with CI/CD

---

## 🙋‍♀️ About

Built by **Sreerama Monisha** — B.Tech AI & ML (2026), Sri Sri University  
📧 monishasreerama@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/monishasreerama8) · [GitHub](https://github.com/monishasreerama)

---

> *"Where machine learning meets the unexplained."*