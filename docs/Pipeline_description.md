## CI/CD Pipeline Diagram and Steps

```
+-------------------+
|                   |
|   Developer Push  |
|   (GitHub/Git)    |
|                   |
+---------+---------+
          |
          v
+-------------------+
|                   |
|    CircleCI       |
| (Pipeline Start)  |
|                   |
+---------+---------+
          |
          v
+-------------------+
|                   |
|   Install & Test  |
|  (Install deps,   |
|   lint, run tests)|
+---------+---------+
          |
          v
+-------------------+
|                   |
|    Build          |
| (Frontend & API)  |
+---------+---------+
          |
          v
+-------------------+
|                   |
|   Deploy          |
| (Auto/manual step)|
+---------+---------+
          |
          v
+-------------------+        +-------------------+
|                   |        |                   |
|  Elastic Beanstalk|        |        S3         |
|   (API Deploy)    |        | (Frontend Deploy) |
+-------------------+        +-------------------+
```

**Pipeline Steps Explained:**

1. **Developer Push:**  
   Code is pushed to the repository (e.g., GitHub).

2. **CircleCI Pipeline Start:**  
   CircleCI detects the push and starts the pipeline.

3. **Install & Test:**  
   - Installs dependencies for frontend and backend.
   - Runs linting and automated tests.

4. **Build:**  
   - Builds the frontend Angular app.
   - Compiles the backend API.

5. **Deploy:**  
   - Deploys the backend API to AWS Elastic Beanstalk.
   - Deploys the frontend build to AWS S3 (and optionally invalidates CloudFront cache).

6. **Production:**  
   - The application is live and accessible to users.
