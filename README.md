# Jenkins Pipeline Task

this project demonstrates a jenkins pipeline integrated with Github

Simple demo that shows a Jenkins declarative pipeline which:
- Builds a Docker image from the repository `Dockerfile`
- Runs tests inside the built image (`npm test`)
- Deploys the built image to a local Docker container on port 3000

## Files
- `app/` — Node app
- `Dockerfile` — builds the app image
- `Jenkinsfile` — Jenkins declarative pipeline
- `jenkins-docker-compose.yml` — to run Jenkins with Docker access locally

## How to run locally
1. `docker compose -f jenkins-docker-compose.yml up -d`
2. Setup Jenkins at `http://localhost:8080` (install plugins)
3. Create pipeline job pointing to this repo (or push this repo to GitHub)
4. Trigger builds by pushing commits

## Notes
- If Jenkins cannot access Docker, ensure `/var/run/docker.sock` is mounted and Docker CLI is available inside Jenkins container.

