# LumenSys - Projeto de Graduação

Projeto de graduação desenvolvido pela equipe LumenSys utilizando React.js + TypeScript (frontend) e C# .NET 8 Web API (backend) com PostgreSQL.

**Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.**

## Working Effectively

### Prerequisites and Initial Setup
- Node.js (v18+ required, v20.19.5 tested working)
- .NET 8 SDK (v8.0.119 tested working)
- Docker and Docker Compose v2
- PostgreSQL (via Docker)
- Git

### Repository Structure
```
LumenSys Organization:
├── LumenSys-Frontend/     # React + TypeScript + Vite frontend
├── LumenSys-Backend/      # C# .NET 8 Web API backend  
└── .github/               # Organization documentation
```

### Clone and Setup Projects
```bash
# Clone both repositories side by side
git clone https://github.com/LumenSys/LumenSys-Frontend.git
git clone https://github.com/LumenSys/LumenSys-Backend.git
```

### Frontend Development (React + TypeScript + Vite)
```bash
cd LumenSys-Frontend/frontend

# Install dependencies - takes ~25 seconds
npm install

# Build project - takes ~6 seconds  
npm run build

# Run linting - takes ~2 seconds (may show 2 warnings about react-refresh)
npm run lint

# Start development server - starts on http://localhost:5173/
npm run dev
```

**Frontend Build Times - NEVER CANCEL:**
- `npm install`: 25 seconds - Set timeout to 60+ seconds
- `npm run build`: 6 seconds - Set timeout to 30+ seconds
- `npm run lint`: 2 seconds - Set timeout to 15+ seconds

**Frontend Testing:**
- No test runner currently configured
- Linting shows 2 warnings about react-refresh (expected)

### Backend Development (C# .NET 8 Web API)
```bash
cd LumenSys-Backend

# Restore dependencies - takes ~30 seconds
dotnet restore

# Build solution - takes ~15 seconds with warnings (expected)
dotnet build

# Run the API - starts on http://localhost:7096/
dotnet run --project LumenSys.WebAPI
```

**Backend Build Times - NEVER CANCEL:**
- `dotnet restore`: 30 seconds - Set timeout to 90+ seconds
- `dotnet build`: 15 seconds with 148 warnings (expected) - Set timeout to 60+ seconds

**Backend Build Warnings:**
- 148 warnings are expected (hiding inherited members, nullable reference types)
- These warnings do not prevent compilation and are not errors

### Database Setup (PostgreSQL via Docker)
```bash
cd LumenSys-Backend/Docker

# Start PostgreSQL with initialization - takes ~30 seconds
docker compose up postgres

# Note: The database will auto-initialize with lumensysDb.sql
# Default credentials: postgres/123456, database: LumenSysDB, port: 5432
```

**Database Details:**
- PostgreSQL latest image
- Database: LumenSysDB
- User: postgres 
- Password: 123456
- Port: 5432
- Initialization script: Database/lumensysDb.sql

### Full Stack with Docker
```bash
cd LumenSys-Backend/Docker

# Build and start all services - takes ~5-10 minutes NEVER CANCEL
docker compose up --build

# Services:
# - PostgreSQL: localhost:5432
# - Backend API: localhost:7096  
# - Frontend: localhost:5173
```

**Docker Build Times - NEVER CANCEL:**
- Full stack build: 5-10 minutes - Set timeout to 20+ minutes
- Database initialization: 30 seconds
- API service build: 2-3 minutes
- Frontend service build: 1-2 minutes

## Validation Scenarios

**Always test these scenarios after making changes:**

### Frontend Validation
1. **Build Validation**: Run `npm install && npm run build` successfully
2. **Development Server**: Start `npm run dev` and verify it serves on http://localhost:5173/
3. **Linting**: Run `npm run lint` (2 warnings expected, not errors)

### Backend Validation  
1. **Build Validation**: Run `dotnet restore && dotnet build` (148 warnings expected)
2. **API Server**: Start with `dotnet run --project LumenSys.WebAPI` 
3. **Health Check**: Verify API responds at http://localhost:7096/

### Database Validation
1. **PostgreSQL Start**: Run `docker compose up postgres` successfully
2. **Connection**: Verify database accepts connections on port 5432
3. **Initialization**: Confirm lumensysDb.sql loads without errors

### Full Integration Testing
1. **Stack Start**: Run `docker compose up --build` for complete environment
2. **Service Health**: Verify all three services (DB, API, Frontend) start successfully
3. **Connectivity**: Frontend can communicate with API, API can connect to database

## Common Tasks and Commands

### Development Workflow Commands
```bash
# Quick frontend development
cd LumenSys-Frontend/frontend && npm install && npm run dev

# Quick backend development  
cd LumenSys-Backend && dotnet restore && dotnet run --project LumenSys.WebAPI

# Database only
cd LumenSys-Backend/Docker && docker compose up postgres

# Full stack development
cd LumenSys-Backend/Docker && docker compose up --build
```

### Code Quality Commands
```bash
# Frontend linting
cd LumenSys-Frontend/frontend && npm run lint

# Backend build with warnings check
cd LumenSys-Backend && dotnet build

# No automated tests currently configured
```

### Container Management
```bash
# Stop all services
docker compose down

# Remove volumes (reset database)
docker compose down -v

# View logs
docker compose logs -f [service-name]
```

## Project Structure Reference

### Frontend (LumenSys-Frontend/frontend/)
```
frontend/
├── src/                # React TypeScript source
├── public/             # Static assets
├── package.json        # Node.js dependencies and scripts  
├── vite.config.ts      # Vite build configuration
├── tailwind.config.js  # Tailwind CSS configuration
├── tsconfig.json       # TypeScript configuration
└── eslint.config.js    # ESLint configuration
```

### Backend (LumenSys-Backend/)
```
LumenSys-Backend/
├── LumenSys.WebAPI/           # Main Web API project
│   ├── Controllers/           # API controllers
│   ├── Services/              # Business logic services
│   ├── Data/                  # Entity Framework repositories
│   ├── Objects/Models/        # Entity models
│   ├── Objects/DTOs/          # Data transfer objects
│   ├── Authentication/        # JWT authentication
│   └── Dockerfile             # API container configuration
├── Database/
│   └── lumensysDb.sql         # Database initialization script
├── Docker/
│   └── docker-compose.yml     # Multi-service orchestration
└── LumenSys.WebAPI.sln        # Visual Studio solution
```

## Technology Stack

### Frontend Technologies
- **React 18.3.1** - UI library
- **TypeScript 5.5.3** - Type safety
- **Vite 5.4.9** - Build tool and dev server
- **Tailwind CSS 3.4.14** - Utility-first CSS
- **React Router DOM 6.27.0** - Client-side routing
- **Axios 1.7.7** - HTTP client

### Backend Technologies  
- **.NET 8** - Web API framework
- **Entity Framework Core** - ORM
- **JWT Authentication** - Security
- **PostgreSQL** - Database

### DevOps and Tools
- **Docker & Docker Compose** - Containerization
- **ESLint** - JavaScript/TypeScript linting
- **PostgreSQL** - Relational database

## Important Notes

### Build Warnings
- **Frontend**: 2 ESLint warnings about react-refresh (harmless)
- **Backend**: 148 C# warnings about nullable references and method hiding (expected, not errors)

### Performance Expectations
- Frontend dev server starts in ~280ms
- Backend API starts in ~2-3 seconds
- Database initialization takes ~30 seconds on first run
- Full Docker stack takes 5-10 minutes to build from scratch

### Development Best Practices
- Always run both frontend and backend linting before committing
- Use Docker for consistent database environment
- Frontend uses port 5173, backend uses port 7096, database uses port 5432
- Environment variables for API URL: `VITE_API_URL=http://localhost:7096/api/`

### Troubleshooting
- If PostgreSQL fails to start: Remove Docker volumes with `docker compose down -v`
- If frontend build fails: Delete node_modules and run `npm install` again  
- If backend build fails: Run `dotnet clean` then `dotnet restore`
- If services can't connect: Check Docker network and port configurations