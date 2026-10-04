💊 MedSnap
Your Camera Knows the Pill. MedSnap Explains the Rest.
MedSnap is an AI-powered medicine information assistant built with
Streamlit, Google Gemini, and Twilio WhatsApp. Users can upload a
photo of a medicine/tablet or enter a medicine-related question, and
MedSnap provides simple information about what the medicine appears to
be, its common purpose, benefits, side effects, and important
precautions.
⚠️ Medical safety: MedSnap is an information assistant, not a
doctor. It does not diagnose conditions, prescribe medicines,
recommend dosages, or tell users to start, stop, or change prescribed
medication.

✨ Features
- 📸 Medicine image analysis --- Upload JPG, JPEG, or PNG images
  of medicines/tablets.
- 💬 Text-based medicine questions --- Ask about medicines using
  natural language.
- 🤖 AI-powered explanations --- Uses Google Gemini to analyze the
  supplied text or image.
- 💊 Structured medicine information --- Explains:
  - What the medicine appears to be
  - Common purpose / general use
  - Common benefits or effects
  - Common side effects
  - Important precautions and warnings
  - Whether identification is certain or estimated
- 📲 WhatsApp summary --- Summarizes medicines discussed during
  the session and sends the summary to the user's WhatsApp number
  through Twilio.
- 🛡️ Safety-focused responses --- Unclear medicine images are
  treated as uncertain, and serious symptoms or reactions are directed
  to qualified healthcare professionals.
🧠 How It Works
User
  │
  ├── Medicine Photo ──────┐
  │                        │
  └── Text Question ───────┤
                           ▼
                    Streamlit Interface
                           │
                           ▼
                     Google Gemini
                           │
                           ▼
                 Medicine Information
                           │
                  ┌────────┴────────┐
                  ▼                 ▼
             Chat Response     Daily Summary
                                      │
                                      ▼
                                Twilio WhatsApp
🛠️ Tech Stack
  Technology        Purpose
  Python            Application logic
  Streamlit         Web interface and chat UI
  Google Gemini     AI-powered medicine analysis and summaries
  google-genai    Gemini API integration
  Twilio            WhatsApp messaging
  twilio          Python SDK for Twilio
  python-dotenv   Optional environment/configuration support
The application imports Google GenAI, Streamlit, and Twilio in the main
application, while the project dependencies are listed in
requirements.txt.
📁 Project Structure
MedSnap/
│
├── app.py
├── prompts.py
├── requirements.txt
├── .gitignore
└── .streamlit/
    └── secrets.toml
app.py
Contains the main Streamlit application, Gemini client, Twilio client,
chat interface, image upload handling, AI requests, and WhatsApp summary
delivery.
prompts.py
Contains the MedSnap system prompt, welcome message, and WhatsApp
summary prompt. The system prompt restricts the assistant to
medicine-related information and includes explicit safety boundaries.
requirements.txt
Contains the Python packages required to run the application.
.streamlit/secrets.toml
Stores API credentials and service configuration. This file should never
be committed to Git.
⚙️ Prerequisites
Before running MedSnap, make sure you have:
- Python 3.10+
- A Google Gemini API key
- A Twilio account with WhatsApp messaging configured
- A Twilio WhatsApp sender
- A Twilio Content Template SID
🚀 Installation
1. Clone the repository
git clone <your-repository-url>
cd MedSnap
2. Create a virtual environment
python -m venv venv
Activate it on Windows:
venv\Scripts\activate
On macOS/Linux:
source venv/bin/activate
3. Install dependencies
pip install -r requirements.txt
The current dependency list includes google-genai, streamlit, and
twilio.
4. Configure Streamlit secrets
Create:
.streamlit/secrets.toml
Add:
GEMINI_API_KEY = "your_gemini_api_key"

TWILIO_ACCOUNT_SID = "your_twilio_account_sid"
TWILIO_AUTH_TOKEN = "your_twilio_auth_token"
TWILIO_WHATSAPP_FROM = "your_twilio_whatsapp_sender"
TWILIO_CONTENT_SID = "your_twilio_content_template_sid"
The application reads these values through st.secrets.
5. Run the application
streamlit run app.py
Open the Streamlit URL shown in your terminal.
📱 Using MedSnap
1. Enter your name.
2. Enter your WhatsApp number with the country code.
3. Start the MedSnap chat.
4. Upload a medicine photo or type a medicine-related question.
5. Review the AI-generated information.
6. Use Send to WhatsApp to receive a concise summary of the
   medicines discussed.
🔐 Safety & Privacy
MedSnap is designed with medicine-information safety boundaries:
- It does not claim that a medicine is definitely safe or appropriate
  for a user.
- It does not diagnose diseases.
- It does not prescribe medicines.
- It does not recommend dosages.
- It does not instruct users to start, stop, or change prescribed
  medication.
- If an image is unclear, it asks for a clearer image instead of
  confidently identifying the medicine.
- Serious symptoms or medication reactions should be handled by a
  qualified healthcare professional or urgent medical service.
Do not commit API keys, authentication tokens, or other secrets to the
repository. The project's .gitignore excludes Streamlit secrets,
virtual environments, Python cache files, and .pyc files.
⚠️ Limitations
AI-based medicine identification can be uncertain, especially when:
- The tablet or packaging is partially visible.
- Text on the packaging is blurry.
- The medicine has similar-looking alternatives.
- The image does not contain enough identifying information.
Always verify important medication information with the packaging, a
pharmacist, doctor, or other qualified healthcare professional.
🌟 Future Possibilities
Potential extensions include:
- 🌐 Multilingual medicine explanations
- 🔊 Voice-based medicine assistance
- 🧾 Prescription and medicine-list organization
- ⏰ Medication reminder workflows
- 📊 Personal medicine history
- 🏥 Pharmacy or healthcare-provider integration
- 🔎 Verified medicine information from trusted medical databases
- ♿ Accessibility-first voice and large-text interfaces
