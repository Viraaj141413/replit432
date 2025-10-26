# QA Reminder App

## Overview
A QA reminder application that helps quality assurance teams schedule and manage testing reminders with automated SMS notifications via Twilio integration.

## Purpose
- Schedule QA reminders with specific dates and times
- Send automated SMS notifications when reminders are due
- Track reminder status (pending, sent, completed)
- Manage active, overdue, and completed reminders
- Support recurring reminders (daily, weekly, monthly)

## Current State
**Status**: Production Ready - Running in Replit Environment

### Recent Changes (October 25, 2025)
- ✅ Successfully imported from GitHub and configured for Replit
- ✅ Installed all npm dependencies 
- ✅ Set up Twilio integration via Replit connector (secure credential management)
- ✅ Configured Supabase for authentication and database storage
- ✅ Fixed timezone handling - times now display correctly in user's local timezone
- ✅ Configured workflow to run on port 5000
- ✅ Set up deployment configuration for Replit Autoscale
- ✅ All features working:
  - Beautiful responsive UI with tabbed navigation
  - Create/edit reminder forms with validation
  - Automated SMS reminder scheduling (checks every 60 seconds)
  - Supabase database storage with Row Level Security
  - Multi-user authentication via Supabase Auth
  - Recurring reminders support
  - Premium visual design with gradients and animations
  - Correct timezone handling for all dates/times

## Project Architecture

### Technology Stack
**Frontend**:
- React with TypeScript
- Wouter for routing
- TanStack Query for data fetching
- Shadcn UI components
- Tailwind CSS for styling
- date-fns for date formatting

**Backend**:
- Express.js server (runs on port 5000)
- Supabase for database storage with PostgreSQL
- Supabase Auth for user authentication
- Twilio integration for SMS via Replit connector
- Automated scheduler (checks every 60 seconds for due reminders)
- Row Level Security (RLS) ensures users only see their own reminders

**Data Model**:
```typescript
Reminder {
  id: string
  title: string
  description?: string
  phoneNumber: string
  scheduledFor: timestamp
  status: 'pending' | 'sent' | 'failed'
  completed: boolean
}
```

### File Structure
```
client/
  src/
    pages/
      Home.tsx - Main dashboard with tabbed reminder views
      Auth.tsx - Sign in/sign up page
    components/
      ReminderCard.tsx - Individual reminder display
      ReminderDialog.tsx - Create/edit reminder form with timezone handling
      EmptyState.tsx - Empty state UI
      Analytics.tsx - Stats dashboard
    contexts/
      AuthContext.tsx - Authentication state management
server/
  routes.ts - API endpoints for CRUD operations
  supabase-storage.ts - Supabase database integration with RLS
  auth-middleware.ts - JWT token validation
  twilio.ts - Twilio SMS integration via Replit connector
  scheduler.ts - Automated reminder checking system
shared/
  schema.ts - TypeScript types and Zod schemas
supabase/
  migrations/ - Database schema migrations
```

## API Routes (To Be Implemented)
- `GET /api/reminders` - Get all reminders
- `POST /api/reminders` - Create new reminder
- `PATCH /api/reminders/:id` - Update reminder
- `DELETE /api/reminders/:id` - Delete reminder
- `PATCH /api/reminders/:id/complete` - Mark as complete

## Features
### Implemented
- ✅ Beautiful, responsive UI with tabbed navigation
- ✅ Create/edit reminder forms with validation
- ✅ Reminder cards with status badges
- ✅ Empty states for better UX
- ✅ Delete confirmation dialogs
- ✅ Complete data model and types
- ✅ Backend API implementation (all CRUD operations)
- ✅ Twilio SMS integration (via Replit connector)
- ✅ Automated scheduling system (60-second intervals)
- ✅ Frontend-backend integration complete

### Features Complete
- ✅ Persistent database storage via Supabase
- ✅ Multi-user authentication with Supabase Auth
- ✅ Row Level Security for data isolation
- ✅ Timezone-aware date/time handling
- ✅ Real-time updates via Supabase subscriptions
- ✅ Recurring reminders (daily, weekly, monthly)
- ✅ Automated SMS notifications via Twilio

## Design Guidelines
Following modern productivity app patterns inspired by Linear and Asana:
- Clean, professional interface
- Consistent spacing using Tailwind units (3, 4, 6, 8, 12)
- Inter font family for readability
- Status badges for visual clarity
- Responsive design for mobile and desktop
- Beautiful empty states and loading indicators

## User Preferences
None specified yet.

## Integration Details
- **Twilio**: Connected for SMS notifications
- Using Replit's Twilio connector for secure credential management
