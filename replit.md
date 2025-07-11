# Programming Lab Management System

## Overview

This is a full-stack web application for managing programming lab activities, built with React, Express, and PostgreSQL. The system allows students to report issues, log lab usage, and provides technicians with tools to manage and resolve problems efficiently.

## User Preferences

Preferred communication style: Simple, everyday language.

## Recent Changes

### January 10, 2025
- ✅ Fixed Firebase authentication with proper error handling and demo mode fallback
- ✅ Added comprehensive sample data for demonstration (issues, lab usage logs, users)
- ✅ Implemented modern welcome screen with role selection
- ✅ Updated color scheme to match provided HTML template (indigo/purple theme)
- ✅ Fixed TypeScript errors in storage implementation
- ✅ Added dynamic notification counter in header showing open issues count
- ✅ Enhanced UI styling with improved gradients and visual hierarchy
- ✅ Added advanced features: Analytics dashboard, Staff information system, Notifications center
- ✅ Implemented special features: Advanced search, Bulk actions, Export tools, System monitoring
- ✅ Enhanced technician panel with comprehensive management tools
- ✅ Added detailed role descriptions for technicians, technical assistants, and junior technicians
- ✅ Prepared complete source code for GitHub with deployment configurations
- ✅ Created comprehensive documentation (README, CONTRIBUTING, DEPLOYMENT guides)
- ✅ Added free hosting configurations for Vercel, Netlify, Railway, and Render
- ✅ Added individual delete and bulk delete functionality for lab usage logs
- ✅ Enhanced log management with proper role-based access controls
- ✅ Created complete project download package with GitHub setup instructions
- ✅ Added MIT license and professional open-source documentation
- ✅ Finalized production-ready codebase with comprehensive deployment guides

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query for server state management
- **UI Components**: Radix UI components with shadcn/ui styling
- **Styling**: Tailwind CSS with custom CSS variables
- **Build Tool**: Vite for development and build process

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ESM modules
- **Database**: PostgreSQL with Drizzle ORM
- **Development**: In-memory storage fallback for development
- **Build**: esbuild for production bundling

### Authentication
- **Provider**: Firebase Authentication
- **Method**: Anonymous authentication for demo purposes
- **Role Management**: Client-side role switching between student and technician

## Key Components

### Database Schema
- **Users**: Basic user management with roles (student/technician)
- **Issues**: Bug reports and technical problems with priority levels
- **Lab Usage Logs**: Student activity tracking for lab sessions

### Advanced Features
- **Advanced Search**: Multi-criteria filtering with date ranges and complex queries
- **Bulk Actions**: Mass operations for issue management and status updates
- **Export Tools**: Data export in CSV/JSON formats with customizable options
- **System Monitoring**: Real-time performance tracking and environmental sensors
- **Role-Based Access**: Separate interfaces for students, technicians, and technical assistants

### API Endpoints
- `GET/POST /api/issues` - Issue management
- `PATCH/DELETE /api/issues/:id` - Issue updates and deletion
- `GET/POST /api/lab-usage-logs` - Lab usage tracking
- `DELETE /api/lab-usage-logs/:id` - Log cleanup

### User Interface
- **Dashboard**: Overview of statistics and recent activity
- **Issue Report**: Form for students to report technical problems
- **Lab Usage**: Session logging and history
- **Technician Panel**: Advanced issue management with bulk actions and search
- **Analytics**: Comprehensive data visualization and performance metrics
- **Notifications**: Real-time alerts and system notifications
- **Staff Information**: Detailed role descriptions and contact information
- **Settings**: User preferences and system configuration
- **System Monitoring**: Real-time system status and performance tracking

## Data Flow

1. **Student Workflow**:
   - Report issues through structured forms
   - Log lab usage sessions
   - View dashboard with personal statistics

2. **Technician Workflow**:
   - View and filter all reported issues with advanced search
   - Bulk update issue status and priority
   - Export data and generate reports
   - Monitor system performance and status
   - Access comprehensive analytics and statistics
   - Manage staff information and procedures

3. **Technical Assistant Workflow**:
   - Provide first-level technical support
   - Monitor daily lab operations
   - Assist with equipment maintenance
   - Record and escalate complex issues

4. **Junior Technician Workflow**:
   - Learn basic system administration under supervision
   - Manage user accounts and basic software installation
   - Replace basic hardware components
   - Participate in training and skill development programs

3. **Data Management**:
   - Real-time updates using TanStack Query
   - Form validation with Zod schemas
   - Automatic timestamp tracking

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: PostgreSQL database connection
- **drizzle-orm**: Type-safe database operations
- **@tanstack/react-query**: Server state management
- **react-hook-form**: Form handling and validation
- **zod**: Schema validation

### UI Dependencies
- **@radix-ui/***: Accessible UI primitives
- **tailwindcss**: Utility-first CSS framework
- **lucide-react**: Icon library
- **class-variance-authority**: Variant-based styling

### Development Dependencies
- **vite**: Build tool and development server
- **typescript**: Type checking
- **drizzle-kit**: Database migrations and introspection

## Deployment Strategy

### Development
- **Database**: In-memory storage for quick prototyping
- **Server**: Express with Vite middleware for HMR
- **Environment**: NODE_ENV=development with development-specific features

### Production
- **Build Process**: 
  - Frontend: Vite build to `dist/public`
  - Backend: esbuild bundle to `dist/index.js`
- **Database**: PostgreSQL with Drizzle migrations
- **Server**: Node.js serving static files and API endpoints
- **Environment Variables**: DATABASE_URL for PostgreSQL connection

### Database Migration
- **Tool**: Drizzle Kit for schema management
- **Command**: `npm run db:push` to apply schema changes
- **Configuration**: `drizzle.config.ts` with PostgreSQL dialect

The application is designed to be easily deployable on platforms like Replit, with automatic database provisioning and seamless development-to-production transitions.

## GitHub Repository Setup

### Free Hosting Options
The project is configured for deployment on multiple free hosting platforms:
- **Vercel**: Recommended for full-stack applications with serverless functions
- **Netlify**: Great for static sites with serverless backend
- **Railway**: Full-stack hosting with database support
- **Render**: Complete application hosting with build automation

### Repository Structure
```
├── README.md              # Comprehensive project documentation
├── CONTRIBUTING.md         # Contribution guidelines
├── DEPLOYMENT.md          # Detailed deployment instructions
├── LICENSE                # MIT license for open source
├── vercel.json            # Vercel deployment configuration
├── netlify.toml           # Netlify deployment configuration
├── .gitignore             # Git ignore rules
└── package.json           # Project dependencies and scripts
```

### Key Features for Open Source
- **MIT License**: Allows free use, modification, and distribution
- **Comprehensive Documentation**: Setup guides, deployment instructions, and contribution guidelines
- **Multiple Deployment Options**: Ready-to-use configurations for popular hosting platforms
- **Professional Code Structure**: Well-organized, commented, and maintainable codebase
- **Environment Variable Support**: Secure configuration management for different environments