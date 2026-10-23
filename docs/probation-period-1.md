# Probationary Period 1 Consolidated Report

**Project:** Development of an Intelligent Web System for Predicting UNT Results and Generating Personalized Recommendations for Students  
**Group:** SE-2428  
**Team:** Сәрсенбек Еркебұлан Бақтығалиұлы; Ихтияр Мағжан Талғатұлы  
**Supervisor:** Солтан Гульжан Жексенбаевна  
**Repository:** https://github.com/MagaBitex64/ent-intelligent-system  
**Tagged version:** https://github.com/MagaBitex64/ent-intelligent-system/tree/prob-period-1

## Table of Contents

1. Project Title
2. Project Overview
3. Problem Statement
4. Aim
5. Project Objectives
6. Project Scope
7. Proposed Methodology
8. Technology Stack and Architecture
9. Expected Deliverables
10. Team Responsibilities and Contribution Evidence
11. Current Status, Limitations and Next Steps

## 1. Project Title

Development of an Intelligent Web System for Predicting UNT Results and Generating Personalized Recommendations for Students.

## 2. Project Overview

The diploma project extends the existing Fenomen learning-management and trial-UNT platform with an intelligent module that will estimate expected UNT results and generate personalized study recommendations. The existing web application already supports student, teacher and administrator roles; course content; assignments and quizzes; complete and single-subject trial UNT variants; automatic scoring; deadlines and repeated attempts; rankings; LaTeX and image content; browser proctoring telemetry; password recovery; audit logs and consultation requests.

The platform is being prepared for an initial pilot in one school with an expected user base of approximately 500 people. Commercial access for students from other schools is planned after the pilot.

Reproducible prototype source: https://github.com/MagaBitex64/ent-intelligent-system/tree/prob-period-1  
Local frontend after setup: http://localhost:3001  
Backend API documentation after setup: http://localhost:8000/docs

No public production URL is claimed in this tagged version; the prototype is reproducible from the tagged repository using Docker Compose.

## 3. Problem Statement

Students preparing for the Unified National Testing complete many practice assessments, but isolated scores do not clearly indicate expected future performance or which subjects and topics deserve priority. Without systematic analysis of attempt history, persistent weaknesses and changes in performance are difficult to identify.

The project addresses this problem by combining a working UNT preparation platform with a planned intelligent module that analyzes assessment history, predicts an expected score and generates explainable recommendations. Predictions will be presented as estimates rather than guarantees and will support, not replace, teacher judgement.

## 4. Aim

To develop and evaluate an intelligent web system that predicts students' expected UNT results and generates personalized recommendations from their verified assessment performance.

## 5. Project Objectives

1. Audit the existing LMS and trial-UNT platform and identify relevant assessment data.
2. Examine scores, subject performance, topic-level accuracy and previous attempts.
3. Define a reproducible prediction target and an anonymized dataset.
4. Establish a simple baseline and select a suitable machine-learning approach.
5. Evaluate prediction quality using MAE, RMSE and R-squared where appropriate.
6. Develop explainable recommendation logic for weak subjects and topics.
7. Integrate prediction and recommendation functions into the FastAPI backend and Next.js frontend.
8. Verify authorization, data privacy, reproducibility and failure handling through tests.
9. Pilot the system in the first school and collect structured feedback.

## 6. Project Scope

Included work covers analysis of the existing application, dataset preparation, baseline and candidate prediction models, evaluation, recommendation logic, backend and frontend integration, automated tests, documentation and production-readiness checks.

The already implemented LMS and trial-UNT functions are treated as the technical foundation. Diploma novelty focuses on result prediction, explainable personalized recommendations and their integration into the existing platform. Only verified new or substantially modified work will be reported as a diploma contribution.

Out of scope for the current stage are native Android and iOS applications, biometric identity verification and any claim of guaranteed examination performance.

## 7. Proposed Methodology

The project follows these stages:

1. Audit the application architecture, assessment schema and data quality.
2. Define the prediction target and prevent future-information leakage.
3. Prepare an anonymized dataset and version the preprocessing rules.
4. Establish a baseline such as a historical average or simple regression.
5. Train suitable candidate models according to dataset size and feature quality.
6. Evaluate the baseline and candidate models on unseen data using MAE, RMSE and R-squared.
7. Design recommendation rules based on subject/topic accuracy and trends.
8. Integrate inference and recommendations into secured APIs and dashboards.
9. Test representative, insufficient-data and authorization scenarios.
10. Run a controlled school pilot and document results and limitations.

Detailed ML design: https://github.com/MagaBitex64/ent-intelligent-system/blob/prob-period-1/docs/ml-design.md

## 8. Technology Stack and Architecture

The backend uses Python and FastAPI. PostgreSQL stores persistent application data, Redis provides caching where configured, and the frontend uses Next.js, React and TypeScript. Docker and Docker Compose manage development and production services. Backend verification uses Python unittest, while the frontend is checked through the pnpm build and dependency audit workflows.

The system follows a client-server architecture. Student, teacher and administrator browsers use the Next.js frontend, which communicates with the FastAPI API. The API accesses PostgreSQL, Redis, uploaded-file storage and the Brevo transactional-email service. The planned intelligent module will consume verified assessment features through the backend and return predictions and recommendations without duplicating application logic.

Editable architecture source: https://github.com/MagaBitex64/ent-intelligent-system/blob/prob-period-1/docs/architecture.mmd  
Production runbook: https://github.com/MagaBitex64/ent-intelligent-system/blob/prob-period-1/docs/production.md  
UNT rules: https://github.com/MagaBitex64/ent-intelligent-system/blob/prob-period-1/docs/ent-rules.md

## 9. Expected Deliverables

1. Audited assessment workflow and database schema.
2. Documented prediction target and anonymized dataset-preparation procedure.
3. Baseline method and evaluated candidate model.
4. Experimental results with limitations and reproducibility notes.
5. Explainable personalized recommendation mechanism.
6. Secured backend API and frontend dashboard integration.
7. Automated tests for data preparation, prediction, recommendations and access control.
8. Deployment, monitoring and backup documentation.
9. Final diploma report and demonstration materials.

Deliverables are marked complete only after implementation and verification. Planned AI outcomes are not represented as completed in Probationary Period 1.

## 10. Team Responsibilities and Contribution Evidence

### Сәрсенбек Еркебұлан Бақтығалиұлы

Area: full-stack development, system analysis, UNT business logic, security, testing and documentation.

Completed work includes official UNT structure and scoring, full and single-subject variants, proctoring telemetry, LaTeX rendering, search and Remember Me, password recovery, audit logging, teacher file-access protection, release audit and responsive interface improvements.

YouTrack: EIS-3, EIS-4, EIS-7, EIS-8, EIS-9, EIS-10, EIS-11, EIS-12.  
Representative commits: c781065, cde3087, b0d39e4, 3977a00, 3abeeba, 35088c5, ca824ec, ce13b1a and ada4cbf.

### Ихтияр Мағжан Талғатұлы

Area: backend and database development, DevOps, deployment, AI-module preparation and technical documentation.

Completed work includes the LMS/UNT foundation, trial-UNT workflows and seed data, upload handling, related-record cleanup, proctoring controls, landing integrations, architecture/database audit and ML design for prediction and personalized recommendations.

YouTrack: EIS-1, EIS-2, EIS-5, EIS-6.  
Representative commits: f0f4b37, 28977c9, 63e3a0a, da09ef2, 5890b7d, 0d54385, 6d7b2f1, f0c73c8, c19b83d and 7d20b4b.

YouTrack project: https://ent-system.youtrack.cloud/issues  
Task-evidence document source: https://github.com/MagaBitex64/ent-intelligent-system/blob/prob-period-1/docs/probation-period-1.md

## 11. Current Status, Limitations and Next Steps

The tagged version is a functional full-stack LMS and trial-UNT platform prepared for pilot deployment. Core learning, assessment, administration, ranking, security and production-support features are present. YouTrack contains twelve project issues: completed audit and design tasks, work under review, current AI preparation and probation-release tasks.

Known limitations are that the AI predictor and recommender are designed but not yet implemented; anonymized historical data is still required; browser proctoring cannot control actions outside the browser; question-bank content needs subject-teacher review; and DNS, TLS, transactional email, backups and monitoring require verification on the final server. YouTrack deadlines were not configured at this stage.

The next stage will define the anonymized dataset and features, collect pilot data with privacy controls, implement and compare baseline and candidate models, evaluate prediction quality, implement the recommendation engine, integrate results into dashboards, conduct the first-school pilot and finalize production monitoring, security checks and diploma documentation.

