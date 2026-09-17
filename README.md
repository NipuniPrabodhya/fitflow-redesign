\# FitFlow Redesign



FitFlow is a redesigned fitness-tracking application developed for the

IT3060 – Human Computer Interaction module.



The redesign focuses on improving personalization, workout planning,

nutrition tracking, progress visualization, social accountability,

privacy, and overall usability.



\## Project Background



Previous user research identified several major usability problems in FitFlow:



\- Limited workout personalization

\- Difficult and time-consuming nutrition logging

\- Poor progress visualization

\- Social privacy concerns

\- Navigation friction

\- Limited support for beginner users



The redesigned FitFlow solution introduces AI-powered workout planning,

camera-based nutrition tracking, improved progress visualization,

private social challenges, and clearer user controls.



\## Core Features



\- AI-personalized Daily Flow workouts

\- AI Workout Planner

\- Adjustable workout duration and difficulty

\- Exercise replacement and skipping

\- "Why This Workout?" AI explanation

\- Workout session tracking

\- Progress dashboard

\- Camera-based nutrition recognition

\- Food and portion correction

\- Private community challenges

\- Privacy controls

\- Persistent bottom navigation

\- Cross-platform mobile and web access



\## Technology Stack



\### Mobile Frontend

\- React Native

\- TypeScript



\### Web Frontend

\- React

\- Next.js

\- TypeScript



\### Backend

\- Node.js

\- NestJS

\- REST API

\- WebSockets



\### AI Service

\- Python

\- FastAPI

\- TensorFlow / PyTorch / TensorFlow Lite where appropriate



\### Database

\- PostgreSQL



\### Cache and Real-Time Layer

\- Redis

\- Redis Pub/Sub

\- WebSockets



\### Authentication

\- Firebase Authentication

\- Firebase Identity Platform where required



\### Storage

\- Secure cloud object storage for meal images and profile media



\### DevOps

\- Git

\- GitHub

\- Docker

\- GitHub Actions



\## Main User Flows



\### Workout Flow



Home Dashboard  

→ AI Workout Planner  

→ Generate Workout  

→ AI Workout Recommendation / Daily Flow  

→ Start Workout  

→ Workout Session  

→ Progress Dashboard



\### Nutrition Flow



Home Dashboard  

→ Nutrition Logger  

→ Scan Food  

→ Food Recognition  

→ Edit Food / Adjust Portion  

→ Confirm and Save



\### Community Flow



Home Dashboard  

→ Community Feed  

→ Challenge Details  

→ Review Privacy Information  

→ Join Challenge



\### Progress Flow



Home Dashboard  

→ Progress Dashboard  

→ Weekly Progress  

→ Workout Statistics  

→ Streaks and Achievements



\## High-Level Architecture



The React Native mobile application and React/Next.js web application

communicate with a NestJS backend through secure REST APIs and WebSockets.



The NestJS backend manages:



\- Users

\- Workouts

\- Nutrition records

\- Progress

\- Community challenges

\- Authorization

\- Real-time communication



PostgreSQL is used as the primary database.



Redis is used for caching, rate limiting, Pub/Sub, and real-time communication.



A separate FastAPI-based Python microservice handles AI-related functions such as:



\- Personalized workout recommendations

\- Exercise replacement

\- Food recognition

\- AI recommendation explanations



Firebase Authentication is used for user authentication.



\## Security Considerations



The FitFlow architecture follows the following security principles:



\- HTTPS/TLS communication

\- JWT token validation

\- Role-based and policy-based authorization

\- Encryption of data at rest

\- Secure secret management

\- Data minimization

\- Privacy-aware community features

\- Audit logging

\- Secure handling of health and fitness information

\- User data deletion and export support

\- No API keys or passwords stored in GitHub



\## Project Structure



```text

fitflow-redesign/

│

├── frontend/

│   ├── mobile/

│   └── web/

│

├── backend/

│

├── ai-service/

│

├── shared/

│

├── database/

│

├── docs/

│   ├── architecture/

│   ├── adr/

│   ├── comparisons/

│   └── hci/

│

├── .github/

│   └── workflows/

│

├── .gitignore

├── docker-compose.yml

└── README.md





Documentation



Supporting project documentation is available in the docs directory.



docs/architecture



Contains the FitFlow high-level system architecture.



docs/adr



Contains Architecture Decision Records.



docs/comparisons



Contains frontend, backend, database, authentication, and weighted decision matrices.



docs/hci



Contains supporting HCI requirements and prototype information.



Repository



Repository Name:



fitflow-redesign



Module Information



Module: IT3060 – Human Computer Interaction

Degree: BSc (Hons) in Information Technology

Year: 3rd Year

Semester: 2nd Semester – 2026

Faculty: Faculty of Computing, SLIIT

