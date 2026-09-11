# GreenSphere

GreenSphere is an AI-assisted plant care web application built with a Flask
backend and a browser-based frontend.

## Features

- Plant identification from uploaded images
- Disease detection and care guidance
- Personal garden and growth tracking
- Nursery browsing and plant orders
- Email OTP registration and verification
- Light-meter and weather analysis
- Optional Gemini, Plant.id, Google Calendar, and n8n integrations

## Project Structure

```text
T113/
|- README.md
|- frontend/
|  |- pages/              HTML application pages
|  |- js/                 Shared browser JavaScript
|  |- css/                Frontend stylesheets
|  |- assets/             Images and animations
|  `- Tests/manual/       Manual browser tests
`- backend/
	|- app.py              Flask application
	|- run.py              Development server
	|- routes/             API route blueprints
	|- tests/              Backend tests
	|- instance/           Local database files
	`- requirements.txt    Python dependencies
```

## Requirements

- Python 3.8 or newer
- pip
- Plant.id API credentials for identification and disease detection
- Optional credentials for Gemini, weather, email, and Google Calendar

## Windows Setup

From the project root, run:

```powershell
backend\setup.bat
```

Or set up manually:

```powershell
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
copy .env.example .env
```

Edit `backend/.env` with your own credentials. Never commit `.env`, tokens,
credentials, or API keys.

## Run the Application

```powershell
cd backend
venv\Scripts\activate
python run.py
```

Open `http://localhost:5000/` in a browser. The API health check is available
at `http://localhost:5000/api/health`.

The Flask server serves pages from `frontend/pages`, scripts from `frontend/js`,
styles from `frontend/css`, and media from `frontend/assets`.

## Testing

Run a backend syntax check:

```powershell
python -m compileall backend\tests
```

Run an individual test from the project root:

```powershell
python backend\tests\test_plant_matching.py
python backend\tests\check_schema.py
```

Manual browser tests are in `frontend/Tests/manual` and require the backend to
be running.

## Git Workflow

```powershell
git status
git add .
git commit -m "Describe your changes"
git push
```

Repository: https://github.com/Keerthana3339/GreenSphere