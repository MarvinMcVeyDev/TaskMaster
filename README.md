# TaskMaster

TaskMaster is a responsive, browser-based task management application built with **HTML, CSS, and vanilla JavaScript**. It provides a simple interface for creating, organizing, completing, filtering, and deleting tasks while incorporating client-side validation, local data persistence, and basic security-focused input handling.

## Features

- **Create tasks**
  - Add a task description
  - Assign a priority level: Low, Medium, or High
  - Set a due date
  - Validate task descriptions before submission

- **Task management**
  - Mark tasks as completed or active
  - Delete individual tasks
  - Clear all completed tasks
  - View all, active, or completed tasks
  - Display the number of remaining active tasks

- **Local persistence**
  - Tasks are stored using the browser's `localStorage`
  - Tasks remain available after refreshing or reopening the page
  - Handles storage and JSON parsing errors gracefully

- **Responsive design**
  - Desktop and mobile-friendly layouts
  - Responsive task navigation
  - Touch-friendly controls on smaller screens

- **Priority indicators**
  - High-priority tasks
  - Medium-priority tasks
  - Low-priority tasks
  - Visual priority indicators using colored borders

- **Read-only mode**
  - Toggle read-only mode using the `R` keyboard shortcut
  - Prevents adding, completing, or deleting tasks while enabled
  - Tasks remain viewable while modifications are disabled

- **Keyboard shortcuts**
  - `R` — Toggle read-only mode
  - `N` — Focus the new-task input
  - Shortcuts are disabled while typing in form controls

- **Input validation and security**
  - Prevents empty task descriptions
  - Requires a minimum task description length
  - Detects several potentially dangerous input patterns
  - Sanitizes user-provided content before displaying it as HTML
  - Restricts URL validation to HTTP and HTTPS protocols
  - Records suspicious input events in an in-memory security log
  - Displays security notifications when security-related functionality is initialized

- **Dynamic UI**
  - Automatically updates the document title with the current task count
  - Displays an empty state when no tasks match the selected filter
  - Updates task counts whenever the task list changes

## Technologies

- **HTML5**
- **CSS3**
- **JavaScript (Vanilla JS)**
- **DOM API**
- **Web Storage API (`localStorage`)**
- **Google Fonts**
  - Poppins
  - Roboto

No JavaScript frameworks or external task-management libraries are required.

## Project Structure

```text
TaskMaster/
├── index.html
├── style.css
└── app.js
```

### `index.html`

Defines the application structure, including:

- Task creation form
- Priority selector
- Due-date input
- Task filter navigation
- Task list
- Task summary
- Clear-completed functionality
- Application header and footer

### `style.css`

Controls the visual presentation and responsive behavior of the application.

It includes:

- Layout and spacing
- Typography
- Form styling
- Task priority indicators
- Completed-task styling
- Buttons and navigation
- Empty states
- Mobile responsive behavior
- Touch-friendly controls

### `app.js`

Contains the application's functionality and state management.

Major responsibilities include:

- Creating and managing task objects
- Rendering tasks
- Filtering tasks
- Completing and deleting tasks
- Local storage persistence
- Form validation
- Input sanitization
- Security feedback
- Read-only mode
- Keyboard shortcuts
- URL validation
- Dynamic task counts

## Getting Started

### 1. Clone or download the project

Download the project files or clone the repository to your local machine.

### 2. Open the application

Open `index.html` in a modern web browser.

No server-side application or build process is required.

### 3. Start managing tasks

Enter a task description, select a priority, choose a due date, and select **Add Task**.

Tasks will be stored locally in the browser automatically.

## Task Data

Each task is represented by an object containing:

```text
{
    id,
    description,
    priority,
    date,
    completed
}
```

Tasks are serialized to JSON and stored under the `taskmasterTasks` key in browser `localStorage`.

## Security Considerations

TaskMaster includes several client-side security measures designed to reduce the risk of unsafe user-provided content being interpreted as HTML or executable code.

### Input validation

Task descriptions are checked for:

- Empty input
- Minimum length requirements
- Common script-related patterns such as `<script`, `javascript:`, and inline event handlers

### HTML sanitization

User-provided task descriptions are sanitized before being inserted into the DOM. This prevents entered HTML from being interpreted as markup.

### URL validation

The application includes URL validation that:

- Accepts empty URLs when appropriate
- Uses the browser's `URL` parser
- Allows only `http:` and `https:` protocols
- Rejects protocols such as `javascript:`, `data:`, `file:`, and `ftp:`

### Security feedback

Potentially suspicious input can be recorded in an in-memory security log, and the application provides a security notification to indicate that its security-related features have been initialized.

> **Note:** These protections are client-side safeguards and should not be considered a replacement for server-side validation and security controls in a production application.

## Responsive Design

TaskMaster adapts its layout for smaller screens.

On screens below 600px:

- The task filter navigation becomes vertically organized
- The Add Task button expands to the available width
- Task summaries stack vertically
- Checkbox controls become larger for touch interaction
- Delete and filter controls receive larger touch targets

## Future Improvements

Potential future enhancements include:

- Task editing
- Task categories or tags
- Search functionality
- Task sorting
- Recurring tasks
- Notifications and reminders
- Drag-and-drop task ordering
- Dark mode
- Backend/database persistence
- User authentication
- Cloud synchronization
- More comprehensive automated testing
- Improved accessibility features

## Author

**Marvin McVey**

TaskMaster was created as a hands-on project for practicing front-end web development, JavaScript DOM manipulation, responsive design, client-side data persistence, input validation, and security-conscious development.

## License

This project is available for educational and personal use.
