## Application Dependencies

The Udagram application consists of two main components: 

- The frontend (Angular).  
- The backend API (Node.js/Express with TypeScript).   
Each component has its own set of dependencies.

### 1. Backend API Dependencies

- **Node.js & npm**: JavaScript runtime and package manager.
- **Express**: Web framework for building RESTful APIs.
- **Sequelize & sequelize-typescript**: ORM for interacting with PostgreSQL.
- **pg**: PostgreSQL client for Node.js.
- **bcryptjs**: Library for hashing passwords.
- **jsonwebtoken**: For creating and verifying JWT tokens (authentication).
- **aws-sdk**: AWS SDK for interacting with S3 and other AWS services.
- **dotenv**: Loads environment variables from `.env` files.
- **body-parser, cors**: Middleware for parsing requests and enabling CORS.
- **email-validator**: Validates email addresses.
- **reflect-metadata**: Enables TypeScript decorators.

### 2. Frontend Dependencies

- **Angular**: Main frontend framework.
- **Ionic Framework**: UI toolkit for building cross-platform apps.
- **RxJS**: Reactive programming library used by Angular.
- **Angular CLI**: Command-line tools for Angular development.
- **Typescript**: Superset of JavaScript for type safety.
- **Bootstrap**: (if used) For responsive UI components.

### 3. Infrastructure Dependencies

- **PostgreSQL (RDS)**: Relational database for storing user and image data.
- **AWS S3**: Storage for uploaded images and static frontend files.
- **AWS Elastic Beanstalk**: Platform for deploying and managing the backend API.
- **AWS CloudFront**: (optional) CDN for serving frontend assets globally.
- **CircleCI**: Continuous Integration/Continuous Deployment pipeline.

### 4. Development & Testing Tools

- **ts-node-dev / ts-node**: For running TypeScript code in development.
- **Jest / Jasmine / Karma**: (if configured) For unit and integration testing.
- **ESLint / TSLint**: For code linting and style checks.

---

**Note:**  
All dependencies are managed via `package.json` files in both the `udagram-api` and `udagram-frontend` directories.  
Environment variables are required for database credentials, AWS access, and JWT secrets.