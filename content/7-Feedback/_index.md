---
title: "Sharing and Feedback"
date: 2026-07-31
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

{{% notice tip %}}
This section summarizes my experience in the First Cloud AI Journey program, the aspects that provided the most value, the difficulties encountered, and several suggestions that could improve the experience for future participants.
{{% /notice %}}

## Overall Experience

The First Cloud AI Journey program provided a useful opportunity to study AWS through a structured project instead of learning each service separately. The progression from cloud fundamentals to architecture, implementation, testing, documentation, and cleanup helped me understand how multiple services participate in one system.

The movie recommendation project was relevant to my interests because it combined web development, data processing, Machine Learning, and cloud infrastructure. Completing both the application and the workshop report also improved my ability to explain technical work instead of only writing source code.

## Detailed Feedback

| No. | Area | Evaluation | Feedback |
| --- | --- | --- | --- |
| 1 | Learning roadmap | Good | The roadmap encouraged a clear progression from theory to implementation and final reporting. |
| 2 | Learning materials | Good | AWS documentation and FCAJ reference materials provided a strong foundation, although several advanced topics required additional independent research. |
| 3 | Mentor and support channels | Good | The support channels were useful for asking questions and comparing approaches when technical issues appeared. |
| 4 | Practical project | Good | The project covered a realistic combination of frontend, backend, data, ML, security, deployment, and cost awareness. |
| 5 | Community and sharing | Good | Progress sharing and other participants' materials provided additional ideas and motivation. |
| 6 | Schedule and workload | Fair | The scope was broad for eight weeks, especially when implementation, AWS screenshots, bilingual documentation, and testing were completed together. |

## Most Valuable Aspects

- The program connected AWS theory to a concrete end-to-end project.
- The project required understanding service interactions instead of only following isolated console steps.
- Preparing the workshop improved technical writing, screenshot organization, and architecture explanation skills.
- Working with IAM, CloudWatch, Budgets, and cleanup increased awareness of security and cloud cost.
- Testing guest, new-user, and returning-user scenarios made the recommendation system easier to understand than evaluating only the model.

## Difficulties Encountered

- The number of technologies was large: React, FastAPI, Docker, DynamoDB, S3, SageMaker, IAM, and recommendation algorithms had to be studied together.
- IAM permission and environment-configuration errors sometimes took significant time to diagnose.
- SageMaker resources can generate costs, so experiments had to be planned and cleaned up carefully.
- Offline recommendation metrics were easier to collect than real user-experience metrics.
- Keeping English and Vietnamese documentation, screenshots, commands, and implementation details consistent required considerable review time.

## Suggestions for Improvement

1. Provide a milestone checklist for each week, including minimum requirements and optional advanced tasks.
2. Hold short, regular technical review sessions so participants can identify architecture or permission problems earlier.
3. Provide a standard starter repository with environment-variable examples, basic CI checks, and a clear folder structure.
4. Add a troubleshooting guide for common IAM, networking, billing, and SageMaker errors.
5. Clearly identify which AWS resources generate continuous charges and provide a cleanup checklist from the beginning.
6. Include a final demo or peer-review session where participants can present their architecture and receive focused feedback.

## Recommendation to Future Participants

I would recommend the First Cloud AI Journey program to students who want practical exposure to AWS and are willing to learn independently. Participants should prepare basic programming, Git, Linux command-line, and web-development knowledge before starting. They should also track costs from the first day and maintain weekly notes so the final report does not become a separate task at the end.

## Future Expectations

I would like future versions of the program to include more content on Infrastructure as Code, automated testing, observability, MLOps, and production deployment. I would also be interested in continuing to improve this project by automating the infrastructure, completing the model release pipeline, adding load testing, and measuring recommendations with real user feedback.

## Final Feedback

Overall, the program provided a positive and practical learning experience. The greatest value was not any single AWS service, but learning how to connect cloud infrastructure, application development, data, Machine Learning, security, and documentation into one project. The workload was challenging, but it helped identify both my current strengths and the skills I need to continue developing.
