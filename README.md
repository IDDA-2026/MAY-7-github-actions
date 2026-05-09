[![Deploy to Render](https://github.com/AnonimProgrammer/MAY-7-github-actions/actions/workflows/deploy.yml/badge.svg)](https://github.com/AnonimProgrammer/MAY-7-github-actions/actions/workflows/deploy.yml)

[![DevOps App CI](https://github.com/AnonimProgrammer/MAY-7-github-actions/actions/workflows/ci.yml/badge.svg)](https://github.com/AnonimProgrammer/MAY-7-github-actions/actions/workflows/ci.yml)

# DevOps App — TV shows API

Spring Boot REST API with CI/CD on GitHub Actions and deployment on Render.

## Live app

**Base URL:** [https://devops-app-ptej.onrender.com](https://devops-app-ptej.onrender.com)

Try it in the browser or with curl:

```bash
curl -s https://devops-app-ptej.onrender.com/tvshows | jq .
```

| Method | Path       | Description        |
|--------|------------|--------------------|
| GET    | `/tvshows` | List all TV shows  |

Free-tier Render services may spin down after idle time; the first request after that can take ~30–60 seconds.
