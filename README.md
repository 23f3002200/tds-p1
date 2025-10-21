title: Tds P1 Llm Deployment Api
emoji: 🏃
colorFrom: pink
colorTo: yellow
sdk: docker
app_port: 7860
pinned: false
LLM Deployment API Service
This is a Docker Space hosting a FastAPI service.

Project Description
This service acts as the Task Receiver API for the student project to build, deploy, and update a web application on GitHub Pages. It performs the following steps:

Receives a task request (brief, attachments) via POST /ready.
Verifies the STUDENT_SECRET.
Calls the Gemini LLM to generate or revise the application code (index.html, README.md, LICENSE).
Commits and pushes the code to a new or existing GitHub repository.
Enables GitHub Pages for deployment.
Pings the evaluation URL with deployment metadata (repo URL, commit SHA, pages URL).
API Endpoints
POST /ready: Primary endpoint for receiving new tasks (Round 1) or revision requests (Round 2+).
GET /health: Returns {"status": "ok"} to confirm the service is running.
GET /logs: Displays the last 100 lines of the application logs.
