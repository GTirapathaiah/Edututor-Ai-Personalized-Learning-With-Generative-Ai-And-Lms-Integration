# 🎓 EduTutor AI: Personalized Learning with Generative AI and LMS Integration
---

## Project Overview:
EduTutor AI is a cloud-based, AI-powered educational platform that revolutionizes how students learn and educators assess. Built using IBM Watsonx, Granite foundation models, Google Classroom APIs, Pinecone vector DB, and Streamlit, this project demonstrates a modular, intelligent, and adaptive learning ecosystem.

**At its core, EduTutor AI aims to:**

* **Personalize Learning Paths:** Leverage generative AI to create dynamic, tailored learning experiences for each student based on their individual progress, strengths, and weaknesses.
* **Automate Assessment and Feedback:** Streamline the assessment process for educators by automatically generating quizzes, evaluating responses, and providing insightful feedback.
* **Integrate Seamlessly with Existing LMS:** Connect with popular learning management systems like Google Classroom to synchronize class data, assignments, and student information.
* **Provide Data-Driven Insights:** Utilize a vector database to store and analyze student performance data, enabling educators to gain deeper insights into learning patterns and identify areas for intervention.
* **Enhance Engagement:** Offer an interactive and adaptive learning environment that keeps students motivated and engaged with the learning material.

## Project Architecture

```bash
EDUTUTOR-AI/
├── .streamlit/                     # Streamlit credentials & secrets
│   ├── client_secret.json
│   └── secrets.toml
│
├── backend/                        # FastAPI backend logic
│   ├── routes/                     # Route handlers for API endpoints
│   │   ├── auth.py
│   │   ├── educator.py
│   │   ├── quiz.py
│   │   ├── submission.py
│   │   ├── user.py
│   │   └── user_auth.py
│   │
│   ├── services/                   # Services for external integrations
│   │   ├── llm_service.py          # Watsonx / Granite model logic
│   │   └── vector_service.py       # Pinecone vector search logic
│   │
│   ├── utils/                      # Helper and auth logic
│   │   ├── api.py
│   │   ├── auth.py
│   │   ├── session.py
│   │   └── watsonx_auth.py
│   │
│   ├── .env                        # Environment variables
│   ├── main.py                     # FastAPI entry point
│   └── students.db                 # SQLite database file (or used for local storage)
│
├── frontend/                       # Streamlit frontend
│   ├── pages/                      # Individual UI screens
│   │   ├── google_login.py
│   │   ├── students_dashboard.py
│   │   └── take_quiz.py
│   ├── app.py                      # Main app file
│   └── static/                     # Static assets like CSS/images
│       └── style.css
│
├── requirements.txt                # Python dependencies
├── README.md                       # Project documentation
└── venv/                           # Python virtual environment

🔧 Technologies Used
🧠 IBM Watsonx (Granite LLM via LangChain)

🚀 FastAPI + Uvicorn

📊 Pinecone Vector DB

🌐 Google Classroom API

🖥️ Streamlit (Role-based Dashboards)

🔐 OAuth (Google Auth)

📦 Python Environment Management with venv

📽️ Demo Video
Because of GitHub’s file size limitations, you can watch the full working demo of EduTutor AI here:

▶️ [Click to Watch the Demo on Google Drive]:https://drive.google.com/drive/folders/1-IwiUbY5DNPC8y0cg2315G4-1waaFpM-?usp=sharing

💫 Project Workflow:
Requirement Setup
Technologies used:

fastapi, uvicorn

langchain_ibm

pinecone-client

streamlit

google-auth-oauthlib

google-api-python-client

python-dotenv

Install them via:

Bash

pip install -r requirements.txt
Environment Initialization
.env file stores all keys securely for:

IBM Watsonx

Pinecone DB

OAuth credentials

FastAPI Backend
Handles student/educator login, quiz generation, answer evaluation, classroom sync, and metadata updates. It serves as the central API for all frontend and external service interactions.

IBM Watsonx AI Integration
Granite model loaded via langchain_ibm.WatsonxLLM

LangChain PromptTemplate dynamically forms questions based on learning materials and student progress.

Output parsed into quiz-ready JSON format for seamless integration with the quiz generation module.

Google Classroom Sync
Login via Google OAuth ensures secure access to user accounts.

Retrieve class names, topics, and student data using Classroom APIs to keep EduTutor AI synchronized with existing course structures.

Facilitates easy assignment creation and result publishing back to Google Classroom.

Pinecone Integration
Embeddings are stored for each user, representing their knowledge state and learning patterns.

Metadata such as quiz scores, topics covered, and dates are associated with these embeddings.

Vector similarity searches are used for personalized quiz suggestions, adaptive learning path recommendations, and identifying knowledge gaps.

Streamlit Frontend
Student Panel
Google/Manual Login provides flexible access for students.

Personalized Dashboard displays progress, recommended quizzes, and learning resources.

Take Quiz module offers a dynamic interface for attempting AI-generated quizzes.

View Quiz History allows students to review past performance and understand areas for improvement.
---### Educator Panel

Dashboard with performance insights provides educators with a comprehensive overview of student and class progress.

View student activity logs and detailed performance metrics.

Analyze progress via Pinecone data, enabling data-driven pedagogical decisions and targeted interventions.

How to Run the Project Locally
1️⃣ Clone the Repository
Bash

git clone [https://github.com/yourusername/edututor-ai.git](https://github.com/yourusername/edututor-ai.git)
cd edututor-ai
2️⃣ Create and Activate Virtual Environment
Bash

# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
3️⃣ Install Dependencies
Bash

pip install -r requirements.txt
4️⃣ Configure Environment Variables
Create a .env file in the root directory with the following:

Code snippet

WATSONX_MODEL_ID=granite-13b-instruct-v2
WATSONX_API_KEY=your_ibm_watsonx_api_key
WATSONX_ENDPOINT=[https://us-south.ml.cloud.ibm.com](https://us-south.ml.cloud.ibm.com)
WATSONX_PROJECT_ID=your_project_id

PINECONE_API_KEY=your_pinecone_api_key
PINECONE_INDEX_NAME=edututor
5️⃣ Run Backend (FastAPI)
Bash

cd backend
uvicorn main:app --reload
Visit API Docs: http://127.0.0.1:8000/docs

6️⃣ Run Frontend (Streamlit)
Bash

cd frontend
streamlit run app.py
🙌 Contributions
We welcome contributors! Please fork this repo, create a new branch, and raise a PR.

📬 Contact
📧 Email:(tirapathaiahg@gmail.com)

🐛 Issues: Open a GitHub Issue:(https://github.com/GTirapathaiah/Edututor-Ai-Personalized-Learning-With-Generative-Ai-And-Lms-Integration.git)

⭐ Star This Project
If you found this project useful or inspiring, please consider starring the repo 🙏
