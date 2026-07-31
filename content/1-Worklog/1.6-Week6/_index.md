---
title: "Week 6 Worklog"
date: 2026-07-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

{{% notice tip %}}
Week 6 focused on developing the React/Vite and FastAPI movie application. Registration, login, onboarding, catalog browsing, and interaction tracking were completed before the application was packaged with Docker and tested on EC2.
{{% /notice %}}

## Week 6 Objectives

- Build the movie catalog and detail interfaces.
- Create the FastAPI structure and main APIs.
- Complete registration, login, and onboarding.
- Record user interactions in DynamoDB.
- Run the application with Docker Compose on EC2.

## Tasks Completed During the Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Create the layout, navigation, and movie cards.<br>- Build catalog and detail pages.<br>- Create a shared frontend API client. | 13/07/2026 | 13/07/2026 | React and Vite Documentation |
| Tuesday | - Create FastAPI routers, services, and repositories.<br>- Build catalog, popular-movie, and detail APIs.<br>- Connect the backend to DynamoDB. | 14/07/2026 | 14/07/2026 | FastAPI and Boto3 Documentation |
| Wednesday | - Build registration and login APIs.<br>- Hash passwords and issue JWTs.<br>- Build preferred-genre onboarding. | 15/07/2026 | 15/07/2026 | FastAPI Security Documentation |
| Thursday | - Record click, watch, rating, reaction, and share events.<br>- Inspect UserInteractions records.<br>- Fix simple request-validation errors. | 16/07/2026 | 16/07/2026 | Boto3 and DynamoDB Documentation |
| Friday | - Build frontend and backend Docker images.<br>- Run Docker Compose on EC2.<br>- Configure the Security Group and test the application in a browser. | 17/07/2026 | 17/07/2026 | Docker and Amazon EC2 Documentation |

## Week 6 Achievements

By the end of Week 6, the basic application was operational and could store user data in DynamoDB.

Key achievements included:

- Completed the movie catalog, cards, and detail page.
- Built APIs that read movie data from DynamoDB.
- Completed registration, login, JWT, and onboarding flows.
- Recorded the main user-interaction events.
- Packaged the frontend and backend with Docker.
- Ran the application on EC2 and fixed initial configuration issues.
