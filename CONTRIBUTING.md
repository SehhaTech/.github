# Contributing to SehhaTech

Thanks for your interest in contributing to SehhaTech! This document covers everything you need to get set up and submit changes that fit smoothly into the project.

## Code of Conduct

This project follows our [Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you're expected to uphold it.

## Tech Stack

| Layer | Technology |
|---|---|
| Backend API | ASP.NET Core (.NET) |
| Database | MySQL |
| Frontend | React |
| Auth | JWT (separate configuration for staff API vs. Patient Portal) |

## Getting Started

### Prerequisites

- [.NET SDK](https://dotnet.microsoft.com/download) (latest LTS)
- [Node.js](https://nodejs.org/) (LTS) + npm
- MySQL (local instance or Docker)
- Git

### Backend Setup (ASP.NET Core)

```bash
# Clone the relevant repository
git clone https://github.com/SehhaTech/SehhaTech.git
cd SehhaTech

# Restore dependencies
dotnet restore

# Apply EF Core migrations
dotnet ef database update

# Run the API
dotnet run
```

Make sure you have a local `appsettings.Development.json` (never commit real secrets — see [Secrets & Environment Variables](#secrets--environment-variables) below) with your local MySQL connection string and JWT configuration.

### Frontend Setup (React)

```bash
cd sehhatech-frontend   # or patient-portal-frontend
npm install
npm run dev
```

Update the API base URL in the frontend's `config.js` to point to your local backend (default: `https://localhost:5001` or similar, depending on your `launchSettings.json`).

## Branching Strategy

- `main` — production-ready code, protected branch
- `dev` — active development / integration branch
- Feature branches: `feature/<short-description>` (e.g. `feature/doctor-profile-edit`)
- Bug fix branches: `fix/<short-description>` (e.g. `fix/cors-config`)

Always branch off `dev` (not `main`) unless told otherwise for a specific repo.

## Commit Messages

Use clear, descriptive commit messages. Conventional prefixes are encouraged:

```
feat: add OTP verification to patient registration
fix: resolve CORS misconfiguration on staff API
refactor: extract JWT config into separate service
docs: update README with deployment steps
```

## Pull Requests

1. Make sure your branch is up to date with `dev` before opening a PR.
2. Fill out the PR template completely — link related issues, describe what changed and why.
3. Ensure the project builds and existing functionality isn't broken.
4. Request review from at least one other team member (Founders team for major architectural changes).
5. Squash-merge once approved, unless the PR intentionally preserves granular commit history.

## Secrets & Environment Variables

**Never commit:**
- API keys (Gemini, GCP, etc.)
- Connection strings with real credentials
- JWT signing secrets
- `.env` files with real values

Always use `.gitignore` to exclude local config files, and use GitHub Secrets / environment variables for CI/CD and deployment (Railway, Render, Vercel). If you accidentally commit a secret, notify the team immediately — see [SECURITY.md](./SECURITY.md).

## Multi-Tenant Considerations

SehhaTech is a multi-tenant platform. When working on any feature that touches data access, make sure:

- Queries are always scoped to the correct clinic/tenant
- No endpoint allows cross-tenant data leakage
- New migrations don't break tenant isolation

## Questions?

Reach out to the team at **sehhatech.team@gmail.com** or open a Discussion in the relevant repository.
