# Business Development App

## Overview

This is a full-stack React application designed for business development and lead management. The application features robust authentication, role-based access control, and a comprehensive business management interface. It's built as a modern web application with Firebase for backend services and a clean, professional UI.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with shadcn/ui component library
- **Routing**: Wouter for client-side navigation
- **State Management**: React Context for authentication, TanStack Query for server state
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Authentication & Database**: Firebase (Authentication + Firestore)
- **API Server**: Express.js (minimal setup, primarily for static file serving)
- **Database Schema**: Uses Drizzle ORM configuration for PostgreSQL (prepared for future expansion)

### UI Design System
- **Component Library**: shadcn/ui with Radix UI primitives
- **Design Tokens**: CSS custom properties for consistent theming
- **Responsive Design**: Mobile-first approach with Tailwind breakpoints
- **Color Scheme**: Professional business theme with primary blue (#0078D4)

## Key Components

### Authentication System
- **Provider**: Firebase Authentication with email/password
- **Role Management**: User roles stored in Firestore ('user' | 'admin')
- **Access Control**: Protected routes with role-based restrictions
- **Session Management**: Firebase handles authentication state persistence

### Layout Structure
- **Topbar**: Search, notifications, quick actions, user menu
- **Sidebar**: Hierarchical navigation with collapsible sections
- **Main Content**: Dynamic content area with proper responsive behavior
- **Admin Sections**: Restricted access for user management and idea review

### Core Features
1. **Dashboard**: Business metrics, charts, recent activities
2. **Idea Submission**: Form-based idea submission with validation
3. **Lead Management**: Pipeline view with status tracking (placeholder)
4. **Project Management**: Project tracking and timeline (placeholder)
5. **User Management** (Admin): Role assignment, user status control
6. **Idea Review** (Admin): Approval workflow for submitted ideas

### Database Schema
- **Users**: Profile data, roles, timestamps stored in Firestore
- **Ideas**: Submission data with review status and admin comments
- **Notifications**: User-specific notification system
- **Future Entities**: Leads, Projects, Tasks (prepared schema structure)

## Data Flow

### Authentication Flow
1. User logs in via Firebase Auth
2. User profile fetched from Firestore
3. Role-based routing determines accessible features
4. Context provides auth state throughout app

### Idea Submission Flow
1. User fills form with validation
2. Data submitted to Firestore with metadata
3. Admin receives notification of new submission
4. Admin can review, approve, or reject with comments

### Admin Workflows
1. User Management: View users, change roles, manage status
2. Idea Review: Approve/reject ideas, add comments, set priority
3. Analytics: Dashboard metrics and reporting capabilities

## External Dependencies

### Firebase Services
- **Authentication**: User login/signup, session management
- **Firestore**: NoSQL database for user data, ideas, notifications
- **Security Rules**: Role-based data access control

### UI Libraries
- **Radix UI**: Accessible component primitives
- **Lucide React**: Icon library for consistent iconography
- **TanStack Query**: Server state management and caching
- **React Hook Form**: Form handling with validation

### Development Tools
- **TypeScript**: Type safety and developer experience
- **Vite**: Fast development server and optimized builds
- **Tailwind CSS**: Utility-first styling approach
- **PostCSS**: CSS processing and optimization

## Deployment Strategy

### Environment Configuration
- Firebase project configuration via environment variables
- Separate development and production Firebase projects
- Environment-specific settings for API endpoints

### Build Process
1. **Frontend**: Vite builds React app to static files
2. **Backend**: Express server bundle for production deployment
3. **Static Assets**: Served via Express with proper caching headers

### Hosting Options
- **Frontend**: Can be deployed to Vercel, Netlify, or Firebase Hosting
- **Backend**: Express server can run on any Node.js hosting platform
- **Database**: Firebase Firestore (managed service)

### Security Considerations
- Firebase Security Rules enforce data access control
- Environment variables protect sensitive configuration
- HTTPS enforced for all production endpoints
- Input validation on both client and server sides