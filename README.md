# California Housing Prices Prediction

## Overview
This project features a robust end-to-end Machine Learning pipeline designed to predict median housing prices in California districts based on 1990 census data.

## Key Features & Achievements
* **Data Engineering & Preprocessing**: Performed extensive data wrangling, cleaning, and imputation on a dataset containing over 20,600 census records, ensuring a high-quality dataset for modeling.
* **Exploratory Data Analysis**: Utilized `Matplotlib` for comprehensive data visualization, geographical distribution analysis, and correlation discovery.
* **Model Optimization**: Engineered data transformation pipelines and applied `GridSearchCV` for systematic hyperparameter tuning. The final optimized model achieved a Root Mean Squared Error (RMSE) of roughly **$47,000**.
* **Production & Deployment**: Containerized the final predictive model into a Docker image and deployed it as a scalable REST API to serve real-time model inferences efficiently.

## Project Structure
- `CaliforniaHousing.ipynb`: The primary Jupyter Notebook containing the full ML pipeline, from data extraction and EDA to model training, evaluation, and prediction.
- `datasets/`: Directory containing the raw census data.

## Technologies Utilized
- **Languages:** Python
- **Machine Learning & Data:** Scikit-Learn, Pandas, NumPy
- **Data Visualization:** Matplotlib
- **MLOps & Deployment:** Docker, RESTful API framework (e.g., Flask/FastAPI)

## Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook
- Docker (for deploying the containerized API)

### Installation
1. Clone the repository and navigate to the project directory:
   ```bash
   git clone <repository_url>
   cd CaliforniaHousing
   ```
2. Set up a virtual environment and install the underlying dependencies:
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows use `env\Scripts\activate`
   pip install jupyter pandas numpy scikit-learn matplotlib
   ```
3. Launch the Jupyter Notebook to explore the modeling phase:
   ```bash
   jupyter notebook CaliforniaHousing.ipynb
   ```

### API Deployment
To run the containerized REST API serving the model locally:
1. Build the Docker image:
   ```bash
   docker build -t ca-housing-api .
   ```
2. Run the container:
   ```bash
   docker run -p 8000:8000 ca-housing-api
   ```
3. The API will now accept POST requests at `http://localhost:8000/predict` formatted with model features to return price estimates.
