# TaskTrack – Smart Task Management Application

TaskTrack is a web-based task management application that helps users organize daily activities, prioritize tasks, track deadlines, and monitor their progress through a simple and responsive dashboard.

The application uses a frontend built with HTML, CSS, and JavaScript, connected to a REST API developed using Spring Boot. Task information is stored using Spring Data JPA and an H2 database.

## Live Demo

- **Frontend:** https://shyamkumar9933.github.io/tasktrack/
- **Backend API:** https://tasktrack-kq0l.onrender.com/api/tasks
- **GitHub Repository:** https://github.com/shyamkumar9933/tasktrack

## Features

- **Create Tasks:** Add new tasks with a title, priority, and optional due date.
- **Delete Tasks:** Remove tasks that are no longer needed.
- **Task Completion:** Mark tasks as completed or pending.
- **Priority Management:** Assign High, Medium, or Low priority to tasks.
- **Due Date Tracking:** Set deadlines and identify overdue tasks.
- **Task Filtering:** View all tasks, pending tasks, or completed tasks.
- **Search Functionality:** Find tasks using the search field.
- **Dashboard Statistics:** View total, completed, and pending task counts.
- **Persistent Storage:** Store and retrieve tasks through the backend API and database.
- **Responsive Interface:** Use the application on desktop and mobile screens.

## Technology Stack

### Frontend
- HTML5
- CSS3
- JavaScript
- Fetch API for HTTP communication

### Backend
- Java 21
- Spring Boot 3.5.6
- Spring Web
- Spring Data JPA
- Maven

### Database
- H2 Database

### Deployment
- GitHub Pages – Frontend hosting
- Render – Backend hosting
- GitHub – Source code management

## System Architecture

The application follows a frontend–backend architecture.

1. The user interacts with the TaskTrack interface.
2. JavaScript sends HTTP requests to the Spring Boot REST API.
3. The backend processes requests through the task controller.
4. Spring Data JPA communicates with the H2 database.
5. The backend returns task data as JSON.
6. The frontend updates the task list and dashboard statistics.

```text
User
 |
 v
TaskTrack Frontend
HTML + CSS + JavaScript
 |
 | HTTP / JSON
 v
Spring Boot REST API
 |
 v
Task Controller
 |
 v
Spring Data JPA
 |
 v
H2 Database
```

## REST API Endpoints

The backend exposes the following endpoints under `/api/tasks`.

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/tasks` | Retrieve all tasks |
| POST | `/api/tasks` | Create a new task |
| PUT | `/api/tasks/{id}` | Update an existing task |
| DELETE | `/api/tasks/{id}` | Delete a task |

### Example API Request

Create a task using `POST /api/tasks` with a JSON request body:

```json
{
  "title": "Complete project documentation",
  "priority": "High",
  "dueDate": "2026-11-01",
  "completed": false
}
```

The backend returns the saved task, including its generated ID.

## Project Structure

```text
tasktrack/
├── index.html
├── README.md
└── backend/
    ├── Dockerfile
    ├── pom.xml
    └── src/
        └── main/
            ├── java/
            │   └── com/
            │       └── tasktrack/
            │           ├── TasktrackApplication.java
            │           ├── Task.java
            │           ├── TaskController.java
            │           └── TaskRepository.java
            └── resources/
                └── application.properties
```

## Run the Project Locally

### Prerequisites

Install the following:
- Java JDK 21
- Apache Maven
- Git
- A modern web browser

### 1. Clone the Repository

```bash
git clone https://github.com/shyamkumar9933/tasktrack.git
cd tasktrack
```

### 2. Start the Backend

```bash
cd backend
mvn spring-boot:run
```

The Spring Boot application starts on port `8080` by default.

Test the API in your browser:

http://localhost:8080/api/tasks

### 3. Start the Frontend

Open the root `index.html` using Visual Studio Code with the Live Server extension.

The frontend's API URL must point to the backend you want to use:

```javascript
const API_URL = "http://localhost:8080/api/tasks";
```

Use the local URL when running the backend locally. For the deployed application, use the deployed backend URL instead.

## Database Configuration

The backend uses H2 with Spring Data JPA.

Current configuration:

```properties
spring.datasource.url=jdbc:h2:file:./data/tasktrackdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console
```

The database uses file-based storage in the configured runtime environment. Persistence across hosting restarts or redeployments depends on the host's persistent storage configuration.

## Deployment

The frontend is published through GitHub Pages, and the Spring Boot backend is deployed on Render.

- Frontend: https://shyamkumar9933.github.io/tasktrack/
- API: https://tasktrack-kq0l.onrender.com/api/tasks

The frontend must use the deployed backend URL for public access. Render's free service may take some time to respond after periods of inactivity.

## Future Improvements

- User authentication and individual task lists
- PostgreSQL integration for production database storage
- Task editing and recurring tasks
- Task reminders and notifications
- Pagination and advanced filtering
- Improved error handling and automated tests
- Enhanced accessibility and user experience

## Learning Outcomes

This project demonstrates practical experience with:
- Building a responsive web interface
- Developing RESTful APIs using Spring Boot
- Implementing CRUD operations
- Connecting a frontend to a backend using HTTP and JSON
- Persisting application data with Spring Data JPA and H2
- Using GitHub for source control and GitHub Pages for deployment
- Containerizing and deploying a Java application

## Author

**Shyam Kumar**

GitHub: https://github.com/shyamkumar9933

---

If you find this project useful, feel free to explore the repository and its implementation.
