# My Epic Loot — Infra

Local development orchestration using Docker Compose.

## Environment Variables Setup

Before running the project, you need to set up Google OAuth environment variables:

### Google OAuth Configuration

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create OAuth 2.0 credentials with these settings:
   - **Authorized JavaScript origins**: `http://localhost:3000`
   - **Authorized redirect URIs**: `http://localhost:3000/api/auth/callback/google`
3. Set environment variables:

```bash
# Backend OAuth credentials
export GOOGLE_OAUTH2_CLIENT_ID="your-google-oauth-client-id"
export GOOGLE_OAUTH2_CLIENT_SECRET="your-google-oauth-client-secret"

# Frontend OAuth credentials (can be the same as backend)
export GOOGLE_CLIENT_ID="your-google-oauth-client-id" 
export GOOGLE_CLIENT_SECRET="your-google-oauth-client-secret"
```

## Usage

```bash
docker compose up --build
```

## Services

- **Backend**: Django API (port 8000)
- **Frontend**: Next.js app (port 3000)  
- **Database**: PostgreSQL (port 5433)
- **Storage**: MinIO (ports 9000, 9001)
- **Logging**: MongoDB (port 27017)
