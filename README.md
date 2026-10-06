# Cloud_Deployment

Small Flask web app prepared for cloud deployment.

## Overview

This repository contains a minimal Flask application with templates organized under `templates/` and a small set of dependencies declared in `requirements.txt`.

## Dependencies

The application dependencies are listed in requirements.txt:

- Flask
- gunicorn
- requests

Install them with:

pip install -r requirements.txt

## Running locally

Development server (not for production):

export FLASK_APP=app.py
export FLASK_ENV=development
flask run

Production (using gunicorn):

gunicorn --bind 0.0.0.0:8000 app:app

Adjust the module/path above if your Flask app entrypoint uses a different filename or application object name.

## Templates

The `templates/` directory contains two subdirectories:

- `templates/admin/` — admin-facing templates
- `templates/public/` — public-facing templates

## Notes for deployment

- Ensure any required environment variables (for secret keys, configuration, or API credentials) are set in your environment or via your cloud provider's configuration.
- If using Docker or a PaaS (Heroku, Render, etc.), configure the platform to start the app using gunicorn for production workloads.

## Next steps / Recommendations

- Add a `Procfile` or `Dockerfile` for explicit deployment instructions.
- Add a `.env.example` documenting required environment variables.
- Include a more detailed README if the project grows (API endpoints, configuration, testing instructions).
