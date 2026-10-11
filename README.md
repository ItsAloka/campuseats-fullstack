# CampusEats - Full-Stack Deployment (SE3090 Lab 11)

| Tier | Folder | Host |
|---|---|---|
| Frontend (React + Vite) | `web/` | Vercel |
| Backend API (ASP.NET Core 8) | `api/` | Railway (Dockerfile) |
| Database (PostgreSQL) | - | Neon (managed PostgreSQL) |

## Environment variables (values are set on the platforms, never committed)

**Frontend (Vercel)**
- `VITE_API_URL` - deployed API base URL, e.g. `https://<api>.up.railway.app`

**Backend (Railway)**
- `ConnectionStrings__Default` - Neon connection string (`...;SSL Mode=Require`)
- `Jwt__Key` - long random production secret
- `Jwt__Issuer` = `CampusEats`, `Jwt__Audience` = `CampusEatsUsers`
- `Cors__AllowedOrigins` - frontend origin, e.g. `https://<web>.vercel.app`

## Local
```
cd web && npm install && npm run build
cd api && dotnet run        # secrets via `dotnet user-secrets`
```
