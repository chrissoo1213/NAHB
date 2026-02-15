🧠 Mindfall: Psychological Horror Engine

A full-stack web application for creating, exploring, and publishing interactive psychological horror experiences where every decision fractures reality.

🕯️ Concept

Mindfall is a branching narrative platform designed for dark, immersive storytelling.
Users create nonlinear psychological journeys where choices distort perception, memory, and consequence.

Each story is structured as interconnected pages and decisions, allowing authors to design unsettling, choice-driven experiences that simulate paranoia, uncertainty, and mental descent.

🏗 Architecture

Mindfall uses a decoupled microservice architecture for flexibility and scalability.

⚙️ Flask API — The Narrative Engine

The Flask service acts as the core data layer and logic processor.

It is responsible for:

Creating and managing Stories

Handling Pages and branching Choices

Processing probability-based events

Persisting data in a SQLite database (instance/app.db)

Securing requests via API key authentication

This layer functions as the “mind mechanics” behind each experience.

🖥 Django Application — The Experience Interface

The Django service provides the interactive user interface.

It manages:

User authentication and sessions

Story exploration and gameplay flow

Personal story dashboards

Community discovery feed

Reviews and moderation reporting

This layer represents the immersive surface where users enter the psychological descent.

🧰 Prerequisites

Python 3.12

pip

virtualenv

⚙️ Setup Instructions
1️⃣ Environment Preparation

Create and activate a virtual environment in the root directory:

python3.12 -m venv venv
source venv/bin/activate
pip install -r flask_api/requirements.txt -r django_app/requirements.txt

2️⃣ Configuration

Create a .env file in the root directory using the structure provided in .env.example.

This file must contain:

API key configuration

Environment variables required by both services

3️⃣ Database Initialization
Flask API
cd flask_api
flask db upgrade
cd ..

Django Application
cd django_app
python manage.py migrate
python manage.py createsuperuser
cd ..


After database setup, create any additional user accounts as needed.

▶️ Running the Application

You must run both services in separate terminal windows.

Terminal 1 — Start Flask API
cd flask_api
flask run --port=5000

Terminal 2 — Start Django Interface
cd django_app
python manage.py runserver 8000


Access the application via:

http://127.0.0.1:8000

🔗 Flask API Endpoints
Stories (/stories)

GET /stories — Retrieve all stories

POST /stories — Create a new story

PUT /stories/<id> — Update a story

DELETE /stories/<id> — Remove a story

Pages & Choices

POST /pages — Create a new page

POST /pages/<id>/choices — Add branching choices

DELETE /choices/<id> — Remove a choice

🎭 Intended Use

Mindfall is designed for:

Psychological horror storytelling

Experimental nonlinear fiction

Interactive narrative research

Creative writing exploration

Choice-based emotional simulation

⚠️ Notes

Both servers must be running simultaneously.

The Flask API must be active before the Django interface can fully operate.

Ensure environment variables are correctly configured before deployment.

🕳️ Final Thought

In Mindfall, every decision is irreversible.
Every path reveals something darker.

Choose carefully.