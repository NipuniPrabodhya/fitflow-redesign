\# FitFlow HCI Requirements



\## Overview



This document summarizes the key user requirements identified through the earlier FitFlow Human Computer Interaction activities.



These requirements influenced the technology selection and high-level architecture.



\## Key User Needs



| ID | User Need |

|---|---|

| UN01 | Receive workouts that adapt to available time |

| UN02 | Modify duration, difficulty, and individual exercises |

| UN03 | Understand why an AI workout was recommended |

| UN04 | View progress clearly and quickly |

| UN05 | Record meals with minimal effort |

| UN06 | Correct food-recognition results |

| UN07 | Receive beginner-friendly exercise guidance |

| UN08 | Participate in private social activities |

| UN09 | Receive meaningful motivation and achievements |

| UN10 | Access important features quickly |



\## Prioritized User Requirements



| ID | Requirement | Priority |

|---|---|---|

| UR01 | Users should receive AI-personalized workouts based on fitness goals, fitness level, available time, and equipment. | High |

| UR02 | Users should be able to adjust workout duration and difficulty. | High |

| UR03 | Users should be able to replace, skip, or regenerate unsuitable exercises. | High |

| UR04 | Users should receive understandable explanations for AI workout recommendations. | High |

| UR05 | Users should be able to record injuries and physical limitations. | High |

| UR06 | Beginners should receive clear exercise instructions, demonstrations, and safe alternatives. | High |

| UR07 | Users should see weekly progress summaries and achievements. | High |

| UR08 | Users should be able to log meals using camera-based recognition. | High |

| UR09 | Users should be able to edit recognized foods and portion sizes. | High |

| UR10 | Users should be able to join invitation-only communities and challenges. | High |

| UR11 | Users should be able to control the visibility of personal fitness information. | High |

| UR12 | Users should receive customizable reminders and milestone notifications. | Medium |

| UR13 | Users should be able to skip optional onboarding questions. | Medium |

| UR14 | Users should be able to access major features using simple navigation. | High |



\## Core User Flows



\### Home Dashboard



Home Dashboard  

→ View AI Daily Flow  

→ Review Today's Workout  

→ Start Workout  

→ Complete Workout  

→ View Updated Progress



\### AI Workout Planner



Home Dashboard  

→ Workout Planner  

→ Select Available Time  

→ Select Fitness Level  

→ Select Goal  

→ Select Available Equipment  

→ Add Limitations if Required  

→ Generate AI Workout  

→ Review Recommended Workout  

→ Replace / Edit Exercise  

→ Start Workout



\### Progress Tracking



Home Dashboard  

→ Progress  

→ View Weekly Summary  

→ View Workout Statistics  

→ View Nutrition Statistics  

→ View Streak  

→ View Achievements



\### Community



Home Dashboard  

→ Community  

→ Browse Challenges  

→ Select Challenge  

→ View Challenge Information  

→ View Privacy Information  

→ Join Challenge  

→ Track Group Progress



\### Nutrition



Home Dashboard  

→ Nutrition  

→ Scan Food with Camera  

→ Food Recognition Result  

→ Edit Food if Necessary  

→ Adjust Portion Size  

→ Confirm Meal  

→ Save Nutrition Record  

→ View Updated Daily Nutrition Summary



\## Technical Mapping



| HCI Requirement | Technical Support |

|---|---|

| AI-personalized workouts | FastAPI AI service |

| Adjustable workouts | NestJS workout service |

| Replace exercise | AI recommendation endpoint |

| Why This Workout? | AI explanation metadata |

| Progress summaries | PostgreSQL analytics + Redis caching |

| Camera meal logging | React Native camera + AI recognition |

| Food correction | Editable nutrition records |

| Private challenges | NestJS authorization + PostgreSQL membership data |

| Privacy controls | Firebase Auth + backend authorization |

| Simple navigation | React Native navigation |

