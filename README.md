# DevOps Monitoring Dashboard

A comprehensive DevOps monitoring dashboard built with React and Node.js, featuring real-time system metrics, service monitoring, deployment tracking, and alerting capabilities.

## 🚀 Features

### Dashboard Overview
- **Real-time System Metrics**: CPU, memory, and disk usage monitoring with visual indicators
- **Service Status Monitoring**: Track multiple services with uptime percentages and health status
- **CI/CD Pipeline Visualization**: Monitor build, test, and deployment stages
- **Deployment History**: Track version deployments across environments
- **Alert Management**: Real-time alerts with acknowledgment capabilities

### Dedicated Pages
- **📊 Metrics**: Detailed system performance monitoring with historical charts
- **⚙️ Services**: Service management with status controls and filtering
- **🚀 Deployments**: Deployment timeline with environment tracking
- **🔔 Alerts**: Alert management with acknowledgment and filtering
- **🏗️ Infrastructure**: Server monitoring, network analytics, and security overview

## 🛠️ Technology Stack

### Frontend
- **React 18** with TypeScript
- **Wouter** for client-side routing
- **TanStack Query** for server state management
- **shadcn/ui** component library
- **Tailwind CSS** for styling
- **Recharts** for data visualization
- **Vite** for development and build

### Backend
- **Node.js** with Express.js
- **TypeScript** with ES modules
- **Drizzle ORM** for database operations
- **PostgreSQL** for persistent data storage
- **Neon Database** serverless driver

## 📋 Prerequisites

- Node.js 18+ installed
- PostgreSQL database (automatically configured in Replit)

## 🚀 Getting Started

### Installation

1. Clone the repository
2. Install dependencies:
```bash
npm install
```

3. Set up the database:
```bash
npm run db:push
```

4. Start the development server:
```bash
npm run dev
```

The application will be available at `http://localhost:5000`

## 📁 Project Structure

```
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/         # Application pages
│   │   ├── lib/           # Utilities and configuration
│   │   └── hooks/         # Custom React hooks
├── server/                # Backend Express application
│   ├── index.ts           # Server entry point
│   ├── routes.ts          # API route definitions
│   ├── storage.ts         # Data storage layer
│   └── db.ts              # Database connection
├── shared/                # Shared types and schemas
│   └── schema.ts          # Database schema definitions
└── README.md
```

## 🗄️ Database Schema

The application uses PostgreSQL with the following tables:

- **metrics**: System performance data (CPU, memory, disk)
- **services**: Service status and uptime information
- **deployments**: Deployment history and status
- **pipeline_stages**: CI/CD pipeline stage tracking
- **alerts**: System alerts and notifications

## 🔧 Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run db:push` - Push database schema changes

## 🎨 Features in Detail

### Real-time Monitoring
- Automatic data refresh every 5-30 seconds
- Live system metrics with color-coded status indicators
- Service health monitoring with uptime tracking

### Interactive Dashboard
- Click to acknowledge alerts
- Service status management
- Pipeline stage monitoring
- Deployment tracking across environments

### Responsive Design
- Mobile-friendly interface
- Dark theme optimized for monitoring environments
- Accessible UI components with proper contrast

## 🚀 Deployment

### Production Build
```bash
npm run build
npm start
```

### Environment Variables
- `DATABASE_URL` - PostgreSQL connection string (automatically configured)
- `NODE_ENV` - Environment mode (development/production)

## 📊 API Endpoints

### Metrics
- `GET /api/metrics/latest` - Get current system metrics
- `GET /api/metrics/history/:hours` - Get historical metrics
- `POST /api/metrics` - Create new metrics entry

### Services
- `GET /api/services` - Get all services
- `PUT /api/services/:id` - Update service status

### Deployments
- `GET /api/deployments` - Get deployment history
- `POST /api/deployments` - Create new deployment

### Pipeline
- `GET /api/pipeline` - Get pipeline stages
- `PUT /api/pipeline/:id` - Update pipeline stage

### Alerts
- `GET /api/alerts` - Get recent alerts
- `POST /api/alerts` - Create new alert
- `PUT /api/alerts/:id/acknowledge` - Acknowledge alert

## 🎯 Use Cases

This dashboard is perfect for:
- **DevOps Teams**: Monitor system health and deployment status
- **System Administrators**: Track server performance and alerts
- **Development Teams**: Monitor CI/CD pipeline progress
- **Educational Projects**: Learn full-stack development with real-world features

## 🔒 Data Persistence

All data is stored in PostgreSQL with:
- Type-safe database operations using Drizzle ORM
- Automatic schema migrations
- Persistent storage across application restarts
- Real-time data updates

## 📈 Performance

- Optimized React Query caching
- Efficient database queries with proper indexing
- Server-side response caching
- Minimal bundle size with code splitting

## 🤝 Contributing

This is a semester project demonstrating modern web development practices with:
- Full-stack TypeScript development
- Database integration and ORM usage
- Real-time data visualization
- Responsive UI design
- RESTful API development

## 📄 License

This project is for educational purposes.

Built using modern web technologies for comprehensive DevOps monitoring.
