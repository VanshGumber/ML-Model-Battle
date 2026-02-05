# ML Model Battle  
**Interactive benchmarking of classical machine learning models**

🔗 **Live App:** https://mlmodelbattle.streamlit.app/

---

## Overview
ML Model Battle is an interactive Streamlit application designed to compare classical machine learning classifiers under identical data preprocessing and evaluation conditions. The project emphasizes **fair comparison**, **reproducibility**, and **interpretability** rather than model optimization.

Users select a model to compete against a randomly chosen baseline, allowing intuitive exploration of performance trade-offs across different algorithms.

---

## Key Features
- Interactive model selection and evaluation via Streamlit  
- Controlled benchmarking using a shared preprocessing and training pipeline  
- Adjustable train–test split ratio and random seed  
- Side-by-side performance comparison between user-selected and baseline models  
- Detailed classification reports for interpretability  

---

## Models Included
The application evaluates the following classifiers:
- Logistic Regression  
- Random Forest  
- k-Nearest Neighbors (KNN)  
- Support Vector Machine (SVM)  
- Gradient Boosting Classifier  

All models are trained and evaluated using the same pipeline to ensure fairness.

---

## Dataset
- Tabular classification dataset loaded from `data.csv`
- Preprocessing steps include:
  - Handling missing categorical values
  - Filtering unrealistic or invalid records
  - Encoding categorical features using label encoding
  - Feature scaling using `StandardScaler`
- Target variable: `income`

*(Dataset preprocessing is intentionally kept explicit to ensure transparency.)*

---

## Evaluation Methodology
- Dataset is split into training and test sets using a configurable test size and random seed  
- Each model is trained using a unified `Pipeline` consisting of:
  - Feature scaling
  - Model-specific training  
- Performance is measured using:
  - Accuracy
  - Full classification report (precision, recall, F1-score)

---

## Application Flow
1. User selects:
   - Test set ratio  
   - Random seed  
   - Preferred ML model  
2. A baseline model is randomly selected from the remaining models  
3. Both models are trained and evaluated on the same data split  
4. Results are displayed side-by-side  
5. A simple outcome (Win / Loss / Draw) highlights comparative performance  

---

## Purpose and Learning Outcomes
This project was built to:
- Develop intuition around model behavior under identical conditions  
- Highlight the impact of model choice on performance  
- Reinforce the importance of controlled experimentation in ML evaluation  
- Serve as a foundation for more advanced benchmarking and decision-support systems  

---

## Tech Stack
- Python  
- Streamlit  
- Scikit-learn  
- Pandas  

---

## How to Run Locally
```bash
pip install streamlit scikit-learn pandas
streamlit run app.py
```

Ensure `data.csv` is present in the project directory.

---

## Notes
- The project prioritizes clarity and reproducibility over hyperparameter tuning  
- All models are evaluated using default parameters to maintain consistency  

---

## Future Extensions
- Add latency and model size comparisons  
- Support multiple datasets  
- Integrate cross-validation  
- Visualize metric trade-offs across runs  
