# Fenomen LMS and Intelligent Trial UNT System

## Overview

Fenomen LMS and Intelligent Trial UNT System is a web-based learning management and examination preparation platform built with FastAPI, PostgreSQL, and Next.js.

The project serves as the foundation for the diploma project **“Development of an Intelligent Web System for Predicting UNT Results and Generating Personalized Recommendations for Students.”**

The goal of the diploma project is to extend the existing learning platform with an intelligent module that analyzes student performance, predicts expected Unified National Testing (UNT) results, and provides personalized recommendations for further study.

The system is intended for use in an educational environment, initially targeting approximately 500 students at one school.

## Project Objectives

- Provide a platform for learning materials and trial UNT preparation.
- Support practice tests and automated assessment.
- Analyze student performance across subjects and topics.
- Develop a model for predicting expected UNT results.
- Generate personalized recommendations based on student performance.
- Integrate the intelligent module into the existing web application.
- Evaluate the prediction model using appropriate quantitative metrics.

## Existing Platform

The existing LMS and trial UNT system provide the foundation for the diploma development.

The project includes functionality related to student, teacher, and administrator roles, courses, test variants, automated scoring, performance analytics, ranking, access control, audit logging, and test completion.

The exact implementation status of individual features must be verified against the current source code.

## Intelligent Prediction and Recommendation Module

The main research component of the diploma project is an intelligent module for predicting student results and generating personalized study recommendations.

### Prediction

The module is intended to use available student performance data to estimate expected UNT results.

Potential input features include:

- Accuracy by subject and topic.
- Task difficulty.
- Results of previous attempts.
- Changes in performance over repeated attempts.

The final prediction target and input features will be defined after analyzing the available data.

### Personalized Recommendations

The recommendation component is intended to identify subjects and topics that require additional study and provide recommendations based on the student's performance.

The recommendation logic will be designed around available assessment data, topic-level accuracy, and performance trends.

### Model Evaluation

The prediction model will be compared with a baseline method using appropriate evaluation metrics:

- **MAE (Mean Absolute Error):** average absolute difference between predicted and actual values.
- **RMSE (Root Mean Squared Error):** error metric that penalizes larger prediction errors more strongly.
- **R² (Coefficient of Determination):** measure of explained variance, where appropriate for the selected prediction task.

The final report will document the selected model, dataset, experimental setup, evaluation results, and limitations. No prediction accuracy or performance improvement is claimed before experimental validation.

## Technology Stack

| Component | Technology |
|---|---|
| Backend | Python, FastAPI |
| Database | PostgreSQL |
| Caching | Redis |
| Frontend | Next.js, React, TypeScript |
| Containerization | Docker, Docker Compose |
| Backend testing | Python `unittest` |
| Frontend verification | pnpm build |
| Dependency auditing | pnpm audit |

The technology list should be kept consistent with the dependencies and configuration files in the repository.

## System Architecture

The application follows a client-server architecture.

1. **Frontend:** provides the user interface for learning, trial testing, and displaying results.
2. **Backend API:** handles application logic, assessment processing, and communication between the frontend and database.
3. **PostgreSQL:** stores persistent application data.
4. **Redis:** provides caching where configured.
5. **Intelligent module:** the planned diploma extension for result prediction and personalized recommendations.
6. **Docker Compose:** manages application services in development and production environments.

The intelligent module will be integrated with the existing application rather than developed as an unrelated standalone product.

## Team Responsibilities

The preliminary division of responsibilities is:

- **Ихтияр Мағжан Талғатұлы:** Backend development, AI/ML, and DevOps.
- **Сәрсенбек Еркебұлан Бақтығалиұлы:** Full-stack development, testing, and security.

Individual contributions will be documented through YouTrack tasks, commits, pull requests, reviews, and technical deliverables. The final submission will distinguish previously existing functionality from work completed specifically for the diploma project.

## Development Setup

### Requirements

- Docker and Docker Compose.
- Git.
- Access to the repository.
- A configured local environment file.

### Installation

Clone the repository and open its directory:

```sh
git clone https://github.com/MagaBitex64/ent-intelligent-system.git
cd ent-intelligent-system
```

Copy the example environment file:

```sh
cp .env.example .env
```

Configure the local credentials and required environment variables in `.env`. Do not commit the resulting file.

Build and start the development services:

```sh
docker compose up --build -d
```

Default local addresses:

- Frontend: http://localhost:3001
- Backend API: http://localhost:8000
- API documentation: http://localhost:8000/docs

These addresses assume the default port mappings in the development Compose configuration.

**Data warning:** existing Docker volumes may contain persistent data. Do not run `docker compose down -v` unless the data is intentionally disposable.

## Production Deployment

Production deployment instructions are maintained in [`docs/production.md`](docs/production.md).

Use the standalone `docker-compose.production.yml` configuration and create `.env.production` privately on the server.

The production setup is designed to expose ports 80 and 443, provide HTTPS, isolate database and API ports, and avoid passing backend secrets to the frontend.

Production images and Python dependencies are pinned. Version changes should be reviewed and validated through security audits, builds, and tests.

Never commit production environment files, credentials, API tokens, private keys, or real student data.

## Testing and Verification

Run backend tests from the `backend/` directory with the required dependencies and a disposable PostgreSQL database.

### ENT Rules and Document Tests

```sh
python -m unittest tests.test_ent_rules tests.test_quiz_docx -v
```

### Integration and Seed Tests

```sh
python -m unittest tests.test_ent_integration tests.test_ent_seed -v
```

### Release Tests

```sh
RUN_RELEASE_TESTS=1 python -m unittest tests.test_release -v
```

Release tests require `DATABASE_URL` to point to a database hostname named `auditdb`. They create an isolated schema for each case and must not run against the real application database. Use a dedicated disposable PostgreSQL container and a read-only source mount.

For the frontend, `pnpm build` includes the TypeScript check. Run `pnpm audit --prod` to audit the production dependencies recorded in the pnpm lockfile used by Docker.

Additional technical documentation:

- [Production runbook](docs/production.md)
- [Release fixes and validation boundaries](docs/release-fixes.md)
- [ENT rules and browser telemetry](docs/ent-rules.md)

## Research Methodology

The diploma research will cover the following stages:

1. Analyze the existing system and available assessment data.
2. Define the prediction target and prepare the dataset.
3. Establish a baseline prediction method.
4. Select and implement an appropriate machine learning model.
5. Evaluate the model using suitable metrics.
6. Design and implement personalized recommendation logic.
7. Integrate the intelligent module into the web application.
8. Test the integrated system and document the results.

The experimental methodology must account for data quality, missing values, and the risk of data leakage between training and evaluation sets.

## Security and Data Privacy

The application must protect student information and restrict access according to user roles.

Development and testing should use anonymized or synthetic student data wherever possible. Access to production data must be limited to authorized personnel.

Prediction results are estimates, not guarantees of actual examination performance. Model limitations and the intended use of predictions must be documented.

## Current Status and Future Work

The existing LMS and trial UNT application serve as the foundation for the diploma project.

The remaining diploma work includes verifying the existing functionality, defining the prediction target and dataset, implementing and evaluating the intelligent module, integrating predictions and recommendations into the frontend, and documenting the experimental results.

The project status will be updated as these deliverables are implemented and verified.

## License

Specify the project's license here if one has been selected.
