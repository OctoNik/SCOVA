# SCOVA — Essay Grading System WebApp

SCOVA, formerly UploadItIn, is an educational web application designed to streamline the management and grading of essay assignments. It is an Automated Short Answer Grading (ASAG) system that automatically evaluates the quality and relevance of student submissions against reference answers, while also generating personalized feedback for each student to enhance their learning experience.

---

## 🌟 Key Features

- **Smart Auto-Grading:** Instantly grade student essays using semantic evaluation powered by Google Gemini embeddings. The system understands the meaning behind the text rather than matching keywords, scoring answers on a 0–100 scale against the teacher's model answer.
- **Personalized Feedback:** Every submission receives tailored, AI-generated feedback explaining how the answer compares to the reference, so students understand not just their score but how to improve.
- **Flexible File Support:** Upload essays in the format that works best for you. We support PDF, DOCX, and TXT files, making submission effortless for students.
- **Class & Assignment Management:** Easily organize your teaching! Teachers can create dedicated virtual classrooms, generate unique join codes, and create assignments.
- **Student Portal:** Students can seamlessly enroll in classes, submit their work, and view their results all in one place.
- **Admin Dashboard:** A robust control center for administrators to manage user accounts, oversee class activities, and update platform content effortlessly.

---

## 🛠️ How It Works

1. **Set Up a Class:** A teacher creates a new class and receives a unique 6-character join code to share with students.
2. **Create an Assignment:** The teacher adds an assignment and provides a "model answer" file as the grading baseline.
3. **Student Submission:** Students join the class using the code and upload their essay answers.
4. **Instant Evaluation:** As soon as the file is submitted, the system embeds both the student answer and the model answer, measures their semantic similarity, and produces a score along with personalized feedback.
5. **Review Results:** Both teachers and students can instantly review the final grades and feedback on their personal dashboards.

---

## 🧠 Technology

| Layer | Stack |
| --- | --- |
| Frontend | Next.js (React), Tailwind CSS, Framer Motion, SWR |
| Backend | Python, Flask |
| Database & Auth | Supabase (PostgreSQL, Auth, Storage) |
| Grading Engine | Google Gemini embeddings (`gemini-embedding-2-preview`), cosine similarity |
| Feedback Engine | Google Gemini 3.1 Flash-Lite (`gemini-3.1-flash-lite-preview`) |
| Fallback Grading | Latent Semantic Analysis (LSA) using TF-IDF + SVD |
| Indonesian NLP | Sastrawi (stemming, stopword removal) |
| Deployment | Docker, Docker Compose |

The grading engine is selected with the `SCORING_ENGINE` environment variable: `embeddings` uses Gemini embeddings, while `legacy` falls back to the LSA pipeline.

---

## 🔧 For Developers

Looking to run SCOVA locally, configure environment variables, or contribute to the codebase? See the **[Developer Setup Guide (DEVELOPMENT.md)](./DEVELOPMENT.md)** for architecture details, prerequisites, environment variables, run instructions, and the test suite.

---

## 👥 The Team

We are a dedicated team of professionals committed to transforming educational technology:

**NLP Team:**
- OctoNik — Nikolaus Nathaniel (535230113)
- Borjues — Dhani Andika Maharsi (535230149)

**Software Development Team:**
- Jalsson (535230145)
- Richie Lagito (535230037)
- Nikolaus Nathaniel (535230113)
- Dhani Andika Maharsi (535230149)
