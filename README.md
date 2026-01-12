# Sticky Note Web App

A full-stack web application for task management with repeat tasks, reminders, and subtasks support. Built with PHP, MySQL, JavaScript, and CSS.

## Features

### 📝 Task Management
- Create, edit, and delete notes/tasks
- Organize tasks by categories: Work, Personal, Wishlist, Birthday, Daily
- Filter tasks by category
- Mark tasks as completed or pending
- View task details with date and time

### 🔄 Repeat Tasks
- Set tasks to repeat daily, weekly, or monthly
- Configure custom intervals for repeat tasks
- Set end dates or number of occurrences for repeating tasks
- Automatic generation of future task instances

### ⏰ Reminders & Notifications
- Set reminders for tasks
- Desktop browser notifications
- Automatic reminder checking every minute
- Configurable reminder times (same time as task or X minutes before)

### ✅ Task Organization
- View tasks organized by sections:
  - **Previous**: Past and today's pending tasks
  - **Future**: Upcoming tasks
  - **Completed Today**: Tasks completed today
- Collapsible sections for better organization
- View all completed tasks in a dedicated page

### 📋 Subtasks
- Add multiple subtasks to each note
- Mark individual subtasks as completed
- Track progress within each task

## Tech Stack

- **Backend**: PHP
- **Database**: MySQL
- **Frontend**: HTML, CSS, JavaScript
- **Styling**: Custom CSS with Poppins font

## Project Structure

```
Sticky Note Web/
├── css/                    # Stylesheets
│   ├── StickyNote.css     # Main page styles
│   ├── add_note.css       # Add note form styles
│   ├── edit_note.css      # Edit note styles
│   ├── view_note.css      # View note details styles
│   ├── completed_task.css # Completed tasks page styles
│   └── popup.css          # Success popup styles
├── php/                    # Backend PHP files
│   ├── db_connect.php     # Database connection
│   ├── StickyNote.php     # Main page
│   ├── add_note.php       # Add new note handler
│   ├── edit_note.php      # Edit note handler
│   ├── view_note.php      # View note details
│   ├── delete_note.php    # Delete note handler
│   ├── update_status.php  # Update task status
│   ├── completed_task.php # Completed tasks page
│   ├── check_reminders.php# Reminder checking API
│   ├── generate_repeat.php# Repeat task generation
│   └── success_popup.php  # Success popup component
├── js/                     # JavaScript files
│   └── ToogleList.js      # Toggle list functionality
├── icon/                   # Icons and images
│   ├── logo.png
│   ├── complete-btn.png
│   ├── uncomplete-btn.png
│   └── ...
└── README.md
```

## Prerequisites

- PHP 7.0 or higher
- MySQL 5.7 or higher
- Web server (Apache/Nginx) or PHP built-in server
- Modern web browser with JavaScript enabled

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/ongcw11/sticky-note-web-app.git
   cd sticky-note-web-app
   ```

2. **Set up the database**
   - Create a MySQL database named `stickynote`
   - Import the database schema (you'll need to create tables based on the code structure)
   - Update database credentials in `php/db_connect.php`:
     ```php
     $servername = "localhost";
     $username = "your_username";
     $password = "your_password";
     $dbname = "stickynote";
     ```

3. **Database Schema**
   The application requires the following tables:
   - `notes` - Main notes/tasks table
   - `subtasks` - Subtasks for each note
   - `repeat_task` - Repeat task configuration
   - `reminders` - Reminder settings

4. **Configure the web server**
   - If using Apache/Nginx, point the document root to the project directory
   - Or use PHP's built-in server:
     ```bash
     php -S localhost:8000
     ```

5. **Access the application**
   - Open your browser and navigate to `http://localhost:8000/php/StickyNote.php`
   - Or configure your web server accordingly

## Usage

### Creating a Note
1. Click the "add new note" button
2. Fill in the task details:
   - Title (required)
   - Remarks/Description
   - Category
   - Date and Time
   - Optional: Enable repeat task
   - Optional: Enable reminder
   - Optional: Add subtasks
3. Click "Save" to create the note

### Editing a Note
1. Click the menu button (⋯) on any note card
2. Select "Edit"
3. Modify the details and save

### Completing a Task
- Click the complete button (✓) on any pending task
- Or click the uncomplete button on a completed task to mark it as pending again

### Filtering Tasks
- Use the filter buttons at the top to filter tasks by category
- Click "All" to view all tasks

### Viewing Completed Tasks
- Click "Check All Completed Tasks" at the bottom of the main page
- View all tasks that have been completed

## Browser Notifications

The app uses browser notifications for reminders. When you first access the application:
1. Your browser will ask for notification permission
2. Allow notifications to receive reminder alerts
3. Reminders are checked automatically every minute

## Configuration

### User ID
Currently, the application uses a hardcoded user ID (`fk_user = 1`). To support multiple users:
- Modify `php/StickyNote.php` and other PHP files to use session-based user authentication
- Update all queries to use the authenticated user's ID

### Timezone
The reminder system uses `Asia/Kuala_Lumpur` timezone. To change it:
- Update `date_default_timezone_set()` in `php/check_reminders.php`

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**ongcw11**
- GitHub: [@ongcw11](https://github.com/ongcw11)

## Acknowledgments

- Poppins font from Google Fonts
- Icons and UI elements designed for the application
