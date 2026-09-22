# AI Decision-Making Under Uncertainty: Smart Irrigation Recommendation System

## Project Overview

This project demonstrates how an Artificial Intelligence system can make practical decisions when available information is incomplete, uncertain, or constantly changing.

The project uses a real-world agricultural scenario: a smart irrigation system that receives information such as soil moisture, temperature, humidity, rainfall probability, wind speed, and crop growth stage.

Based on the available information, the AI estimates the probability that irrigation is required and recommends one of three actions:

- 💧 IRRIGATE
- 💦 IRRIGATE LIGHTLY
- ⏳ WAIT

The system is designed to demonstrate how AI can make informed decisions without requiring perfect information.

---

## Project Question

«How can an Artificial Intelligence system make optimal decisions when the available information is incomplete, uncertain, or constantly changing?»

---

## Objectives

The main objectives of this project are to:

1. Demonstrate AI decision-making under uncertainty.
2. Handle missing or incomplete sensor information.
3. Use machine learning to predict irrigation requirements.
4. Generate probability estimates rather than simple yes/no predictions.
5. Apply decision theory to select an appropriate action.
6. Demonstrate how AI decisions change when new information becomes available.
7. Show how machine learning can support real-world decision-making.

---

## Real-World Scenario

A farmer wants to determine whether a field should be irrigated.

The AI receives information from farm sensors and weather services:

Input| Description
Soil Moisture| Current amount of water in the soil
Temperature| Current environmental temperature
Rain Probability| Probability of rainfall
Humidity| Current atmospheric humidity
Wind Speed| Current wind conditions
Crop Stage| Vegetative, flowering, or fruiting

However, real-world data is rarely perfect.

A sensor may fail, a weather forecast may change, or some measurements may be unavailable.

The AI therefore needs to make the best possible decision using the information currently available.

---

## AI Approach

The project combines Machine Learning, Probability, and Decision Theory.

Decision Process

Farm & Weather Data
        ↓
Incomplete / Uncertain Information
        ↓
Data Preprocessing
        ↓
Missing-Value Handling
        ↓
Machine Learning Model
        ↓
Probability of Irrigation Need
        ↓
Decision Engine
        ↓
Recommended Action
        ↓
New Information
        ↓
Update Decision

---

## Machine Learning Model

The project uses a Random Forest Classifier to predict whether irrigation is required.

The target variable is:

1 = Irrigation Needed
0 = Irrigation Not Needed

The model learns relationships between environmental conditions and irrigation requirements.

Instead of relying only on a binary prediction, the system uses the model's probability estimate.

For example:

Probability = 0.94

means the model estimates a 94% probability that irrigation is required.

---

## Handling Incomplete Information

To simulate real-world conditions, missing values are intentionally introduced into the dataset.

For example:

Soil Moisture:      Missing
Temperature:        34°C
Rain Probability:   20%
Humidity:           45%
Crop Stage:         Flowering

The system uses data imputation to estimate missing numerical values and allow the AI model to continue operating.

This demonstrates an important capability of real-world AI systems: making decisions despite incomplete data.

---

## Decision-Making Under Uncertainty

Prediction alone does not determine the final action.

The system considers the potential consequences of different actions.

Possible actions are:

Action| Description
IRRIGATE| Apply normal irrigation
IRRIGATE LIGHTLY| Apply limited irrigation
WAIT| Do not irrigate yet

The decision engine calculates the expected cost of each action based on the estimated probability.

The system then selects the action with the lowest expected cost.

This connects machine learning with decision theory.

---

## Changing Information

The project also demonstrates dynamic decision-making.

Initially, the system may receive:

Soil Moisture:       20%
Temperature:         36°C
Rain Probability:   15%

The AI may recommend:

IRRIGATE

Later, the weather service provides new information:

Rain Probability: 85%

The AI recalculates its probability and may change the recommendation:

WAIT

This demonstrates that an intelligent AI system should update its decisions when new evidence becomes available.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Random Forest
- Data Imputation
- Probability Estimation
- Decision Theory

---

## Project Structure

AI-Decision-Making-Under-Uncertainty/
│
├── README.md
├── AI_Decision_Making_Under_Uncertainty.ipynb
│
└── images/
    ├── confusion_matrix.png
    ├── irrigation_probability.png
    └── changing_weather_decision.png

---

## Key Implementation

The project follows these main stages:

1. Generate/Collect Data

Agricultural and weather variables are prepared for analysis.

2. Introduce Missing Data

Some sensor values are intentionally removed to simulate real-world incomplete information.

3. Preprocess Data

Missing numerical values are handled using median imputation, while categorical values are handled using the most frequent value.

4. Train the Model

A Random Forest classifier learns patterns from the available data.

5. Generate Probabilities

The model estimates the probability that irrigation is required.

6. Apply Decision Theory

Expected costs are calculated for the possible actions.

7. Recommend an Action

The AI selects:

IRRIGATE
IRRIGATE LIGHTLY
or
WAIT

8. Update the Decision

When new weather or sensor information becomes available, the system recalculates the recommendation.

---

## Example Decision

An example situation might look like:

Soil Moisture:       20%
Temperature:         36°C
Rain Probability:   15%
Humidity:            45%
Wind Speed:          18 km/h
Crop Stage:          Flowering

AI assessment:

Probability irrigation is needed: High

Recommendation:
IRRIGATE

If the rain probability subsequently increases significantly, the AI can reassess the situation and recommend:

WAIT

---

## Visualizations

The project includes visualizations showing:

- Model classification performance
- Confusion matrix
- Irrigation probability
- Effect of changing rainfall probability
- Changing AI recommendations over time

These visualizations make the AI's decision-making process easier to understand.

---

## Key Learning

This project demonstrates that AI does not always need perfect information to make useful decisions.

An effective AI decision-making system can:

«Observe → Estimate → Evaluate → Decide → Update»

Rather than assuming certainty, the system considers available evidence and uncertainty before selecting an action.

The project also demonstrates the difference between prediction and decision-making.

A machine-learning model may predict that irrigation is likely, but a decision-making system must go further and determine what action should be taken based on the potential consequences.

---

## Challenges

Missing Data

Real-world sensors may fail or produce incomplete readings.

Solution: Missing-value imputation.

Uncertainty

Environmental conditions do not always provide a clear answer.

Solution: Use probability estimates instead of only binary predictions.

Conflicting Information

Dry soil may indicate irrigation while a high rain probability suggests waiting.

Solution: Combine multiple variables through machine learning and decision analysis.

Changing Conditions

Weather forecasts and sensor readings can change.

Solution: Recalculate the AI recommendation when new information arrives.

Decision Risk

Over-irrigation wastes water, while under-irrigation may damage crops.

Solution: Use expected-cost decision-making.

---

## Limitations

This project is an educational prototype.

The dataset is simulated rather than collected from a live farm, and the cost values used by the decision engine are illustrative.

A production system would require:

- Real farm sensor data
- Reliable weather APIs
- Crop-specific requirements
- Soil characteristics
- Farm location
- Evapotranspiration data
- Real irrigation costs
- Model monitoring
- Human oversight

---

## Future Improvements

Future versions could include:

- Real-time weather API integration
- IoT soil-moisture sensors
- Live agricultural datasets
- Bayesian decision-making
- Reinforcement Learning
- Deep Learning
- Crop-specific irrigation models
- Real-time dashboards
- Automated irrigation control with safety mechanisms

---

## Key AI Concepts Demonstrated

This project provides practical demonstrations of:

- Artificial Intelligence
- Machine Learning
- Classification
- Probability
- Uncertainty
- Missing-data handling
- Decision Theory
- Risk-aware decision-making
- Dynamic/adaptive decision-making
- Human-in-the-loop AI

---

## Conclusion

The Smart Irrigation Recommendation System demonstrates how Artificial Intelligence can make useful decisions when information is incomplete, uncertain, or constantly changing.

The system does not simply wait for perfect information. Instead, it:

1. Processes the available information.
2. Handles missing values.
3. Estimates the probability of irrigation need.
4. Evaluates the possible actions.
5. Selects the action with the best expected outcome.
6. Updates its recommendation when new information becomes available.

The central lesson is:

«Intelligent AI decision-making is not about having perfect information. It is about making the best possible decision with the information currently available and continuously updating that decision as new evidence arrives.»

---

## Project Type

Practical AI / Machine Learning Project

Domain: Agriculture & Smart Farming

Focus: AI Decision-Making Under Uncertainty

Language: Python

Model: Random Forest Classifier

Decision Approach: Probability + Expected Cost