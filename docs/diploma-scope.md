# ML Module Design

## 1. Purpose

The ML module is a planned extension of the existing Fenomen LMS and trial UNT system. Its purpose is to estimate students' expected UNT results and support personalized study recommendations.

The module must use available assessment data and integrate with the existing backend.

## 2. Problem Definition

The project contains two related tasks:

1. **Result prediction:** estimate a student's future UNT score using available historical performance data.
2. **Personalized recommendations:** identify subjects or topics that require additional practice and generate recommendations based on assessment results.

The exact prediction target must be selected after inspecting the existing database and confirming which historical data is available.

## 3. Data Requirements

Potential input features include:

- Student's previous test scores.
- Accuracy by subject.
- Accuracy by topic.
- Number of completed attempts.
- Performance changes across attempts.
- Task difficulty, if recorded consistently.

Before training, the team must inspect data completeness, consistency, and availability.

Student identifiers must not be used as predictive features merely to distinguish individuals. Development experiments should use anonymized or synthetic data where possible.

## 4. Data Preparation

The data preparation pipeline should:

1. Select records suitable for the prediction target.
2. Remove invalid or duplicate records where appropriate.
3. Handle missing values using documented rules.
4. Construct features from assessment history.
5. Split data into training and evaluation sets without leaking future information into training.
6. Record the dataset version and preprocessing configuration.

The split strategy must account for the temporal nature of student attempts when applicable.

## 5. Baseline and Model

A simple baseline must be established before selecting a more complex model.

Candidate approaches may include predicting a historical average or using a regression model. The final choice depends on the target variable, dataset size, feature quality, and experimental results.

The selected model must be reproducible and compared against the baseline using the same evaluation procedure.

## 6. Evaluation Metrics

For numerical score prediction, the primary evaluation metrics are:

- **MAE:** average absolute prediction error.
- **RMSE:** square root of the average squared prediction error.
- **R²:** proportion of target variance explained by the model, where appropriate.

Evaluation results must be calculated on data not used to fit the model. The report must include the baseline results, model results, evaluation procedure, and limitations.

No accuracy or improvement figures should be reported until experiments have been conducted.

## 7. Recommendation Logic

The recommendation component should use verified assessment information to identify areas requiring additional study.

Possible recommendation rules include:

- Recommend additional practice for topics with consistently low accuracy.
- Prioritize topics that contribute to the selected UNT subject.
- Consider changes in performance across attempts.
- Avoid generating confident recommendations when there is insufficient data.

The team must document the final rules and verify them with representative test cases.

## 8. Backend Integration

The module should be integrated into the existing FastAPI backend.

The integration design must specify:

- The input data required for prediction.
- The service or function responsible for inference.
- The API response structure.
- Error handling for insufficient or invalid data.
- Access control for student results.
- How prediction and recommendation results are presented to the frontend.

The implementation should follow the existing project's architecture rather than duplicate existing application logic.

## 9. Testing

Testing should cover:

- Feature preparation and validation.
- Prediction output format and valid score ranges.
- Recommendation generation for different performance profiles.
- Missing and insufficient input data.
- API integration.
- Authorization and access restrictions.
- Reproducibility of evaluation results.

Tests must use isolated test data and must not modify the real application database.

## 10. Limitations and Risks

Potential limitations include insufficient historical data, unrepresentative samples, changes in examination formats, missing topic-level results, and prediction errors.

Predictions are estimates and must not be presented as guaranteed examination outcomes. The system should communicate uncertainty and avoid unsupported conclusions about individual students.

## 11. Implementation Status

This document describes the intended design. Features must be marked as implemented only after their code, tests, and behavior have been verified.

The final version must be updated with the actual prediction target, selected model, available features, measured evaluation results, and integration details.
