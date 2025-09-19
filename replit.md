# Overview

This is a board game learning platform called "GameMaster" that helps users discover, learn, and master board games through interactive tutorials and progress tracking. The application provides a comprehensive dashboard for browsing games, following structured learning paths, and tracking personal progress across different board game experiences.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The frontend is built with React and TypeScript using Vite as the build tool. The application follows a component-based architecture with:

- **Routing**: Uses `wouter` for client-side routing with pages for dashboard, game browsing, game details, and tutorials
- **State Management**: React Query (`@tanstack/react-query`) handles server state management and caching
- **UI Framework**: Implements shadcn/ui components built on Radix UI primitives with Tailwind CSS for styling
- **Component Structure**: Organized into reusable components (game cards, progress tracking, tutorial steps) and layout components (sidebar, header)

## Backend Architecture
The backend is an Express.js server with TypeScript that provides:

- **API Layer**: RESTful endpoints for games, tutorials, user progress, and learning paths
- **Storage Abstraction**: Uses an interface-based storage pattern with in-memory implementation for development
- **Request Handling**: Express middleware for JSON parsing, logging, and error handling
- **Development Setup**: Vite integration for hot module replacement in development mode

## Data Storage Solutions
The application uses Drizzle ORM with PostgreSQL for data persistence:

- **Schema Definition**: Centralized schema in `shared/schema.ts` defining users, games, tutorials, user progress, learning paths, and user goals
- **Database Configuration**: Drizzle Kit configured for PostgreSQL with Neon Database serverless driver
- **Type Safety**: Zod schemas generated from Drizzle for runtime validation
- **Migrations**: Database migrations managed through Drizzle Kit

## Authentication and Authorization
Currently implements a basic user system with hardcoded user references ("user1") suggesting placeholder authentication. The architecture supports user-specific data through user IDs in the data models.

## External Dependencies

- **Database**: Neon Database (PostgreSQL serverless)
- **UI Components**: Radix UI primitives for accessible component foundation
- **Styling**: Tailwind CSS with custom design tokens and CSS variables
- **Development Tools**: 
  - Replit-specific plugins for development environment integration
  - ESBuild for server bundling
  - PostCSS with Tailwind for CSS processing
- **Fonts**: Google Fonts integration (Architects Daughter, DM Sans, Fira Code, Geist Mono)
- **Icons**: Lucide React for consistent iconography
- **Session Management**: connect-pg-simple for PostgreSQL session storage
- **Date Handling**: date-fns for date manipulation and formatting

The architecture prioritizes type safety, component reusability, and scalable data management while providing a smooth development experience with hot reloading and integrated tooling.