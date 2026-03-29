# Machine Learning Analysis of Nifty 50  
Using Return-Based Modelling


## Project Overview

This project started with a simple question — can daily financial market data actually be understood using machine learning, or does it only look useful when we see good-looking outputs?

The goal was not just to build models and compare scores, but to understand whether the models were actually capturing something meaningful from the data, and whether that meaning holds when tested properly.


## Problem Statement

Financial data often shows patterns, but the real issue is whether those patterns remain stable on unseen data.

This project explores:

- Whether Nifty 50 daily returns can be explained using a small set of major stocks  
- Whether machine learning can capture that relationship in a meaningful way  
- Whether increasing model complexity actually improves usefulness, or only makes the model look better  


## Dataset Overview

- Target: Nifty 50 daily returns (later converted into direction)  
- Features: Returns of HDFC Bank, ICICI Bank, TCS, Infosys, Reliance  
- Structure: One row per trading day  
- Setup: Train–test split for validation  

The dataset is built using return values instead of prices so that relationships across stocks remain comparable.


## Analytical Approach

The project was built step by step, where each stage raised the next question:

- **Regression**  
  To first check whether any basic explanatory relationship exists  

- **Logistic Classification (Direction Focus)**  
  When exact prediction felt unstable, the focus shifted to direction  

- **Shallow Boosted Tree (Depth = 3)**  
  To explore whether nonlinear or conditional patterns exist  

- **Ensemble Models (Higher Complexity)**  
  To test whether added complexity reveals deeper structure or only stronger-looking outputs  

- **Evaluation & Reliability Analysis**  
  Moving beyond accuracy to ROC, AUC, and confidence behaviour, especially high-confidence errors  


## Key Results

- Logistic Classification Accuracy: ~86%  
- Test AUC: ~0.93  
- Errors remain relatively balanced (as seen in the confusion matrix)  
- More complex models produced higher confidence, but also higher high-confidence mistakes  


## Final Model Selection

Logistic Regression emerged as the most reliable model.

While more complex models appeared stronger in some aspects, they also introduced higher risk through confident but incorrect predictions. Logistic regression remained more balanced and controlled, making it more dependable.


## Key Insights

- Financial data contains structure, but not all of it is stable  
- Predicting direction is more reliable than predicting exact returns  
- Increasing complexity does not necessarily improve usefulness  
- Reliability matters more than raw accuracy  


## Limitations

- Only same-day data is used (no lag-based features)  
- Limited feature set (no macroeconomic variables)  
- No explicit modelling of market regimes or volatility shifts  


## Future Improvements

- Introduce lag-based features  
- Include macroeconomic and global indicators  
- Add volatility or regime-based modelling  
- Focus more on feature engineering rather than increasing model complexity  


## Repository Structure

machine-learning-project/

├── README.md
├── reports/
│ └── ML Project Report.pdf
│ └── ML Project Fact Sheet.pdf
├── analysis/
│ └── ML Project Detailed Working Analysis.pdf
├── data/
│ └── ML Project Dataset.csv
├── assets/
│ └── Confusion Matrix.png
│ └── Final Metrics.png


## Project Files

- **ML Project Report.pdf**  
  Final structured explanation of the project  

- **ML Project Fact Sheet.pdf**  
  One-page summary of model performance, reliability, and final decision  

- **ML Project Detailed Working Analysis.pdf**  
  Step-by-step analytical thinking and detailed modelling process  

- **ML Project Dataset.csv**  
  Dataset used for modelling  


## Final Conclusion

This project became less about comparing models and more about understanding how models behave on financial data.

The key takeaway is simple: a model is useful not because it looks strong, but because it remains reliable when it matters.

In this dataset, a simpler model turned out to be the better choice — not because it was the most powerful, but because it was the most dependable.
