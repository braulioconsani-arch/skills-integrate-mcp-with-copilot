# Feature Issues for Mergington High School Activity Management

Generated: February 6, 2026

These issues are ready to create in GitHub. Copy the issue details below and create them manually or via CLI.

---

## 🔴 PRIORITY HIGH (4 issues)

### 1. Add persistent database (SQLite/PostgreSQL)
**Label:** enhancement, database, priority-high

```
## Current State
In-memory activity dictionary - data lost on app restart

## Desired State
Migrate to persistent database for production readiness

## Details
- Replace in-memory `activities` dict with database
- Use SQLAlchemy ORM with SQLite (dev) or PostgreSQL (prod)
- Create database schema/migrations
- Ensure data persistence across restarts

## Why This Matters
Essential for production; currently all signup data is lost when server restarts.
```

### 2. Implement student authentication & user profiles
**Label:** enhancement, auth, priority-high

```
## Current State
No authentication - any email can signup without verification

## Desired State
Secure student authentication with complete user profiles

## Details
- Add user registration/login (email + password)
- Create student profile model (name, email, grade, contact)
- Implement JWT or session-based auth
- Add middleware to protect signup endpoints
- Student can only view/modify their own enrollments

## Why This Matters
Critical for security and proper activity enrollment tracking.
```

### 3. Create admin dashboard for staff management
**Label:** enhancement, ui, admin, priority-high

```
## Current State
No backend admin interface - staff can't manage activities or enrollments

## Desired State
Full-featured admin dashboard for school staff

## Details
- Build admin panel (Flask-Admin, Streamlit, or custom)
- Allow staff to CRUD activities
- View/manage student enrollments
- Set activity capacity and schedules
- Basic reporting views

## Why This Matters
Staff need tools to manage activities without touching code.
```

### 4. Add attendance tracking system
**Label:** enhancement, tracking, priority-high

```
## Current State
Only tracks signup - no record of actual participation

## Desired State
Complete attendance/participation tracking

## Details
- Add attendance endpoint: `POST /activities/{activity_name}/attendance`
- Record who attended each session with timestamp
- View attendance history per student and per activity
- Generate attendance reports

## Why This Matters
Schools need proof of participation for transcripts/records.
```

---

## 🟡 PRIORITY MEDIUM (6 issues)

### 5. Implement waitlist & enrollment cap management
**Label:** enhancement, enrollment, priority-medium

```
## Current State
Max capacity is enforced but no waitlist - students get rejected

## Desired State
Graceful waitlist system when activities are full

## Details
- Allow students to join waitlist when activity is full
- Notify students when spot opens up
- Auto-confirm from waitlist when capacity available
- API endpoints for waitlist management

## Why This Matters
Better UX - students can stay interested in full activities.
```

### 6. Add in-app notification system
**Label:** enhancement, notifications, priority-medium

```
## Current State
No notifications - students won't know about schedule changes or updates

## Desired State
Real-time notifications for activity updates and events

## Details
- Notification model/table (user, activity, message, read status)
- Endpoints to get unread notifications
- Mark notifications as read
- Notify on: schedule changes, activity cancellations, waitlist spots
- Optional: Email/SMS integration

## Why This Matters
Keep students informed about activity changes and updates.
```

### 7. Implement activity fee/payment tracking
**Label:** enhancement, payments, priority-medium

```
## Current State
No payment system - assumes all activities are free

## Desired State
Track activity fees and payment status

## Details
- Add optional fee field to activities
- Create payment/invoice records
- Track payment status per enrollment
- API to record payments made
- Export payment reports

## Why This Matters
If school charges fees for certain activities, need payment tracking.
```

### 8. Build advanced scheduling system
**Label:** enhancement, scheduling, priority-medium

```
## Current State
Schedule stored as text string - limited scheduling power

## Desired State
Sophisticated scheduling with conflict detection

## Details
- Structure schedules with day/time/duration
- Detect student schedule conflicts
- Show student availability based on other activities
- Support recurring schedules
- Notify on reschedules

## Why This Matters
Students need to avoid double-booking activities.
```

### 9. Add reporting & analytics dashboard
**Label:** enhancement, reporting, priority-medium

```
## Current State
No data analytics - can't pull reports on participation

## Desired State
Rich reporting on activity metrics and trends

## Details
- Activity popularity (enrollment counts)
- Student participation rates
- Attendance statistics
- Demographic breakdown (grade levels, etc.)
- Export reports to CSV/PDF
- Visualizations (charts, graphs)

## Why This Matters
Staff need insights on activity success and student engagement.
```

### 10. Implement student engagement/follow-up system
**Label:** enhancement, engagement, priority-medium

```
## Current State
No way to track or engage inactive students

## Desired State
Track engagement and re-engage inactive students

## Details
- Track last activity signup/attendance
- Identify inactive students
- Automated reminders for inactive students
- Staff can send direct messages
- Track interaction history

## Why This Matters
Schools want to keep students active and engaged.
```

---

## 🟢 PRIORITY LOW (2 issues)

### 11. Add document generation (certificates, slips)
**Label:** enhancement, documents, priority-low

```
## Current State
Can't generate any documents for students

## Desired State
Generate documents like participation certificates or permission slips

## Details
- Generate attendance certificates
- Generate permission slips for parents
- Generate participation records
- PDF export with school branding
- Bulk document generation

## Why This Matters
Schools can provide students with tangible proof of participation.
```

### 12. Upgrade frontend with real-time updates
**Label:** enhancement, ui, priority-low

```
## Current State
Static HTML - page needs refresh to see updates

## Desired State
Live updating dashboard with real-time data

## Details
- Implement WebSocket or Server-Sent Events (SSE)
- Live activity status updates
- Live participant counts
- Live notification feed
- Consider lightweight framework (Alpine.js, HTMX)

## Why This Matters
Modern UX - students see real-time availability without refreshing.
```

---

## Creating Issues

### Option 1: GitHub Web UI (Manual)
1. Go to: https://github.com/braulioconsani-arch/skills-integrate-mcp-with-copilot/issues
2. Click "New Issue"
3. Copy title and body from above
4. Add labels from the label field
5. Submit

### Option 2: GitHub CLI (Automated)
```bash
# First, ensure you have authentication:
gh auth login

# Then create all issues:
gh issue create --title "Add persistent database (SQLite/PostgreSQL)" \
  --body "..." \
  --label "enhancement,database,priority-high"
# ... (repeat for each issue)
```

### Option 3: Script (If using API token)
Set `GITHUB_TOKEN` environment variable and run the Python script in `/tmp/create_issues.py`.

---

## Summary
- **Total Issues:** 12
- **Priority High:** 4 (foundation/critical features)
- **Priority Medium:** 6 (enhancement/scaling)
- **Priority Low:** 2 (UX/polish)

Estimated work: **3-6 months** depending on team size and other projects.
