
# Scriptly — AI-Powered Mental Health Journaling Web Application

Scriptly is a full-stack web application that helps users maintain a digital journal and understand their emotions through AI-powered text analysis.

The application analyzes journal entries, identifies the user's emotional state, provides confidence scores, and offers recommendations based on the detected emotion. It also includes user authentication, emotion history, and an alert mechanism for entries containing potentially concerning keywords.

## Features

- 🔐 **User Authentication**
  - User registration and login
  - JWT-based authentication
  - Protected API endpoints

- 📝 **Digital Journaling**
  - Create and manage journal entries
  - View previous journal entries
  - Simple and user-friendly journal interface

- 🧠 **Emotion Analysis**
  - Analyzes text written in journal entries
  - Uses a transformer-based NLP model for emotion classification
  - Detects six emotions:
    - Joy
    - Sadness
    - Anger
    - Fear
    - Love
    - Surprise
  - Provides confidence scores for detected emotions

- 📊 **Emotion History**
  - Stores previous emotion analysis results
  - Allows users to view their emotional history

- 💡 **Personalized Recommendations**
  - Provides rule-based recommendations based on detected emotions

- 🚨 **Alert System**
  - Checks journal entries for predefined concerning keywords and conditions
  - Can trigger email notifications through SMTP when configured

- 🌐 **Frontend**
  - HTML5
  - CSS3
  - JavaScript
  - Tailwind CSS
  - Separate pages for authentication, journaling, emotion results and history

## Technology Stack

### Frontend

- HTML5
- CSS3
- JavaScript
- Tailwind CSS

### Backend

- Python
- Django
- Django REST Framework
- PostgreSQL
- JWT Authentication

### Machine Learning / NLP

- Python
- Transformers
- DistilRoBERTa
- NLTK

### Deployment

- Frontend: Netlify
- Backend: Render
- Database: PostgreSQL

## Project Structure

```text
Scriptly/
│
├── Backend/
│   ├── accounts/
│   ├── alerts/
│   ├── journal/
│   ├── nlp/
│   ├── recommendations/
│   ├── scriptly_project/
│   ├── manage.py
│   └── requirements.txt
│
├── Frontend/
│   ├── static/
│   │   ├── css/
│   │   └── js/
│   └── templates/
│
├── .gitignore
├── rquirements.txt
└── README.md
````

## How It Works

```text
User writes a journal entry
          ↓
Frontend sends the entry to the backend
          ↓
Django REST API receives the request
          ↓
Text preprocessing using NLTK
          ↓
Emotion classification using the NLP model
          ↓
Emotion + confidence score generated
          ↓
Result stored in the database
          ↓
Recommendation generated
          ↓
Result displayed to the user
```

## Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/ShawliS/Scriptly.git
cd Scriptly
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\activate
```

### 3. Install Backend Dependencies

```bash
cd Backend
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file inside the `Backend` directory and add the required environment variables.

Example:

```env
SECRET_KEY=your_secret_key
DEBUG=True

DATABASE_URL=your_database_url

EMAIL_HOST=your_email_host
EMAIL_PORT=your_email_port
EMAIL_HOST_USER=your_email
EMAIL_HOST_PASSWORD=your_email_password
```

**Never commit your `.env` file or API keys to GitHub.**

### 5. Run Database Migrations

```bash
python manage.py migrate
```

### 6. Start the Backend Server

```bash
python manage.py runserver
```

The backend will normally be available at:

```text
http://127.0.0.1:8000/
```

### 7. Run the Frontend

Open the frontend files using your preferred local development server and make sure the API URL in the frontend configuration points to your running Django backend.

## Backend Modules

The backend is organized into separate Django applications:

| Module            | Purpose                                                  |
| ----------------- | -------------------------------------------------------- |
| `accounts`        | User registration, authentication and account management |
| `journal`         | Journal entry management                                 |
| `nlp`             | Text preprocessing and emotion analysis                  |
| `recommendations` | Emotion-based recommendations                            |
| `alerts`          | Alert and email notification functionality               |

## Security

Scriptly uses several measures to protect application data:

* JWT-based authentication
* Environment variables for sensitive configuration
* Protected API endpoints
* CORS configuration
* HTTPS support in deployment

Sensitive credentials such as API keys, passwords and secret keys should never be stored directly in source code.

## Disclaimer

Scriptly is an educational/software project designed for journaling and emotion-analysis purposes. Its emotion predictions and recommendations should not be considered a medical diagnosis, professional mental-health assessment, or replacement for professional support.

## Future Improvements

* More detailed emotion analytics and visualizations
* Improved recommendation personalization
* Better model optimization and response time
* More comprehensive automated testing
* Mobile application support
* Additional NLP features
* Improved accessibility and UI/UX
