# Week 8 Task Manager Full Stack Project

🚀 FULL STACK TASK MANAGER
==========================

🌟 APPLICATION STARTED
----------------------
✅ Backend: Spring Boot running on http://localhost:8080
✅ Frontend: React running on http://localhost:3000
✅ Database: PostgreSQL connected
✅ WebSocket: Ready for real-time updates
✅ Authentication: JWT configured

👤 AUTHENTICATION FLOW:
-----------------------
1. User visits http://localhost:3000
2. Redirected to login page if not authenticated
3. User enters credentials:
   - Email: user@example.com
   - Password: password123
4. API Call: POST /api/auth/login
5. Response: JWT tokens returned
6. Frontend stores tokens in secure storage
7. User redirected to dashboard

📱 FRONTEND DASHBOARD:
----------------------
┌─────────────────────────────────────────────────────┐
│                    TASK MANAGER                      │
├─────────────────────────────────────────────────────┤
│ 👋 Welcome, John Doe!                                │
│ 📊 Stats: 12 tasks • 3 overdue • 5 completed         │
│                                                    │
│ 🔍 Search: [____________________]                   │
│                                                    │
│ 📋 TASK BOARD (Drag & Drop)                         │
│ ┌─────────────┬─────────────┬─────────────┐       │
│ │   TODO      │ IN PROGRESS │  COMPLETED  │       │
│ ├─────────────┼─────────────┼─────────────┤       │
│ │ • Fix login │ • API docs  │ • Homepage  │       │
│ │ • Add tests │ • Dashboard │ • Auth flow │       │
│ │ • Deploy    │             │             │       │
│ └─────────────┴─────────────┴─────────────┘       │
│                                                    │
│ 🎯 RECENT ACTIVITY:                                 │
│ • John updated "Fix login" status                   │
│ • Sarah commented on "API docs"                    │
│ • New task "Deploy to production" created          │
└─────────────────────────────────────────────────────┘

🔧 REAL-TIME UPDATES:
--------------------
WebSocket Connection: ws://localhost:8080/ws

Sample WebSocket Messages:
{
  "type": "TASK_UPDATED",
  "payload": {
    "taskId": 123,
    "newStatus": "IN_PROGRESS",
    "updatedBy": "john@example.com",
    "timestamp": "2024-01-25T14:30:00Z"
  }
}

{
  "type": "TASK_CREATED",
  "payload": {
    "id": 124,
    "title": "New Feature Request",
    "createdBy": "sarah@example.com",
    "timestamp": "2024-01-25T14:31:00Z"
  }
}

📊 API INTERACTIONS:
-------------------
Frontend API Calls:
1. GET /api/tasks?status=TODO&page=0&size=10
   Response: 200 OK with 10 tasks
   
2. POST /api/tasks
   Request: {"title":"New Task","description":"...","priority":"HIGH"}
   Response: 201 CREATED with task details
   
3. PUT /api/tasks/123/status
   Request: {"status":"IN_PROGRESS"}
   Response: 200 OK with updated task
   
4. WebSocket: Task status update broadcasted to all connected clients

🔐 SECURITY HEADERS:
-------------------
Request Headers:
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
Content-Type: application/json
Accept: application/json

Response Headers:
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
Content-Security-Policy: default-src 'self'
Strict-Transport-Security: max-age=31536000

⚡ PERFORMANCE METRICS:
----------------------
Frontend:
• First Contentful Paint: 1.2s
• Time to Interactive: 2.1s
• Bundle Size: 150KB gzipped
• API Response Time: < 100ms

Backend:
• JVM Memory: 256MB used / 512MB allocated
• Database Connections: 5/20 active
• Request Rate: 45 requests/minute
• Error Rate: 0.1%

🐳 DOCKER CONTAINERS:
-------------------
CONTAINER ID   IMAGE                     STATUS    PORTS
abc123def456   taskmanager-frontend:latest Up 2 minutes 0.0.0.0:3000->3000/tcp
def456abc123   taskmanager-backend:latest  Up 2 minutes 0.0.0.0:8080->8080/tcp
ghi789def012   postgres:15-alpine         Up 2 minutes 0.0.0.0:5432->5432/tcp

📈 MONITORING ENDPOINTS:
-----------------------
• Health Check: http://localhost:8080/actuator/health
• Metrics: http://localhost:8080/actuator/metrics
• Info: http://localhost:8080/actuator/info
• Loggers: http://localhost:8080/actuator/loggers

🧪 TEST COVERAGE:
-----------------
Backend Tests:
• Unit Tests: 95% coverage
• Integration Tests: 85% coverage
• Security Tests: 100% of endpoints

Frontend Tests:
• Component Tests: 90% coverage
• Integration Tests: 80% coverage
• E2E Tests: 10 critical user flows
📤 Submission Requirements:
GitHub Structure:

week8-task-manager-fullstack/
│── backend/ (Spring Boot)
│ ├── src/main/java/com/taskmanager/
│ │ ├── TaskManagerApplication.java
│ │ ├── config/
│ │ │ ├── SecurityConfig.java
│ │ │ ├── WebSocketConfig.java
│ │ │ └── CorsConfig.java
│ │ ├── controller/
│ │ │ ├── AuthController.java
│ │ │ ├── TaskController.java
│ │ │ └── WebSocketController.java
│ │ ├── service/
│ │ │ ├── AuthService.java
│ │ │ ├── TaskService.java
│ │ │ └── WebSocketService.java
│ │ ├── security/
│ │ │ ├── JwtTokenProvider.java
│ │ │ └── JwtAuthenticationFilter.java
│ │ └── model/
│ │ ├── entity/
│ │ ├── dto/
│ │ └── enums/
│ ├── src/main/resources/
│ │ ├── application.yml
│ │ └── db/migration/
│ ├── Dockerfile
│ └── pom.xml
│── frontend/ (React TypeScript)
│ ├── src/
│ │ ├── components/
│ │ │ ├── TaskList.tsx
│ │ │ ├── TaskForm.tsx
│ │ │ ├── LoginForm.tsx
│ │ │ └── Layout/
│ │ ├── pages/
│ │ │ ├── Dashboard.tsx
│ │ │ ├── Login.tsx
│ │ │ └── TaskDetail.tsx
│ │ ├── services/
│ │ │ ├── api.ts
│ │ │ ├── auth.ts
│ │ │ └── websocket.ts
│ │ ├── hooks/
│ │ │ ├── useTasks.ts
│ │ │ └── useAuth.ts
│ │ ├── context/
│ │ │ ├── AuthContext.tsx
│ │ │ └── TaskContext.tsx
│ │ ├── types/
│ │ │ └── task.ts
│ │ ├── styles/
│ │ ├── App.tsx
│ │ └── main.tsx
│ ├── public/
│ ├── Dockerfile
│ ├── package.json
│ ├── tsconfig.json
│ └── vite.config.ts
│── docker-compose.yml
│── .github/workflows/
│── README.md
└── .gitignore
