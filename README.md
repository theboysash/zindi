Yep — the README should explicitly mention LightGBM as one of the models considered/used.

A clean place to add it is under Machine Learning Approach and Future Improvements. If LightGBM was actually trained in the notebook, I'd phrase it as “Models evaluated” rather than merely a future improvement.

For example:

README — LightGBM Model Addition
Mapping Service Delivery Needs in Gauteng
Models Evaluated

The project evaluates multiple machine-learning approaches for predicting household service-delivery gaps.

The models include:

Random Forest with MultiOutputClassifier — used as the main baseline model.
LightGBM (Light Gradient Boosting Machine) — evaluated as an additional gradient-boosting approach for the classification task.

LightGBM was included because gradient-boosting methods can capture complex, non-linear relationships between household characteristics and service-delivery outcomes while remaining computationally efficient.

The modelling workflow therefore allows the performance of different algorithms to be compared using the same validation framework, with Macro-F1 and Hamming Loss used as the primary evaluation metrics.

Machine Learning Approach

The project treats service-delivery prediction as a multi-label classification problem, since a household can experience multiple service gaps simultaneously.

The main modelling approaches considered were:

Household Data
      ↓
Feature Selection
      ↓
Categorical Feature Encoding
      ↓
 ┌─────────────────────────────┐
 │       Models Evaluated      │
 │                             │
 │  Random Forest              │
 │  LightGBM                   │
 └──────────────┬──────────────┘
                ↓
        Model Evaluation
                ↓
        Threshold Tuning
                ↓
        Final Predictions

Random Forest

The baseline implementation uses a RandomForestClassifier within a MultiOutputClassifier framework. This provides a separate classifier for each of the five service-gap targets.

LightGBM

LightGBM was also used as one of the project's machine-learning models. It is a gradient-boosting framework designed for efficient training and strong predictive performance, particularly on structured/tabular datasets.

Including LightGBM provides a useful comparison against the Random Forest baseline and allows us to investigate whether gradient boosting can better capture relationships within the household-level data.

Future Improvements

Potential improvements include:

Further hyperparameter tuning for Random Forest and LightGBM
Cross-validation for more reliable model comparison
Feature engineering and improved treatment of ordinal variables
Testing additional gradient-boosting approaches
Using ClassifierChain to model relationships between service-gap labels
Optimising prediction thresholds using cross-validation
Comparing ensemble approaches that combine Random Forest and LightGBM predictions
Conclusion

This project demonstrates how machine learning can be applied to multi-label service-delivery prediction using household-level data from Gauteng.

Multiple modelling approaches, including Random Forest and LightGBM, were considered to identify effective ways of predicting gaps in water, sanitation, refuse removal, electricity, and education access.

The comparison of different algorithms provides a stronger basis for selecting a final predictive model, while threshold tuning helps account for the imbalance between the different service-gap labels.
