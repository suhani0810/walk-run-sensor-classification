# Walking Running Classification (PRCP-1013)

## Problem Statement
This project developed a highly accurate system to distinguish between walking and running using raw, noisy data from wrist-worn sensors. This is a fundamental building block for fitness tracking and health monitoring technology.

## Doman Analysis
The dataset contains 88,588 rows of raw sensor readings captured at high frequency:
  - **Date/Time/Username:** Temporal data and user identification.
  - **Wrist:** Indicates which arm the device was worn on (0 for left, 1 for right); used to ensure "wrist-neutral" accuracy.
  - **Activity (Target):** Binary label (0 for Walking, 1 for Running).
  - **Acceleration_x/y/z:** Linear acceleration along the three axes. The Y-axis (vertical) was found to be the most indicative of the "bounce" in running.
  - **Gyro_x/y/z:** Angular velocity (rotation) around the three axes, capturing the arm swing intensity.

## Feature Engineering & Insights
- **Variation is Key:** The standard deviation (variance) in acceleration is a better predictor than movement direction.
- **Vertical Signature:** The Y-axis (vertical) is the most informative for detecting the "bounce" associated with running.
- **Timestamp Precision:** Converted raw strings to micro-second precision to track rapid physical transitions.

## Results
- Developed a highly sensitive model with over **99% accuracy**.
- Hyperparameter optimization was essential to pushing the model to elite-level performance.

## Future Scope
- Expanding activity recognition to cycling, swimming, or climbing stairs.
- Edge deployment for real-time tracking on smartwatches (TensorFlow Lite).

## Technologies Used
- Python (Pandas, Scikit-learn)
- XGBoost, SVM, and KNN models
