# Fenomen LMS and Trial ENT

FastAPI/PostgreSQL backend and Next.js frontend for a learning management system and trial UNT preparation. The repository also serves as the foundation for the diploma project:

**Development of an Intelligent Web System for Predicting UNT Results and Generating Personalized Recommendations for Students**

## Project Overview

The system is intended to support students preparing for the Unified National Testing (UNT) through online learning, practice tests, automated scoring, and performance analytics.

The diploma project extends the existing LMS and trial UNT system with a planned intelligent module for predicting student results and generating personalized recommendations.

The prediction and recommendation features must be documented as implemented only after their code and behavior have been verified.

## Existing Functionality

The current system includes or is designed around the following functionality. Verify each item against the current code before treating this list as a confirmed implementation inventory.

- Student, teacher, and administrator roles
- Courses and learning materials
- Trial UNT test variants and attempts
- Automated test scoring
- Student performance analytics and ranking
- Access control and audit logging
- Controls for test completion

## Planned Intelligent Module

The planned diploma extension will analyze student performance to estimate expected UNT results and provide personalized recommendations.

Potential input features include:

- Accuracy by subject and topic
- Task difficulty
- Results from repeated attempts
- Changes in performance over time

The module will be evaluated against an appropriate baseline. Planned evaluation metrics include Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and the coefficient of determination (R²), where suitable for the selected prediction target and dataset.

The final implementation must document the selected prediction target, input features, dataset preparation, baseline, model, evaluation results, and limitations.

## Technology Stack

- **Backend:** FastAPI, Python
- **Database:** PostgreSQL
- **Caching:** Redis
- **Frontend:** Next.js
- **Deployment:** Docker Compose
- **Testing:** Python `unittest`, frontend build and audit checks

Confirm the stack against the actual repository before submission.

## Development Setup

Copy `.env.example` to `.env`, configure local credentials, then run:

```sh
docker compose up --build -d
