# TeamFlow — Task Manager

A modern, collaborative project and task management application built with React. TeamFlow provides teams with an intuitive interface to organize projects, manage tasks, track progress, and collaborate seamlessly.

## ✨ Features

### 📊 Dashboard
- **Quick Overview**: View total tasks, in-progress items, overdue tasks, and completed work at a glance
- **Project Progress**: Track project completion percentage with visual progress bars
- **Recent Activity**: Monitor the latest task updates across projects
- **Overdue Alerts**: Immediate visibility into overdue tasks with warnings

### 📁 Projects
- **Create & Manage Projects**: Easily create projects with custom names, descriptions, and colors
- **Project Organization**: View all projects with progress tracking and member avatars
- **Color Coding**: Visually distinguish projects with custom color themes
- **Team Management**: Add/remove team members to projects by email
- **Quick Stats**: See tasks completed, active items, and overdue tasks per project

### ✅ Tasks
- **Create Tasks**: Add tasks with title, description, priority, status, and due dates
- **Smart Filtering**: Filter by project, status, priority, or view only your assigned tasks
- **Status Tracking**: Manage task workflows from To Do → In Progress → In Review → Done
- **Priority Levels**: Set high, medium, or low priority for tasks
- **Task Details**: View comprehensive task information, assignee, and due dates
- **Comments & Collaboration**: Add comments to tasks for team communication
- **Overdue Alerts**: Visual indicators for overdue tasks

### 👥 Team
- **Team Dashboard** (Admin only): View all team members and their activity
- **Performance Metrics**: Track tasks assigned, completed, overdue, and projects per member
- **Member Details**: See member contact information and role assignments
- **Role-Based Access**: Admin and Member roles with different permissions

### 🔐 Authentication
- **Secure Login/Signup**: Create accounts with email and password
- **Role Management**: Admin and Member roles with appropriate permissions
- **Demo Accounts**: Pre-configured accounts for testing

## 🎨 Design

- **Dark Theme**: Modern dark interface with comfortable viewing
- **Responsive Design**: Fully responsive on desktop, tablet, and mobile devices
- **Custom Color Palette**: Carefully selected color system for visual hierarchy
- **Accessible UI**: Clear typography and high contrast for readability
- **Smooth Animations**: Subtle transitions and interactions

## 🚀 Getting Started

### Demo Accounts

**Admin Account:**
- Email: `admin@teamflow.com`
- Password: `admin123`

**Member Accounts:**
- Email: `sam@teamflow.com` | Password: `member123`
- Email: `jordan@teamflow.com` | Password: `member123`
- Email: `riley@teamflow.com` | Password: `member123`

### Setup

1. Open `teamflow.html` in a modern web browser
2. Sign in with a demo account or create a new account
3. Start creating projects and tasks

## 🏗️ Architecture

### Stack
- **React 18**: UI library with hooks for state management
- **Babel**: JavaScript transpiler for JSX support
- **In-Memory Database**: All data stored in browser memory (resets on page refresh)

### Key Components

| Component | Purpose |
|-----------|---------|
| `AuthScreen` | User authentication (login/signup) |
| `Dashboard` | Overview and statistics |
| `Projects` | Project management interface |
| `Tasks` | Task creation, filtering, and management |
| `Team` | Team member administration |
| `Modal` | Reusable modal dialog system |
| `Avatar` | User avatar display component |

### Data Model

**Users**
```javascript
{
  id: string,
  name: string,
  email: string,
  password: string,
  role: 'admin' | 'member',
  avatar: string,
  color: string
}
```

**Projects**
```javascript
{
  id: string,
  name: string,
  description: string,
  ownerId: string,
  members: string[],
  createdAt: string (ISO date),
  color: string
}
```

**Tasks**
```javascript
{
  id: string,
  title: string,
  description: string,
  projectId: string,
  assigneeId: string,
  priority: 'high' | 'med' | 'low',
  status: 'todo' | 'progress' | 'review' | 'done',
  dueDate: string (ISO date),
  createdAt: string,
  createdBy: string,
  comments: Comment[]
}
```

## 🔑 Key Features Breakdown

### Permission System
- **Admins**: Full access to all projects, tasks, and team management
- **Members**: Access only to projects they're assigned to

### Task Lifecycle
1. Create task in a project
2. Assign to team member with priority
3. Track status through workflow stages
4. Add comments for collaboration
5. Mark as done when complete

### Overdue Detection
- Tasks are marked overdue when due date passes and status is not "done"
- Visual alerts shown throughout the application
- Overdue filter available in task view

## 🎯 Use Cases

- **Team Collaboration**: Manage team projects and coordinate work
- **Project Tracking**: Monitor progress with visual indicators
- **Workload Management**: Assign tasks and track team performance
- **Sprint Planning**: Create projects and organize tasks by priority
- **Team Communication**: Comment on tasks for asynchronous collaboration

## 💾 Data Persistence

⚠️ **Note**: All data is stored in browser memory. Data will reset when the page is refreshed. For production use, integrate with a backend database.

## 🎨 Customization

### Color Scheme
Edit CSS variables in the `<style>` section:
```css
:root {
  --bg: #0d0f14;
  --accent: #6c63ff;
  --success: #22c55e;
  /* ... and more */
}
```

### Fonts
Three font families included:
- **Syne**: Headlines and titles
- **Inter**: Body text
- **DM Mono**: Monospace/data display

## 📱 Responsive Breakpoints

- **Desktop**: Full layout with sidebar
- **Tablet** (≤768px): Reduced sidebar width
- **Mobile** (≤560px): Hidden sidebar, full-width main content

## 🔒 Security Notes

- Passwords stored in memory (not hashed)
- No actual authentication or authorization checks
- For production, implement proper backend security

## 🚀 Future Enhancements

- Backend API integration
- Database persistence
- Real-time collaboration
- File attachments
- Email notifications
- Advanced reporting
- Custom workflows
- Integrations (Slack, Zapier, etc.)

## 📄 License

This project is provided as-is for educational and demonstration purposes.

---

**Built with ❤️ using React**
