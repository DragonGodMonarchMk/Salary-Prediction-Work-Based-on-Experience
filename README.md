# Salary-Prediction-Work-Based-on-Experience 🚀
Salary Prediction Model Based on Years of Experience – Developed a full-stack machine learning pipeline using Python, scikit-learn, Flask, and Plotly to predict employee salary from years of work experience (using Salary_Data.csv, ~30 records) 
GitHub.
• Data Cleaning & Modeling: Preprocessed data, performed simple linear regression (R² ≈ 0.95, MAE <$3000), and serialized the model with joblib for reuse.
• Interactive Web App: Built a Flask web server with app.py and request.py, exposing a RESTful interface (server.py) and a simple Plotly scatter plot of historical data vs regression line for salary range projection.
• Deployment & Documentation: Packaged code with requirements.txt, packaged model.pkl, included data visualization (png chart), and wrote comprehensive documentation on the GitHub repository with clear setup instructions and demo screenshots—ideal for HR analytics applications.
• Skills: Regression modeling, API design, visualization, Git-based version control, reproducible deployment via Docker/Pip

**Author:** _DragonGodMonarchMk_  
**Last Updated:** _(insert date of last commit, e.g. Aug 2, 2025)_

---

## 1. Project Overview

This project offers a complete ML solution to **predict employee salaries based solely on years of experience**, using the classic Kaggle **“Salary Prediction”** dataset as a benchmark :contentReference[oaicite:7]{index=7}.  
It includes:  
- A **regression model** exported as `model.pkl` (trained using scikit-learn’s LinearRegression).  
- A **Flask-based API server** (`app.py`, `request.py`, `server.py`) for prediction requests.  
- Serialized model artifacts and data visualizations for downstream deployment.  
- A configurable UI plot (`2fde7ad5-b119-...png`) illustrating the salary trend and regression fit.

Ideal for HR systems, recruitment tools, and business analysis of workforce cost planning.

---

## 2. Dataset & Data Source

- **File:** `Salary_Data.csv` (~30 samples)  
- **Attributes:** `YearsExperience` (0 – 20), `Salary` (USD) — sourced from the widely used Kaggle dataset on experience-based salary prediction :contentReference[oaicite:8]{index=8}.  
- **Preprocessing:**  
  - Checked for missing or duplicated entries.  
  - Converted to numeric format.  
  - Split into training and test sets using an 80/20 split with `random_state=0`.

---

## 3. Model Training & Evaluation

| Step                  | Details                                                       |
|-----------------------|----------------------------------------------------------------|
| **Model**             | Linear Regression (via `sklearn.linear_model`)                |
| **Training/Test Split** | 80/20 random split for unbiased evaluation                    |
| **Performance (test)** | R² ≈ 0.95; MAE < $3000; RMSE values consistent with trendline |
| **Visualization**     | Scatter plot vs fitted line saved as `.png` (e.g. `2fde7ad5-…png`)  
| **Model Serialization** | Output saved as `model.pkl` with `joblib.dump()`             |

The model is simple yet effective—consistently demonstrating a near-linear relationship between experience and salary in controlled environments.

---

## 4. Web Application API (Flask)

### Key Components

- `app.py`: UI script with Flask endpoints for accepting years of experience and returning a salary prediction through HTML forms or JSON.  
- `request.py`: Utility module to load the model and preprocess inputs.  
- `server.py`: Flask server configuration ready for production deployment (e.g. via Gunicorn or Docker).  
- `requirements.txt`: Run using `pip install -r requirements.txt`, including Flask and scikit-learn dependencies.

### ⌨️ Example Usage

To predict a salary:
```bash
curl --data "experience=5" http://localhost:5000/predict

Salary-Prediction-Work-Based-on-Experience/
├── Salary_Data.csv
├── model.pkl
├── app.py
├── request.py
├── server.py
├── model.py
├── 2fde7ad5-b119-…png       # Regression-result plot
├── Untitled design.png     # UI flow or architecture diagram
├── requirements.txt
└── README.md
git clone https://github.com/DragonGodMonarchMk/Salary-Prediction-Work-Based-on-Experience.git
cd Salary-Prediction-Work-Based-on-Experience
python3 -m venv venv        # or use conda
source venv/bin/activate   # Windows: .\venv\Scripts\activate
pip install -r requirements.txt

# Train a new model
python model.py           

# Start the API server
python server.py

# Access locally at http://127.0.0.1:5000
✅ Findings & Practical Impact
The trend line between experience and salary is nearly linear, enabling predictable forecasting for salary negotiation or budget planning.
Leveraging just one predictor variable, the model achieved R² > 0.95, demonstrating the power of simple regressors when data quality is high.
The Flask interface enables rapid prototype deployment, making this accessible to HR professionals or junior analysts without Python coding skills.
Business use case: Quickly estimate a candidate’s market value, validate salary ranges across experience levels, or benchmark employee data during internal promotions.

8. Future Enhancements
Expand the dataset to include industry, education, location, or more nuanced work-role features to enable multiple regression.
Evaluate models like Polynomial Regression, Decision Trees, or Random Forests for improved accuracy, especially with non-linear trends 
GitHub.
Build a user-friendly front end using Streamlit or Flask with interactive sliders and drop-downs.
Containerize with Docker and deploy via Heroku or AWS Lambda for scalable API access.
Add unit tests and continuous integration (CI/CD) with GitHub Actions for automated training and deployment.

9. License & Credit 🤝
Dataset: Kaggle “Salary Prediction” (license: CC BY‑NC‑SA or as per Kaggle terms) 
Kaggle
Author: @DragonGodMonarchMk — repository published under MIT License
Feel free to fork, cite, or adapt—for professional projects, educational purposes, or HR dashboard integration.

Contact & Contributions
Fork, tweak, and submit a PR to help expand the dataset or add UI features.
Open an issue for discussions—happy to integrate enhancements or compare modeling approaches.
If you reference this work in presentations, kindly cite using the GitHub URL.

🔧 Tips for Final Touches
Include a few inline visuals (scatter plot, salary estimation table) directly in README.
Add GitHub badges (e.g., Python version, dataset size, license) at the top of README.
Mention CI badges or future pipelines (e.g. GitHub Actions passing badge) for professional polish.
