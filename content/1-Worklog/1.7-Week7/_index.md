---
title: "Week 7 Worklog"
date: 2026-07-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

{{% notice tip %}}
Week 7 implemented the recommendation methods studied in Week 4. The model was trained and evaluated before running through a SageMaker Processing Job and connecting to FastAPI through a real-time Endpoint, cache, and fallback flow.
{{% /notice %}}

## Week 7 Objectives

- Build recommendation methods for guests and new users.
- Train implicit ALS for returning users.
- Combine and evaluate recommendation results.
- Run model processing with SageMaker.
- Connect the recommendation Endpoint to the backend.

## Tasks Completed During the Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Build weighted popularity ranking for guests.<br>- Create TF-IDF features and cosine-similarity recommendations.<br>- Check several genre examples. | 20/07/2026 | 20/07/2026 | Pandas and Scikit-learn Documentation |
| Tuesday | - Convert events to implicit scores.<br>- Train the ALS model.<br>- Combine candidates with weighted Reciprocal Rank Fusion. | 21/07/2026 | 21/07/2026 | Implicit Library Documentation |
| Wednesday | - Split data by time.<br>- Calculate Recall@K, NDCG@K, and coverage.<br>- Save artifacts, mappings, and reports to S3. | 22/07/2026 | 22/07/2026 | Scikit-learn and Amazon S3 Documentation |
| Thursday | - Package the training command.<br>- Submit a SageMaker Processing Job.<br>- Monitor the job and inspect S3 output. | 23/07/2026 | 23/07/2026 | Amazon SageMaker Documentation |
| Friday | - Validate the SageMaker Endpoint response.<br>- Connect FastAPI to the Endpoint.<br>- Add RecommendationCache and popularity fallback. | 24/07/2026 | 24/07/2026 | SageMaker Runtime and Boto3 Documentation |

## Week 7 Achievements

By the end of Week 7, the recommendation pipeline had been implemented and connected to the application.

Key achievements included:

- Generated popular movies for guests.
- Generated genre-based recommendations for new users.
- Trained implicit ALS for users with interaction history.
- Combined candidates and filtered invalid items.
- Stored model artifacts and evaluation reports in S3.
- Invoked the SageMaker Endpoint from FastAPI with caching and fallback.
