# Diploma Project Scope

## 1. Project Title

Development of an Intelligent Web System for Predicting UNT Results and Generating Personalized Recommendations for Students.

## 2. Project Overview

The diploma project focuses on extending the existing Fenomen LMS and trial UNT preparation platform with an intelligent module for predicting students' expected UNT results and generating personalized study recommendations.

The existing platform provides the foundation for the diploma development. The project will build upon its existing functionality instead of creating a separate, unrelated application.

The intelligent module will analyze students' assessment history, identify areas that require improvement, estimate expected performance, and provide recommendations for further preparation.

## 3. Problem Statement

Students preparing for the Unified National Testing (UNT) complete practice assessments to evaluate their knowledge. However, individual test results do not always provide a clear picture of future performance or explain which subjects and topics should receive additional attention.

Without systematic analysis of previous attempts, students may find it difficult to identify persistent weaknesses and prioritize their preparation effectively.

The project addresses this problem by developing a web-based system that uses available assessment data to predict expected results and generate personalized recommendations.

## 4. Aim

To develop and evaluate an intelligent web system that predicts students' expected UNT results and generates personalized recommendations based on their assessment performance.

## 5. Project Objectives

1. Analyze the existing LMS and trial UNT platform and identify the data required for prediction and recommendations.
2. Examine available student assessment results, including scores, subject performance, topic-level accuracy, and previous attempts where these data are available.
3. Define the prediction target and prepare an appropriate dataset.
4. Implement a baseline prediction method and select a suitable machine-learning approach based on the available data.
5. Evaluate prediction performance using appropriate metrics.
6. Develop a recommendation mechanism that identifies subjects and topics requiring additional practice.
7. Integrate the prediction and recommendation functionality into the existing backend and frontend.
8. Test the implemented functionality and document the experimental results, limitations, and conclusions.

## 6. Project Scope

### 6.1. Included Work

The diploma project includes:

- Analysis of the existing application and its assessment workflow.
- Identification and preparation of relevant student performance data.
- Development of a student result prediction module.
- Comparison of the selected model with a baseline method.
- Evaluation of predictive performance using appropriate metrics.
- Development of personalized recommendations based on assessment results.
- Backend API and frontend integration.
- Testing, technical documentation, and evaluation of the completed solution.

### 6.2. Existing Platform

The existing platform serves as the starting point for the diploma project. Its previously implemented functionality will be treated as existing work.

The exact state of the existing features will be verified against the source code. Only functionality newly implemented or substantially modified for the diploma will be reported as a diploma contribution.

### 6.3. Limitations

The prediction quality depends on the availability, quantity, and quality of assessment data. The selected prediction target and final model will be determined after examining the actual database structure and available records.

The system will provide estimates rather than guarantees of actual UNT results. Recommendations will support students' preparation but will not replace teachers' professional judgement.

The project will not claim prediction accuracy or improvement until these claims are supported by experimental results.

## 7. Proposed Methodology

The work will follow these stages:

1. Analyze the existing system and relevant literature.
2. Inspect the assessment data and define the prediction target.
3. Prepare the dataset and establish a baseline.
4. Select and implement an appropriate prediction model.
5. Evaluate the model using a documented experimental procedure.
6. Develop personalized recommendation logic.
7. Integrate the intelligent module into the web application.
8. Test the integrated solution and document the results.

The evaluation will account for data quality, missing values, and possible data leakage between training and evaluation datasets.

## 8. Technology Stack

The project builds on the existing application's technology stack:

- **Backend:** Python and FastAPI.
- **Database:** PostgreSQL.
- **Caching:** Redis, where configured.
- **Frontend:** Next.js, React, and TypeScript.
- **Deployment:** Docker and Docker Compose.
- **Testing:** Automated backend and frontend checks.
- **Machine learning:** To be selected according to the available dataset and defined prediction task.

The final implementation and report will reflect the technologies actually used in the completed solution.

## 9. Expected Deliverables

The expected deliverables are:

1. Analysis of the existing platform and relevant assessment data.
2. A documented prediction target and dataset preparation procedure.
3. A baseline prediction method and an evaluated candidate model.
4. Experimental results and an explanation of the model's limitations.
5. A personalized recommendation mechanism.
6. Integration of prediction and recommendation functionality into the web application.
7. Automated tests and technical documentation.
8. A final diploma report describing the problem, methodology, implementation, evaluation, and conclusions.

These are planned deliverables; each will be marked complete only after implementation or verification.

## 10. Team Responsibilities

**Ихтияр Мағжан Талғатұлы**
- Backend development.
- Machine-learning module and prediction experiments.
- DevOps and deployment-related work.

**Сәрсенбек Еркебұлан Бақтығалиұлы**
- Full-stack development.
- Frontend integration.
- Testing and security.

Individual contributions will be documented through task assignments, commits, pull requests, code reviews, and completed technical deliverables.

## 11. Current Status and Next Steps

The existing LMS and trial UNT platform form the technical foundation of the diploma project. The repository documentation describes the planned intelligent functionality and its intended evaluation.

The next steps are to verify the actual assessment schema, determine whether sufficient historical data is available, define the prediction target, implement the baseline, and begin testing the prediction and recommendation components.

The project will progress from design to implementation and experimental validation. The final report will distinguish existing platform functionality from new diploma work and will include only verified implementation details and measured results.
