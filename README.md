# TaskTrack — Smart Task Management System

TaskTrack is a task management application designed to help users organize daily activities, prioritize tasks, and track their progress efficiently.

## Features
- Add new tasks with title, priority, and due date
- Mark tasks as completed
- Delete tasks
- Search tasks by title
- Filter tasks based on status
- View task statistics and progress
- Save tasks using browser local storage

## Technologies Used
- **Frontend:** HTML, CSS, JavaScript
- **Backend:** Java, Spring Boot
- **Database:** H2 Database
- **Build Tool:** Maven

## Project Structure
```text
tasktrack/
├── index.html
├── README.md
└── backend/
    ├── pom.xml
    └── src/
        └── main/
            ├── java/tasktrack/
            └── resources/
                └── application.properties
```

## Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/shyamkumar9933/tasktrack.git
   ```
2. Open `index.html` in a browser to use the frontend.
3. To run the Spring Boot backend, use Java 21 and Maven from the `backend` directory:
   ```bash
   mvn spring-boot:run
   ```
4. The backend API is available at:
   `http://localhost:8080/api/tasks`

## Future Improvements
- Connect the frontend directly to the backend API
- Add user authentication
- Deploy the application online

## Author
**Shyam Kumar**

GitHub: [@shyamkumar9933](https://github.com/shyamkumar9933)
