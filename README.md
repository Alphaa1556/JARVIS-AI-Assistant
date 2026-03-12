J.A.R.V.I.S 🤖
Just A Rather Very Intelligent System
Built for CSE (AI & ML) Students — Beginner Friendly

📁 Project Structure
JARVIS/
│
├── jarvis.py              ← Main entry point (RUN THIS)
├── register_face.py       ← Register your face (run once)
├── requirements.txt       ← All Python packages needed
│
├── modules/
│   ├── voice_engine.py    ← STT (listen) + TTS (speak)
│   ├── ai_brain.py        ← Gemini AI for intelligence
│   ├── skill_router.py    ← Maps commands to actions
│   ├── face_vision.py     ← Face recognition + object detection
│   └── display.py         ← Terminal HUD display
│
└── data/
    ├── memory.json        ← Conversation history (auto-created)
    └── known_faces.pkl    ← Registered face encodings (auto-created)

⚡ Quick Setup (Step by Step)
Step 1 — Open in VS Code
File → Open Folder → Select the JARVIS folder
Step 2 — Create a virtual environment
Open the VS Code terminal (Ctrl + `) and run:
bash# Create venv
python -m venv venv

# Activate it
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate
Step 3 — Install dependencies
bashpip install -r requirements.txt

⚠️ If pyaudio fails on Windows:
bashpip install pipwin
pipwin install pyaudio

Step 4 — Get your FREE Gemini API Key

Go to → https://aistudio.google.com/app/apikey
Click "Create API Key"
Copy the key
Open modules/ai_brain.py
Replace "YOUR_API_KEY_HERE" with your key:

python   GEMINI_API_KEY = "AIza...your_key_here"
Step 5 — Register your face (optional but cool!)
bashpython register_face.py
Look at your webcam and press Q when done.
Step 6 — Run JARVIS!
bashpython jarvis.py
```

---

## 🎙️ Voice Commands

| Say this...                    | JARVIS does this               |
|-------------------------------|-------------------------------|
| `Hey JARVIS` + any question   | Answers using Gemini AI        |
| `Hey JARVIS, what time is it` | Tells the current time         |
| `Hey JARVIS, open YouTube`    | Opens YouTube in browser       |
| `Hey JARVIS, open Google`     | Opens Google in browser        |
| `Hey JARVIS, search...`       | Google searches your query     |
| `Hey JARVIS, who am I`        | Activates face recognition     |
| `Hey JARVIS, what do you see` | Detects objects with YOLOv8    |
| `Hey JARVIS, clear memory`    | Wipes conversation history     |
| `Hey JARVIS, shutdown`        | Turns off JARVIS               |

---

## 🧠 How JARVIS Works (Flow Diagram)
```
🎤 You speak
     ↓
[Wake Word Check] — "jarvis" detected?
     ↓ YES
[Speech-to-Text] — Whisper/Google converts audio → text
     ↓
[Skill Router] — Does it match a known command?
     ↓ YES                    ↓ NO
[Run Skill]             [AI Brain (Gemini)]
(time, browser,          Understands context,
 face scan, etc.)        generates smart reply
     ↓                         ↓
[Text-to-Speech] — JARVIS speaks the response
     ↓
🔊 You hear JARVIS

➕ How to Add Your Own Skill
Open modules/skill_router.py and:
1. Write your function:
pythondef skill_weather(self):
    self.voice.speak("Checking weather...")
    # Add weather API call here
    self.voice.speak("It's 32 degrees and sunny in Mumbai.")
2. Register trigger words:
pythonself.skill_map = {
    # ... existing skills ...
    "weather":       self.skill_weather,
    "temperature":   self.skill_weather,
    "how hot":       self.skill_weather,
}
Done! JARVIS now responds to "weather", "temperature", and "how hot".

🚀 Upgrade Path (as you learn more)
When you're ready...Upgrade to...Better STT accuracy (offline)OpenAI WhisperPremium JARVIS voiceElevenLabs APIWake word without saying "jarvis"Porcupine by PicovoiceLong-term memoryChromaDB (vector database)Emotion detectionDeepFace libraryHand gesture controlMediaPipeSmart home controlHome Assistant API

🐛 Troubleshooting
Microphone not working?

Check your mic is connected and set as default input device
Try adjusting energy_threshold in voice_engine.py (increase if too sensitive)

pyaudio installation fails on Windows?
bashpip install pipwin
pipwin install pyaudio
face-recognition install fails?
bashpip install cmake
pip install dlib
pip install face-recognition
JARVIS doesn't understand me?

Speak clearly and not too fast
Make sure you say the wake word ("JARVIS" or "Hey JARVIS") first
Reduce background noise


📚 Learning Resources

Python basics: https://docs.python.org/3/tutorial/
SpeechRecognition docs: https://pypi.org/project/SpeechRecognition/
Gemini API: https://ai.google.dev/docs
YOLOv8 docs: https://docs.ultralytics.com
face_recognition: https://github.com/ageitgey/face_recognition


📄 License
MIT License — free to use, modify, and share.

Built with Python 3.10+ | CSE AI&ML Project
