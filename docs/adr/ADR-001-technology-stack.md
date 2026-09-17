\# ADR-001: FitFlow Technology Stack Selection



\## Status



Accepted



\## Date



2026



\## Context



FitFlow is a redesigned fitness-tracking platform that must support:



\- Android and iOS applications

\- Web access

\- AI-personalized workout recommendations

\- Camera-based nutrition recognition

\- Progress tracking

\- Community challenges

\- Real-time updates

\- Secure user authentication

\- Privacy controls

\- Sensitive health and fitness information

\- Scalable future development



Previous HCI activities identified personalization, nutrition logging, progress visualization, user control, privacy, and simple navigation as major requirements.



The selected technical architecture must therefore provide:



\- Good performance

\- Cross-platform support

\- Fast development

\- AI/ML integration

\- Real-time capabilities

\- Strong security

\- Scalability

\- Maintainability

\- Reasonable cost



Several frontend, backend, database, and authentication technologies were evaluated using comparison tables and weighted decision matrices.



\---



\## Decision



The following technology stack will be used for the FitFlow redesign.



\### Frontend



\*\*React Native + TypeScript\*\*



for Android and iOS.



\*\*React / Next.js + TypeScript\*\*



for the web application.



\### Main Backend



\*\*Node.js + NestJS + TypeScript\*\*



\### AI Microservice



\*\*Python + FastAPI\*\*



\### Primary Database



\*\*PostgreSQL\*\*



\### Cache and Real-Time Layer



\*\*Redis\*\*



\### Real-Time Communication



\*\*WebSockets\*\*



\### Authentication



\*\*Firebase Authentication / Identity Platform\*\*



\### Object Storage



\*\*Secure cloud object storage\*\*



\### AI/ML



Possible technologies include:



\- TensorFlow

\- PyTorch

\- TensorFlow Lite



\### DevOps



\- Git

\- GitHub

\- Docker

\- GitHub Actions



\---



\## Decision Rationale



\### React Native



React Native was selected because it provides:



\- Strong Android and iOS support

\- High code reuse

\- Good development speed

\- TypeScript support

\- Camera integration

\- Real-time support

\- Large ecosystem

\- Lower maintenance cost than separate native applications



It also integrates well with a TypeScript-based backend.



\### React / Next.js



React / Next.js was selected for web access because it provides:



\- Strong browser support

\- Good maintainability

\- Reuse of TypeScript models

\- Responsive interface development

\- Large ecosystem



\### NestJS



NestJS was selected as the main backend because it provides:



\- Modular architecture

\- Strong TypeScript support

\- REST API development

\- WebSocket support

\- Dependency injection

\- Good scalability

\- Good maintainability

\- Easy integration with React Native



\### FastAPI



FastAPI was selected as the AI microservice because Python has a strong machine-learning and computer-vision ecosystem.



It can support:



\- AI workout recommendations

\- Exercise replacement

\- Food recognition

\- Recommendation explanations

\- Model inference



\### PostgreSQL



PostgreSQL was selected because FitFlow contains strongly related information such as:



\- Users

\- Workout plans

\- Exercises

\- Nutrition records

\- Progress

\- Challenges

\- Challenge memberships

\- Privacy settings



PostgreSQL provides:



\- Strong relational integrity

\- Transactions

\- Advanced queries

\- Reporting

\- Analytics

\- JSONB support

\- Security features



\### Redis



Redis was selected to support:



\- Caching

\- Rate limiting

\- Real-time coordination

\- Pub/Sub

\- Frequently requested dashboard data

\- Community challenge updates



\### Firebase Authentication



Firebase Authentication was selected because it provides:



\- Strong mobile support

\- Strong web support

\- Email/password authentication

\- Google sign-in

\- Apple sign-in

\- Token-based authentication

\- Multi-factor authentication where required

\- Fast development



Authorization decisions will remain inside the NestJS backend.



\---



\## Alternatives Considered



\### Flutter



Flutter provides strong cross-platform development and excellent UI consistency.



It was not selected as the primary option because:



\- It introduces Dart as another programming language

\- React/TypeScript provides stronger alignment with the selected backend and web ecosystem

\- TypeScript models can be reused across frontend and backend



\### Kotlin Multiplatform



Kotlin Multiplatform provides strong native performance and business-logic sharing.



It was not selected because:



\- It introduces additional cross-platform complexity

\- Teams may require both Kotlin and Swift knowledge

\- Web UI support is less mature than React-based solutions



\### Swift / SwiftUI



SwiftUI provides excellent Apple-platform performance.



It was not selected as the main frontend because:



\- It does not provide Android support

\- A separate Android application would be required

\- This would increase development and maintenance cost



\### MongoDB



MongoDB provides flexible document storage and strong scalability.



It was not selected as the primary database because:



\- FitFlow contains strongly relational data

\- Progress reporting requires structured queries

\- PostgreSQL provides stronger relational integrity



\### Firebase Cloud Firestore



Firestore provides strong real-time synchronization and mobile integration.



It was not selected as the main database because:



\- Complex relational queries are more difficult

\- Reporting and analytics are less natural

\- PostgreSQL better matches FitFlow's data model



\### DynamoDB



DynamoDB provides very high scalability.



It was not selected because:



\- It requires careful access-pattern design

\- It increases architectural complexity

\- The current FitFlow requirements do not require this level of NoSQL optimization



\### Go



Go provides excellent performance and concurrency.



It was not selected as the main backend because:



\- NestJS provides adequate performance

\- TypeScript improves development speed

\- Introducing Go would add another programming language



\### Auth0



Auth0 provides strong authentication capabilities.



It was not selected because:



\- Firebase Authentication provides a simpler mobile-first integration

\- Firebase provides strong support for Android, iOS, and web

\- Firebase is sufficient for the FitFlow project requirements



\---



\## Consequences



\### Positive Consequences



The selected architecture provides:



\- Strong cross-platform support

\- Fast development

\- Good performance

\- Strong AI/ML integration

\- Secure authentication

\- Real-time communication

\- Scalable backend architecture

\- Strong relational data management

\- Good maintainability

\- Strong TypeScript reuse



\### Negative Consequences



The architecture also introduces several trade-offs:



\- Two backend programming languages must be maintained: TypeScript and Python

\- Redis adds another infrastructure component

\- Firebase Authentication introduces external service dependency

\- Web and mobile user-interface code cannot be completely identical

\- The AI service requires separate deployment and monitoring



\---



\## Security Consequences



The system must implement:



\- HTTPS/TLS

\- Secure token validation

\- Backend authorization

\- Encryption at rest

\- Secure secret management

\- Data minimization

\- Privacy controls

\- Audit logging

\- Secure object storage

\- Controlled access to sensitive fitness data



Authentication alone is not sufficient.



NestJS authorization rules must determine what authenticated users can access.



\---



\## Scalability Consequences



The architecture supports horizontal scaling through:



\- Stateless NestJS services

\- Multiple backend instances

\- Redis Pub/Sub

\- PostgreSQL indexing and replication

\- Independently scalable AI microservices

\- Cloud object storage



\---



\## Relationship to FitFlow HCI Requirements



| HCI Requirement | Technical Decision |

|---|---|

| AI Daily Flow | FastAPI AI recommendation service |

| Workout personalization | AI service + PostgreSQL |

| Replace Exercise | AI alternative recommendation |

| Why This Workout? | Recommendation explanation metadata |

| Progress Dashboard | PostgreSQL analytics + Redis cache |

| Camera nutrition logging | React Native camera + AI service |

| Food correction | Editable PostgreSQL nutrition record |

| Community challenges | NestJS + WebSockets |

| Privacy controls | Firebase Auth + NestJS authorization |

| Cross-platform access | React Native + React / Next.js |



\---



\## Final Decision



The selected FitFlow technology architecture is accepted.



The final core stack is:



\*\*React Native + React/Next.js + NestJS + FastAPI + PostgreSQL + Redis + Firebase Authentication\*\*



This stack provides the most appropriate balance between:



\- Performance

\- Development speed

\- Scalability

\- Security

\- AI integration

\- Cross-platform compatibility

\- Maintainability

\- Cost

