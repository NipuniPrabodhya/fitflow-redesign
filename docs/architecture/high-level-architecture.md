\# FitFlow High-Level Architecture



\## Overview



The FitFlow redesign uses a service-oriented architecture to support cross-platform mobile and web access, AI-based personalization, nutrition recognition, progress tracking, real-time community features, and secure handling of user information.



The main architectural components are:



\- React Native mobile application

\- React / Next.js web application

\- Firebase Authentication / Identity Platform

\- NestJS backend

\- PostgreSQL database

\- Redis cache and real-time layer

\- FastAPI AI microservice

\- Machine-learning models

\- Secure cloud object storage



\---



\## Architecture Diagram



!\[FitFlow High-Level Architecture](fitflow-high-level-architecture.png)



\---



\## Client Layer



\### React Native Mobile Application



The mobile application supports:



\- Android

\- iOS

\- AI Workout Planner

\- Workout Session

\- Progress Dashboard

\- Nutrition Logger

\- Camera-based food scanning

\- Community challenges

\- Notifications

\- Local caching



\### React / Next.js Web Application



The web application provides browser-based FitFlow access.



It can support:



\- Account management

\- Progress monitoring

\- Community access

\- Workout information

\- Administrative interfaces where required



\---



\## Authentication Layer



FitFlow uses:



\*\*Firebase Authentication / Identity Platform\*\*



Authentication responsibilities include:



\- Email and password login

\- Google sign-in

\- Apple sign-in

\- Token generation

\- Multi-factor authentication where required



The client receives an authentication token.



The NestJS backend validates the token before allowing access to protected resources.



\---



\## Application / API Layer



The primary backend is developed using:



\*\*NestJS + TypeScript\*\*



The backend contains the following logical services:



\- User Service

\- Workout Service

\- Nutrition Service

\- Progress Service

\- Community Service

\- Authentication Guards

\- Authorization Policies

\- WebSocket Gateway



The backend is responsible for business logic and communication between clients, databases, AI services, and external services.



\---



\## PostgreSQL Database



PostgreSQL is used as the primary database.



It stores:



\- User profiles

\- Fitness goals

\- Physical limitations

\- Exercises

\- Workout plans

\- Workout sessions

\- Workout completion records

\- Nutrition entries

\- Foods

\- Progress records

\- Challenges

\- Challenge members

\- Achievements

\- Privacy settings

\- AI recommendation metadata

\- Audit information



PostgreSQL was selected because FitFlow contains strongly related data and requires secure transactions, advanced queries, reporting, and analytics.



\---



\## Redis



Redis supports:



\- Caching

\- Rate limiting

\- Real-time communication

\- Pub/Sub

\- Dashboard summaries

\- Challenge updates



PostgreSQL remains the permanent source of truth.



Redis is used only for temporary or frequently accessed information.



\---



\## AI Microservice



The AI microservice is implemented using:



\*\*FastAPI + Python\*\*



Responsibilities include:



\- Personalized workout recommendation

\- Exercise replacement

\- Food recognition

\- AI explanation metadata

\- Model inference



The AI service communicates with the NestJS backend rather than directly exposing sensitive database information to clients.



\---



\## Machine-Learning Models



Possible machine-learning technologies include:



\- TensorFlow

\- PyTorch

\- TensorFlow Lite



TensorFlow Lite may be used for selected on-device tasks where appropriate.



\---



\## Object Storage



Secure cloud object storage is used for:



\- Meal images

\- Profile media

\- AI processing assets



Food images should not be stored directly inside PostgreSQL.



The backend should provide controlled access using secure upload and download mechanisms.



\---



\## Communication



\### Client to Backend



Communication occurs using:



\- HTTPS

\- REST APIs

\- WebSockets



\### Authentication



Firebase Authentication provides JWT-based user identity.



The NestJS backend validates tokens and applies authorization rules.



\### Backend to Database



NestJS communicates with PostgreSQL for persistent application data.



\### Backend to Redis



NestJS uses Redis for:



\- Cache

\- Pub/Sub

\- Rate limiting

\- Real-time coordination



\### Backend to AI Service



NestJS sends AI requests to the FastAPI microservice.



Examples include:



\- Generate personalized workout

\- Replace exercise

\- Recognize food

\- Generate recommendation explanation



\---



\## Scalability Considerations



The architecture supports scalability through:



\- Stateless NestJS backend instances

\- Horizontal scaling

\- Redis-backed real-time coordination

\- PostgreSQL indexing

\- PostgreSQL read replicas where required

\- Independently scalable FastAPI AI instances

\- Cloud object storage

\- Load balancing



\---



\## Security Considerations



The architecture applies the following security principles:



\- HTTPS/TLS

\- JWT validation

\- Role-based and policy-based authorization

\- Encryption at rest

\- Secure secret management

\- Audit logging

\- Data minimization

\- Secure object storage

\- Private challenge controls

\- Secure handling of health and fitness data



Sensitive information such as:



\- Weight

\- Injuries

\- Meal history

\- Physical limitations



should not be stored inside authentication tokens.



\---



\## Relationship to FitFlow HCI Requirements



The architecture directly supports the FitFlow design decisions from previous HCI activities.



| HCI Requirement | Architecture Support |

|---|---|

| AI Daily Flow | FastAPI recommendation service |

| Workout personalization | NestJS + AI service + PostgreSQL |

| Replace Exercise | AI alternative recommendation |

| Why This Workout? | AI explanation metadata |

| Progress Dashboard | PostgreSQL aggregation + Redis cache |

| Camera nutrition logging | React Native camera + AI recognition |

| Food correction | Editable nutrition record |

| Community challenges | NestJS + WebSockets |

| Private communities | Backend authorization |

| Privacy control | Authentication + authorization policies |

| Cross-platform access | React Native + React / Next.js |



\---



\## Summary



The selected FitFlow architecture provides a balance between:



\- Cross-platform support

\- AI integration

\- Performance

\- Scalability

\- Security

\- Maintainability

\- Real-time functionality



It also directly supports the main user requirements and prototype features identified during the earlier FitFlow HCI activities.

