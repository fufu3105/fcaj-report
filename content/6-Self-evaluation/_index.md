---
title: "Self-Assessment"
date: 2026-07-31
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

{{% notice tip %}}
This section reviews the knowledge, skills, working attitude, and limitations identified during the internship from June 1, 2026 to July 31, 2026. The assessment is based on the completed movie recommendation project, workshop documentation, and recorded test results.
{{% /notice %}}

## Internship Overview

During the First Cloud AI Journey program, I spent the first four weeks learning cloud computing, AWS services, web architecture, security, and recommendation-system theory. During the final four weeks, I applied that knowledge to build and document a movie recommendation system using React/Vite, FastAPI, Amazon S3, DynamoDB, EC2, SageMaker, IAM, and CloudWatch.

The project helped me connect theoretical knowledge with a complete technical flow: preparing data, storing application records, training a recommendation model, serving recommendations through an API, testing user scenarios, and reviewing cloud security and cost.

## Results Achieved

### Cloud and AWS Knowledge

- Understood the roles of IAM, VPC, EC2, S3, DynamoDB, SageMaker, CloudWatch, and AWS Budgets.
- Learned how to separate application data in DynamoDB from datasets and model artifacts in S3.
- Understood least privilege, service roles, instance profiles, logging, and basic cost control.
- Learned the difference between batch processing with SageMaker Processing Jobs and real-time inference with SageMaker Endpoints.

### Application Development

- Built the main React/Vite interfaces for browsing movies, authentication, and onboarding.
- Organized the FastAPI backend using routers, services, repositories, and a recommendation provider.
- Implemented the main flows for accounts, movie data, interactions, recommendation caching, and fallback.
- Packaged the frontend and backend with Docker and tested the application on EC2.

### Data and Machine Learning

- Profiled, cleaned, and mapped data from the movie dataset.
- Implemented popularity ranking, content-based filtering, implicit ALS, and hybrid ranking.
- Learned to evaluate recommendations with Recall@K, NDCG@K, and coverage.
- Stored model artifacts, mappings, and evaluation reports in S3.

### Documentation and Testing

- Documented the architecture, data flow, training flow, inference flow, security, and cleanup process.
- Prepared screenshots and diagrams to support the implementation steps.
- Tested guest, new-user, returning-user, interaction, cache, and fallback scenarios.
- Maintained consistent English and Vietnamese report content.

## Self-Assessment Table

| No. | Criterion | Evidence from the Internship | Self-Rating |
| --- | --- | --- | --- |
| 1 | Professional knowledge | Applied AWS, web-development, data-processing, and recommendation-system knowledge to one integrated project. | Good |
| 2 | Ability to learn | Learned several unfamiliar AWS and machine-learning services within a limited period. | Good |
| 3 | Practical implementation | Completed the main application and recommendation flows, but production hardening remains incomplete. | Fair |
| 4 | Problem solving | Investigated data-format, permission, environment, API, and model-integration issues. More practice is needed for complex incidents. | Fair |
| 5 | Responsibility and progress | Followed the eight-week plan and completed the required report sections and project milestones. | Good |
| 6 | Documentation | Recorded architecture, procedures, expected results, screenshots, limitations, and cleanup steps. | Good |
| 7 | Communication and reporting | Maintained weekly progress records and summarized technical decisions. Updates could be shorter and more regular. | Fair |
| 8 | Security and cost awareness | Considered least privilege, credential handling, logging, budgets, fallback, and resource cleanup. | Good |
| 9 | Initiative | Independently researched documentation, compared solutions, and added simple validation and fallback mechanisms. | Good |
| 10 | Overall performance | Completed the project at workshop level and achieved the main learning objectives of the internship. | Good |

## Strengths

- Able to learn independently and organize knowledge into a clear implementation sequence.
- Able to connect frontend, backend, data, machine learning, and AWS services in one architecture.
- Careful when documenting procedures, evidence, limitations, security, and cleanup steps.
- Willing to test multiple user scenarios and review failures instead of only demonstrating the successful path.
- Maintained steady progress from theory to implementation throughout the internship.

## Areas for Improvement

- Improve infrastructure automation by learning AWS CDK, CloudFormation, or Terraform.
- Add more unit, integration, performance, and failure-recovery tests.
- Strengthen MLOps knowledge, including model packaging, registry, automated promotion, rollback, and drift monitoring.
- Improve debugging speed for IAM permissions, networking, and distributed cloud-service errors.
- Report blockers and technical decisions more concisely and consistently.
- Gain more experience measuring real user behavior instead of relying mainly on offline model metrics.

## Development Plan

1. Rebuild the infrastructure with an Infrastructure as Code tool and separate development and production configurations.
2. Add automated tests and CI checks for the data pipeline, backend APIs, and recommendation scenarios.
3. Complete the model deployment pipeline with versioning, approval, monitoring, and rollback.
4. Practice CloudWatch dashboards, alarms, load testing, and cost analysis using measurable targets.
5. Continue improving technical communication through short progress updates, diagrams, and structured reports.

## Overall Assessment

I consider the internship objectives to have been achieved at a **Good** level. I completed the planned learning path, built a working workshop-level project, and improved my AWS, software-development, data, machine-learning, and documentation skills. However, the system still requires additional automation, production testing, monitoring, and operational experience before it can be considered production-ready.
