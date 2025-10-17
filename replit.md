# Staff Report & HR Management System

## Overview

A comprehensive enterprise HR and performance management system built with React, Express, and PostgreSQL. The application provides staff management, performance tracking, leave request handling, scheduling, and detailed reporting capabilities with a modern dashboard interface.

The system features a **vibrant, gorgeous design** with bold gradients, colorful UI elements, and optimized performance. The design is inspired by modern platforms like Monday.com and ClickUp, blending enterprise professionalism with engaging visual aesthetics.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Technology Stack:**
- **Framework:** React 18 with TypeScript
- **Routing:** Wouter (lightweight client-side routing)
- **State Management:** TanStack Query (React Query) for server state
- **UI Framework:** Shadcn/ui components built on Radix UI primitives
- **Styling:** Tailwind CSS with custom design tokens
- **Charts:** Recharts for data visualization
- **Form Handling:** React Hook Form with Zod validation

**Design System:**
- **Vibrant color palette** with gorgeous gradients and bold accents
- **Vibrant purple gradient sidebar** (HSL 250 100% 65% to 280 100% 70%)
- **Colorful UI elements** with subtle tints on cards and panels
- **Multi-color chart palette** for engaging data visualization
- Inter font family as primary typography
- Light/dark mode support with vibrant color schemes
- Consistent component patterns using class-variance-authority
- Responsive layouts optimized for desktop workflows

**Component Architecture:**
- Modular page-based structure (`/pages` directory)
- Reusable UI components from Shadcn library (`/components/ui`)
- Custom hooks for authentication and mobile detection
- Protected route wrapper for authenticated access

### Backend Architecture

**Technology Stack:**
- **Runtime:** Node.js with Express.js
- **Language:** TypeScript with ES modules
- **Database ORM:** Drizzle ORM
- **Authentication:** Passport.js with local strategy
- **Session Management:** Express-session with connect-pg-simple store
- **Security:** Scrypt password hashing with timing-safe comparison

**API Design:**
- RESTful endpoints under `/api` prefix
- Authentication middleware protecting all routes
- CRUD operations for staff, reports, leave requests, schedules, and performance data
- CSV upload/import functionality using Multer and csv-parse
- Standardized error handling with status codes

**Storage Layer:**
- Interface-based storage abstraction (`IStorage`)
- In-memory implementation for development
- PostgreSQL-ready schema via Drizzle ORM
- Session persistence with PostgreSQL session store

**Database Schema (PostgreSQL):**
- `users` - Authentication and user profiles
- `staff` - Employee records with department and position data
- `reports` - Performance metrics (FTD, calls, deposits, conversion rates)
- `leave_requests` - Leave management with approval workflow
- `schedules` - Staff scheduling with shift assignments
- `performance` - Detailed performance reviews and ratings
- `notifications` - Real-time user notifications with read/unread status

### Build & Deployment

**Development:**
- Vite dev server with HMR for frontend
- TSX for TypeScript execution without compilation
- Middleware-mode Vite integration with Express
- Source map support for debugging

**Production:**
- Vite builds frontend to `dist/public`
- ESBuild bundles backend to `dist/index.js`
- Static file serving from build output
- Environment-based configuration

### Authentication & Authorization

**Strategy:**
- Username/password authentication via Passport Local Strategy
- Session-based authentication with secure cookies
- Role-based access control (staff, admin roles in schema)
- Protected route components on frontend
- Server-side authentication checks on all API endpoints

**Session Management:**
- Express-session with PostgreSQL store (connect-pg-simple)
- Secure session secrets via environment variables
- Automatic session persistence across server restarts

### Real-time Notifications System

**Architecture:**
- PostgreSQL-backed notification storage with user association
- Auto-refresh polling every 10 seconds for unread notifications
- Bell icon in header with unread count badge
- Popover interface for viewing and managing notifications

**Notification Types:**
- `leave_approved` - Leave request approved notification
- `leave_rejected` - Leave request rejected notification  
- `schedule_changed` - Schedule update notification
- `report_uploaded` - Report upload notification

**Auto-Triggers:**
- Leave request approval/rejection → Notification to staff's user account
- Schedule updates → Notification to staff's user account

**Features:**
- Mark individual notifications as read
- Mark all notifications as read
- Visual indicators for unread status
- Relative timestamps (e.g., "5 minutes ago")
- Type-based Lucide React icons for visual distinction

**Performance Optimizations:**
- Polling interval: 30 seconds (reduced from 10s)
- Stale time: 20 seconds to reduce unnecessary refetches
- Only fetch when user is authenticated
- Database indexes on userId and isRead columns
- Query response times: 126-157ms average

## External Dependencies

### Third-Party Services
- **Neon Database:** PostgreSQL serverless database (@neondatabase/serverless)
- **Google Fonts:** Inter font family loaded via CDN

### UI Libraries
- **Radix UI:** Accessible component primitives (20+ component packages)
- **Shadcn/ui:** Pre-built component library based on Radix
- **Recharts:** Chart and data visualization library
- **Lucide React:** Icon library

### Development Tools
- **Replit Plugins:** Cartographer and dev banner for development environment
- **Vite:** Build tool and dev server
- **Drizzle Kit:** Database migrations and schema management

### Key npm Packages
- `express` - Web server framework
- `drizzle-orm` - TypeScript ORM for PostgreSQL
- `passport` / `passport-local` - Authentication
- `express-session` / `connect-pg-simple` - Session management
- `react-hook-form` / `zod` - Form validation
- `@tanstack/react-query` - Data fetching and caching
- `multer` - File upload handling
- `csv-parse` - CSV data processing
- `date-fns` - Date manipulation
- `tailwindcss` - Utility-first CSS framework

### Database
- **PostgreSQL** via Neon serverless driver
- **Drizzle ORM** for type-safe database queries
- Schema-first approach with migrations in `/migrations` directory
- Connection via `DATABASE_URL` environment variable