---
title: "Week 5 Worklog"
date: 2026-07-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

{{% notice tip %}}
Week 5 began the practical phase by setting up the project environment and preparing the movie dataset. The S3 layout and DynamoDB tables were then created and populated with the application's initial data.
{{% /notice %}}

## Week 5 Objectives

- Prepare the frontend, backend, and machine-learning environments.
- Profile, clean, and normalize the movie dataset.
- Organize datasets and model artifacts in Amazon S3.
- Create five DynamoDB tables based on application access patterns.
- Load and validate the initial movie and popularity data.

## Tasks Completed During the Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Initialize the repository and ML submodule.<br>- Install Python, Node.js, Docker, and AWS CLI.<br>- Prepare environment variables from the project template. | 06/07/2026 | 06/07/2026 | Project README and Notes |
| Tuesday | - Profile movie, rating, link, credit, and keyword files.<br>- Check missing and duplicate values.<br>- Map MovieLens IDs to TMDB IDs. | 07/07/2026 | 07/07/2026 | Kaggle Dataset, Pandas Documentation |
| Wednesday | - Create the project S3 bucket.<br>- Prepare raw, processed, training, inference, model, and evaluation prefixes.<br>- Enable Block Public Access and encryption. | 08/07/2026 | 08/07/2026 | Amazon S3 Documentation |
| Thursday | - Create Movies, PopularMovies, Users, UserInteractions, and RecommendationCache.<br>- Verify their keys and table status. | 09/07/2026 | 09/07/2026 | Amazon DynamoDB Documentation |
| Friday | - Load movie metadata and popularity data.<br>- Inspect sample records through the console and CLI.<br>- Correct missing required fields. | 10/07/2026 | 10/07/2026 | AWS CLI and Project Data Scripts |

## Week 5 Achievements

By the end of Week 5, the data layer was ready to support application development and model training.

Key achievements included:

- Prepared a working local development environment.
- Cleaned the dataset and standardized movie identifiers.
- Created the required S3 layout for data, models, and reports.
- Created the five DynamoDB tables.
- Loaded Movies and PopularMovies data.
- Validated sample records and corrected simple formatting issues.
