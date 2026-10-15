## Deploy Project

## 1. Project Overview

A full-stack task planning application deployed on a Linux VPS. I got the front and back-end from an educational youtube video (RED Group).

The goal of this project was to gain practical experience in server administration, application deployment, database configuration, process management, and reverse proxy setup.

**My focus:** infrastructure setup, deployment, configuration, troubleshooting, and application availability.

## 2. My Responsibilities

- Prepared and configured an Ubuntu VPS.
- Set up SSH access and the server environment.
- Installed and configured PostgreSQL.
- Configured application environment variables and database connectivity.
- Built and deployed the application services.
- Configured PM2 for process management.
- Set up Nginx as a reverse proxy.
- Troubleshot API connectivity, authentication, cookies, and configuration issues.
- Verified that the application was accessible through the server's public IP.

## 3. Infrastructure & Technologies

| Technology | Purpose |
|---|---|
| Ubuntu Server | VPS operating system |
| SSH | Remote server administration |
| Node.js | JavaScript runtime |
| PostgreSQL | Database |
| PM2 | Application process management |
| Nginx | Web server and reverse proxy |
| Git | Source code management |

## 4. Architecture

The application runs on a VPS with separate frontend and backend services and a PostgreSQL database.

- **Frontend:** Next.js, running on port `3000`
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ff96dd7c-4dac-4592-ae0b-b70ea4df9230" />

- **Backend API:** NestJS, running on port `4200`
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/805facd0-755c-4087-82e1-201d3f9d6279" />

- **Database:** PostgreSQL
- **Process manager:** PM2
- **Reverse proxy:** Nginx

The browser connects to Nginx, which routes requests to the appropriate application service.

## 5. Deployment Process

### 5.1 — VPS Preparation
- Prepared the Ubuntu server.
- Configured remote access over SSH.
- Installed the required runtime and development tools.
- Connected local front and back-end from my Linux to Github. It is then accessed by the VPS
  <img width="1920" height="1080" alt="Screenshot_20261012_182658" src="https://github.com/user-attachments/assets/70b71fff-be35-4c3a-b834-cf9a164a68ba" />


### 5.2 — Database Setup
- Installed PostgreSQL.
- Created the application database and database user.
- Configured database connection settings.
  <img width="1920" height="915" alt="Screenshot_20261014_123858" src="https://github.com/user-attachments/assets/45bea8a0-50be-4b22-9a02-0912922dff41" />


### 5.3 — Environment Configuration
- Configured environment variables for the frontend and backend.
- Set up the backend connection to PostgreSQL.
- Configured the API URL and cross-origin request settings.

  
### 5.4 — Application Deployment
- Retrieved the application source code.
- Installed dependencies.
- Built the application services.
- Prepared the application to run on the server.

  
### 5.5 — Process Management
- Started the services using PM2.
- Inspected process status and application logs.
- Verified that the services could be restarted.
  <img width="1920" height="1012" alt="Screenshot_20261014_130907" src="https://github.com/user-attachments/assets/53cbcd2d-363a-4d62-84df-f1b8049d9701" />


### 5.6 — Nginx Configuration
- Configured Nginx as a reverse proxy.
- Routed incoming requests to the appropriate application services.
- Tested the configuration and verified external access.
  <img width="601" height="487" alt="image" src="https://github.com/user-attachments/assets/9750d253-e605-435e-8a2a-32869b80ba1a" />


## 6. Troubleshooting & Problem Solving

During deployment, I've encountered a lot of small and significant obstacles. I did document some of them:

### Port errors
Apache was occupying port 80 (where nginx was) had to disable it. Still the site did not open. It happened because I forgot to configure the firewall.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c137963f-cbe7-4db3-a959-7822d3978d5e" />

### Authentication & Cookies
Investigated browser console errors and network requests to understand why authentication was not working as expected. Traced the login flow between the frontend and backend, reviewed cookie handling and authentication-related configuration, and made code changes on both sides to improve communication and ensure login requests were handled correctly.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/867cd859-af0d-4146-811b-c047160a7590" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cf752514-23a2-4659-9bb2-63b2c6221391" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/79d66351-6a40-4911-a08f-8d86e8f4d7ed" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c55d7d9a-c291-4146-8749-90e29a6efeef" />

### Validation Errors
Investigated a case where the backend rejected a login request because the password did not meet the minimum length requirement, while the frontend did not display the returned validation error clearly (it did in the browser devtools).
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/035cc2ea-9f82-404a-8b51-e2dc16e78b13" />


**Key takeaway:** Successful deployment involves not only starting services, but also verifying how they communicate and how errors are handled across the application.

## 7. Security Considerations

- Use SSH for remote administration.
- Keep secrets and database credentials out of Git.
- Restrict externally accessible ports.
- Avoid exposing the PostgreSQL service unnecessarily.
- Validate Nginx and application configuration before restarting services.
- Configure HTTPS before using the application for production traffic.

## 8. Challenges & Lessons Learned

This project helped me gain practical experience with:

- Troubleshooting: Gained additional experience in error investigation using Chrome DevTools, browser network requests, and server logs.
- Authentication: Investigated login issues, cookie handling, and frontend-backend interactions.
- Full-Stack Debugging: Modified frontend and backend code to address issues discovered during testing.
- Server Management: Gained practical experience with Ubuntu, PM2, and running application services.
- Deployment & Infrastructure: Learned how the frontend, backend, PostgreSQL, and Nginx work together on a VPS.

## 9. Future Improvements

- Configure a domain name and HTTPS.
- Improve server monitoring and log management.
- Automate deployment.
- Add database backup and recovery procedures.
- Strengthen server security and operational reliability.

## 10. Project Links

## 11. Attribution

The application is based on an existing educational project. This repository documents my deployment work, server configuration, troubleshooting, and learning outcomes.
