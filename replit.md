# DevOps Dashboard - System Overview

## Overview

This is a modern DevOps dashboard application built with React and Node.js, designed to provide real-time monitoring and management of system metrics, services, deployments, and CI/CD pipelines. The application follows a full-stack architecture with a REST API backend and a responsive frontend using shadcn/ui components.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with custom dashboard theme variables
- **Build Tool**: Vite for development and production builds
- **Charts**: Recharts for data visualization

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM with PostgreSQL dialect
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: PostgreSQL session store with connect-pg-simple
- **Development**: TSX for TypeScript execution in development

### Data Storage
- **Primary Database**: PostgreSQL (Replit-hosted database)
- **ORM**: Drizzle ORM with type-safe schema definitions
- **Database Connection**: Neon serverless driver with WebSocket support
- **Schema Management**: Automated schema migrations via `npm run db:push`
- **Data Persistence**: All dashboard data now persists in PostgreSQL tables

## Key Components

### Database Schema
Located in `shared/schema.ts`, defines five main entities:
- **Metrics**: CPU, memory, disk usage with timestamps
- **Services**: Service status, uptime, and descriptions
- **Deployments**: Version tracking, environment, and deployment status
- **Pipeline Stages**: CI/CD pipeline stage management
- **Alerts**: System alerts with acknowledgment tracking

### API Endpoints
RESTful API structure in `server/routes.ts`:
- **GET/POST /api/metrics**: System metrics management
- **GET/PUT /api/services**: Service status monitoring
- **GET/POST /api/deployments**: Deployment history tracking
- **GET/PUT /api/pipeline**: CI/CD pipeline management
- **GET/POST /api/alerts**: Alert management

### Frontend Components
Modular component architecture:
- **Dashboard**: Main overview with real-time metrics
- **MetricCard**: Reusable metric display component
- **PerformanceChart**: Time-series data visualization
- **ServiceStatus**: Live service monitoring
- **PipelineStatus**: CI/CD pipeline visualization
- **DeploymentHistory**: Deployment tracking table

### Application Pages
Complete page structure with dedicated views:
- **Dashboard** (`/`): Overview with key metrics and system status
- **Metrics** (`/metrics`): Detailed system performance monitoring with historical charts
- **Services** (`/services`): Service management with status controls and filtering
- **Deployments** (`/deployments`): Deployment timeline with environment tracking
- **Alerts** (`/alerts`): Alert management with acknowledgment and filtering
- **Infrastructure** (`/infrastructure`): Server monitoring, network analytics, and security overview

## Data Flow

1. **Real-time Updates**: Frontend components use React Query with automatic refetch intervals (5-30 seconds depending on data criticality)
2. **API Communication**: RESTful endpoints with JSON data exchange
3. **Database Operations**: Drizzle ORM handles all database interactions with type safety
4. **State Management**: React Query manages server state, local component state for UI interactions
5. **Error Handling**: Centralized error handling with toast notifications

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Serverless PostgreSQL connection
- **drizzle-orm & drizzle-kit**: Type-safe database ORM and migrations
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: Accessible UI component primitives
- **recharts**: Chart visualization library
- **tailwindcss**: Utility-first CSS framework
- **wouter**: Lightweight React router

### Development Dependencies
- **tsx**: TypeScript execution for development
- **vite**: Build tool and development server
- **@replit/vite-plugin-***: Replit-specific development plugins

## Deployment Strategy

### Development
- **Command**: `npm run dev` - Uses TSX to run TypeScript directly
- **Hot Reload**: Vite provides fast HMR for frontend changes
- **Database**: Uses DATABASE_URL environment variable for connection

### Production Build
- **Frontend**: `vite build` - Optimized production bundle
- **Backend**: `esbuild` - Bundles server code with external packages
- **Output**: Static files in `dist/public`, server bundle in `dist/index.js`

### Production Runtime
- **Command**: `npm start` - Runs the bundled Node.js application
- **Environment**: NODE_ENV=production
- **Database**: Requires DATABASE_URL for PostgreSQL connection

### Database Management
- **Migrations**: `npm run db:push` - Pushes schema changes to database
- **Schema**: Centralized in `shared/schema.ts` for type safety across frontend/backend

## User Preferences

Preferred communication style: Simple, everyday language.

## Changelog

```
Changelog:
- June 30, 2025. Initial setup
- June 30, 2025. Added PostgreSQL database integration with Drizzle ORM
  * Replaced in-memory storage with persistent PostgreSQL storage
  * Created database schema with 5 tables: metrics, services, deployments, pipeline_stages, alerts
  * Implemented DatabaseStorage class with full CRUD operations
  * Successfully migrated all data to PostgreSQL with proper seeding
  * All dashboard functionality now uses persistent data storage
```