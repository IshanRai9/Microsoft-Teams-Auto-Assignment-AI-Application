# Microsoft Teams Auto Assignment AI Application

An AI-powered automation tool that integrates with Microsoft Teams to fetch your upcoming assignments and auto-generates assignment content using AI. The output is saved in a pre-defined Word template at your specified local path.

---

## 🚀 Features

- 🔐 Authenticates with your Microsoft Teams account using Microsoft Graph API
- 📅 Fetches upcoming assignments from Teams
- 🧠 Uses AI (OpenAI or Hugging Face) to generate detailed assignment content
- 📄 Saves the content to a Word document using a custom template
- 🌐 Frontend interface with Streamlit for manual control and visualization
- 🖥️ Optional: Generate a standalone `.exe` for local execution

---

## 📁 Project Structure
```
teams-assignment-ai/
│
├── backend/ # Core logic
│ ├── graph_auth.py # Handles Microsoft Graph authentication
│ ├── assignment_fetcher.py # Fetches Teams assignments
│ ├── ai_generator.py # AI-based content generation
│ ├── word_generator.py # Word document creation
│ └── main.py # CLI runner
│
├── templates/
│ └── assignment_template.docx # Word template file
│
├── output/ # Auto-generated Word documents
│
├── frontend/ # Streamlit GUI
│ ├── app.py # Streamlit app
│ └── style.css # (Optional) Custom styling
│
├── .env # Environment variables
├── requirements.txt # Python dependencies
└── README.md
```

---

## ⚙️ Prerequisites

### 🔑 Accounts Required
- Microsoft 365 Account (with Teams)
- Azure Developer Account (for Graph API)
- OpenAI API Key (or Hugging Face if using free models)

### 💻 Software Requirements
- Python 3.10+
- Node.js 18+ (only for initial Azure app setup if needed)
- Streamlit (for frontend)

---

## 📦 Installation

### 1. Clone the Repo
```bash
git clone https://github.com/yourusername/teams-assignment-ai.git
cd teams-assignment-ai
```
2. Install Python Requirements
```
pip install -r requirements.txt
```
3. Setup .env File
Create a .env file in the backend/ folder:
```
CLIENT_ID=your-microsoft-app-id
CLIENT_SECRET=your-microsoft-app-secret
TENANT_ID=your-tenant-id
REDIRECT_URI=http://localhost:8000/
OPENAI_API_KEY=your-openai-key
```
💡 You can get these credentials by registering your app on Azure Portal.

🧪 How to Use
CLI Version
```bash
cd backend
python main.py
```
This will:

Authenticate your account via browser popup

Fetch your upcoming Teams assignments

Use AI to generate content based on the assignment

Save it as a Word file in the output/ folder

GUI Version (Recommended)
```bash
cd frontend
streamlit run app.py
```

This will launch a local web app where you can:

Fetch assignments

View instructions

Generate Word files on button click

📂 Output is saved to output/ directory.

🧠 AI Models Supported
OpenAI GPT (e.g., gpt-3.5-turbo)

Hugging Face Transformers (e.g., mistralai/Mixtral for free use)

To use Hugging Face, you’ll need to:

Update ai_generator.py

Install transformers and sentencepiece

📄 Word Template
Your Word template must be placed at:

```
templates/assignment_template.docx
```
You can design the template using placeholders and standard formatting.

🖥️ Create Standalone App (.exe)
```bash
pip install pyinstaller

# Create entrypoint
echo "import os\nos.system('streamlit run frontend/app.py')" > main_gui.py

# Build executable
pyinstaller --onefile main_gui.py
```
Your .exe file will be in dist/.

🔐 Permissions Required in Azure App
Make sure your Azure App has these API Permissions:

EduAssignments.ReadBasic

EduAssignments.Read

Tasks.Read

EduAssignments.ReadWrite (optional for future features)

🧩 To-Do / Future Improvements
 Add document upload preview for assignments with attachments

 Enable login via frontend GUI

 Add option to use different AI models

 Save generation history

🆓 Licensing & Credits
🧠 AI by OpenAI or Hugging Face

🧾 Word Document Generation via python-docx

🎨 UI via Streamlit

🔐 Authentication via msal + Microsoft Graph

This project is free and open-source under the MIT License.

🤝 Contributions
PRs and suggestions are welcome! Please open issues for bugs or improvements.

📬 Contact
Made by Ishan Rai
📧 ishanrai1109@gmail.com
