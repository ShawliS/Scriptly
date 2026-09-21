# Scriptly — AI-Powered Mental Health Journaling Web Application

Scriptly is a full-stack web application that helps users maintain a digital journal and understand their emotions through AI-powered text analysis.

The application analyzes journal entries, identifies the user's emotional state, provides confidence scores, and offers recommendations based on the detected emotion. It also includes authentication, emotion history, and an alert mechanism for entries containing potentially concerning keywords.

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
  - HTML, CSS and JavaScript-based interface
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

## How it works
- User writes a journal entry
          ↓
- Frontend sends the entry to the backend
          ↓
- Django REST API receives the request
          ↓
- Text preprocessing using NLTK
          ↓
- Emotion classification using the NLP model
          ↓
- Emotion + confidence score generated
          ↓
- Result stored in the database
          ↓
- Recommendation generated
          ↓
- Result displayed to the user

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
