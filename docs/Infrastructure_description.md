## Infrastructure UML Diagram  
Udagram - an Image Filtering application, allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering service. It has two components:

- Frontend - Angular web application built with Ionic framework.
- Backend RESTful API - Node-Typescript application.

```
+-------------------+        +-------------------+        +-------------------+
|                   |        |                   |        |                   |
|      Client       +------->+   CloudFront CDN  +------->+    S3 Bucket      |
|   (Web Browser)   |        | (optional, for    |        | (Static Frontend) |
|                   |        |  frontend assets) |        |                   |
+-------------------+        +-------------------+        +-------------------+
         |                                                        ^
         |                                                        |
         v                                                        |
+-------------------+        +-------------------+        +-------+-----------+
|                   |        |                   |        |                   |
|      Client       +------->+ Elastic Beanstalk +------->+      RDS          |
|   (Web/Mobile)    |        |   (API Server)    |        |   (Postgres DB)   |
|                   |        |                   |        |                   |
+-------------------+        +-------------------+        +-------------------+
         |                                                        ^
         |                                                        |
         +--------------------------------------------------------+
         |                |
         v                |
+-------------------+     |
|                   |     |
|      S3 Bucket    <-----+
| (Image Uploads)   |
|                   |
+-------------------+

         ^
         |
         |
+-------------------+
|                   |
|    CircleCI       |
| (CI/CD Pipeline)  |
|                   |
+-------------------+
         |
         v
+-------------------+        +-------------------+
|                   |        |                   |
|   Elastic         |        |      S3           |
|   Beanstalk       |        | (Frontend Deploy) |
|   (API Deploy)    |        |                   |
+-------------------+        +-------------------+

         |
         v
+-------------------+
|                   |
|       VPC         |
| (Virtual Private  |
|    Cloud for      |
|  Beanstalk & RDS) |
|                   |
+-------------------+
```

**Legend:**
- **Client**: User's browser or mobile app
- **CloudFront**: (optional) CDN for frontend assets
- **S3 Bucket**: Hosts static `udagram frontend` and stores uploaded images
- **Elastic Beanstalk**: Hosts Node.js/Express API such as `udagram-api`
- **RDS**: PostgreSQL database
- **CircleCI**: Automates build, test, and deployment to Elastic Beanstalk and S3
- **VPC**: Provides private networking for Elastic Beanstalk and RDS
