# ProjectFlow - Project Management Application

## Overview

ProjectFlow is a modern project management application built with a full-stack architecture featuring React with TypeScript on the frontend and Express.js with Node.js on the backend. The application provides comprehensive project and task management capabilities with real-time collaboration features, user authentication, and an intuitive Kanban-style interface.

The system enables teams to create projects, manage tasks across different workflow stages (To Do, In Progress, Done), collaborate through comments, and track project progress. It includes features like user management, project member management, task prioritization, due date tracking, and a notification system.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript and Vite as the build tool
- **UI Components**: Radix UI primitives with custom shadcn/ui components for consistent design
- **Styling**: Tailwind CSS with custom design tokens and CSS variables for theming
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Routing**: Wouter for client-side routing with simple path-based navigation
- **Form Handling**: React Hook Form with Zod validation schemas

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Design**: RESTful API with JSON request/response format
- **Session Management**: Express sessions with PostgreSQL storage using connect-pg-simple
- **Error Handling**: Centralized error middleware with structured error responses
- **Request Logging**: Custom middleware for API request/response logging

### Authentication System
- **Provider**: Replit OIDC (OpenID Connect) integration
- **Strategy**: Passport.js with OpenID Connect strategy
- **Session Storage**: PostgreSQL-backed sessions with configurable TTL
- **Security**: HTTP-only cookies with secure flags for production environments

### Database Architecture
- **Database**: PostgreSQL with Neon serverless hosting
- **ORM**: Drizzle ORM with type-safe schema definitions
- **Schema Design**: Relational model with users, projects, tasks, comments, and project members
- **Migrations**: Drizzle Kit for schema migrations and database management
- **Connection**: Connection pooling with @neondatabase/serverless

### Data Models
- **Users**: Profile information with email, names, and avatar URLs
- **Projects**: Project metadata with ownership, descriptions, and custom colors
- **Tasks**: Task management with status, priority, assignments, and due dates
- **Comments**: Thread-based commenting system linked to tasks
- **Project Members**: Many-to-many relationship for project collaboration

### API Structure
- **Authentication Routes**: `/api/auth/*` for user authentication and session management
- **Project Routes**: `/api/projects/*` for CRUD operations on projects
- **Task Routes**: `/api/projects/:id/tasks/*` for task management within projects
- **Comment Routes**: Nested under task endpoints for comment operations

### File Organization
- **Shared Schema**: Common TypeScript types and Zod schemas in `/shared/`
- **Client Code**: React application in `/client/` with component-based architecture
- **Server Code**: Express server in `/server/` with modular route organization
- **Configuration**: TypeScript, Tailwind, and build configurations at root level

## External Dependencies

### Core Framework Dependencies
- **@neondatabase/serverless**: PostgreSQL serverless client for database connectivity
- **drizzle-orm**: Type-safe ORM for database operations and query building
- **drizzle-kit**: Database migration and schema management tooling

### Authentication & Security
- **passport**: Authentication middleware for Express applications
- **openid-client**: OpenID Connect client for Replit OIDC integration
- **express-session**: Session management middleware for Express
- **connect-pg-simple**: PostgreSQL session store for persistent sessions

### UI & Styling
- **@radix-ui/react-***: Comprehensive set of accessible UI primitives
- **tailwindcss**: Utility-first CSS framework for styling
- **class-variance-authority**: Utility for creating variant-based component APIs
- **lucide-react**: Modern icon library with consistent design

### State Management & Data Fetching
- **@tanstack/react-query**: Server state management with caching and synchronization
- **wouter**: Lightweight client-side routing library
- **react-hook-form**: Form handling with validation support

### Development & Build Tools
- **vite**: Fast build tool and development server
- **typescript**: Static type checking and enhanced developer experience
- **@replit/vite-plugin-***: Replit-specific development tools and error handling

### Utility Libraries
- **zod**: Schema validation for type-safe data parsing
- **date-fns**: Date manipulation and formatting utilities
- **clsx**: Conditional className utility for dynamic styling