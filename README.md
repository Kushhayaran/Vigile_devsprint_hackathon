# Vigile_devsprint_hackathon
🛡️ VIGILE: The Smart AI Chat ModeratorVIGILE is a real-time chat moderation layer designed to keep digital conversations safe, professional, and engaging. It acts as an intelligent middleware between users and chat interfaces, utilizing Google Gemini's advanced LLMs to detect toxicity and suggest polite alternatives instantly.🚀 Key FeaturesDual-Threshold Moderation: Uses a "Warning Threshold" for mild rudeness and a "Hard-Gate" for blocking severe toxicity.Real-Time Toxicity Scoring: Evaluates every message on a granular 0–10 scale using Google Gemini.Intelligent Rephrasing: Instead of simple redaction, VIGILE provides AI-generated professional suggestions to help users communicate better.Emergency Bypass: Includes a pre-vetted list of common greetings to minimize latency and API calls for safe interactions.Live Admin Feed: A dedicated sidebar log that allows administrators to audit moderation actions and toxicity scores in real-time.🛠️ Technical StackFrontend: Streamlit (Python-based Web UI).AI Engine: Google Gemini API (2.0 & 1.5 Flash models).Environment Management: python-dotenv and Streamlit Secrets for secure API key handling.Data Structure: JSON-based structured output to ensure high-fidelity moderation data.📂 Project StructurePlaintextvigile-moderator/
├── .streamlit/
│   └── secrets.toml     # Config for Streamlit Cloud deployment
├── app.py               # Main application logic (VIGILE engine)
├── .env                 # Local API Key storage (DO NOT COMMIT)
├── .gitignore           # Prevents sensitive files from being uploaded
└── requirements.txt     # List of Python dependencies
⚙️ Setup & InstallationClone the Repository:Bashgit clone https://github.com/yourusername/vigile-moderator.git
cd vigile-moderator
Install Dependencies:Bashpip install streamlit google-genai python-dotenv
Configure API Key:Create a .env file in the root directory and add your Google AI Studio API Key:PlaintextGemini_api_key=your_api_key_here
Run the Application:Bashstreamlit run app.py
📊 How It Works (The Logic Gate)VIGILE follows a specific decision tree to ensure conversation flow while maintaining safety:AI ScoreStatusAction Taken0 - 3SAFEDelivered normally.4 - 6WARNINGDelivered with a behavioral warning.7 - 10BLOCKIntercepted; user is shown a polite rephrased version.🛡️ Security & Best PracticesAPI Key Rotation: We recommend using Streamlit's native "Secrets" feature for cloud deployment to prevent API key leaks on GitHub.Model Redundancy: The app is configured with a fallback loop (Gemini 2.0 -> 1.5) to ensure 100% uptime even during rate-limiting events.
