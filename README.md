# 🌬️ Wind Forecast Monitoring App

A full-stack web application for monitoring UK wind power generation and evaluating forecast performance using data from the **Elexon BMRS API**.

🔗 **Live Demo:** https://wind-forecast-frontend-dusky.vercel.app/

💻 **GitHub Repository:** https://github.com/mohithshuka/windForecast

## 🚀 Overview

Wind generation is an important part of the UK's renewable energy system. This application helps users compare actual wind generation with published forecasts, explore forecast horizons, and visualize the relationship between forecast and actual generation.

The application uses a React frontend and a Python FastAPI backend to retrieve and process energy data.

## ✨ Features

- 📊 Interactive visualization of actual and forecast wind generation
- 🌬️ UK wind power data from the Elexon BMRS API
- ⏱️ Configurable forecast horizon
- 📅 Selectable date range for data analysis
- 🔄 Backend API for fetching and processing energy data
- 📈 Forecast-versus-actual comparison to support forecast evaluation
- 🌐 Web-based dashboard accessible through the live demo

## 🛠️ Technology Stack

| Component | Technologies |
|---|---|
| Frontend | React, JavaScript, HTML, CSS |
| Backend | Python, FastAPI |
| API | Elexon BMRS API |
| Data analysis | Jupyter Notebook, Python |
| Frontend deployment | Vercel |
| Backend deployment | Render |

## 🏗️ Architecture

```text
Elexon BMRS API
       |
       v
Python FastAPI Backend
       |
       v
Data Fetching and Processing
       |
       v
React Frontend Dashboard
       |
       v
Forecast vs Actual Visualization
```

## 📂 Project Structure

```text
windForecast/
├── backend/
│   ├── main.py
│   ├── data_fetcher.py
│   ├── forecast_selector.py
│   └── requirements.txt
├── frontend/
│   ├── public/
│   ├── src/
│   └── package.json
├── analysis/
│   └── forecast_analysis.ipynb
├── .gitignore
└── README.md
```

## 🔌 Data Sources

The application uses Elexon BMRS datasets:

- **FUELHH:** Actual half-hourly generation by fuel type, including wind.
- **WINDFOR:** Wind generation forecast data.

Official API documentation:

- [FUELHH API](https://bmrs.elexon.co.uk/api-documentation/endpoint/datasets/FUELHH/stream)
- [WINDFOR API](https://bmrs.elexon.co.uk/api-documentation/endpoint/datasets/WINDFOR/stream)

## 💻 Run Locally

### Prerequisites

- Python 3.10 or later
- Node.js and npm
- Git

### 1. Clone the repository

```bash
git clone https://github.com/mohithshuka/windForecast.git
cd windForecast
```

### 2. Start the backend

```bash
cd backend
python -m venv venv
```

Activate the virtual environment.

**Windows PowerShell:**

```powershell
.\venv\Scripts\Activate.ps1
```

Install dependencies and start the server:

```bash
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

Backend local URL: http://localhost:8000

FastAPI documentation: http://localhost:8000/docs

### 3. Start the frontend

Open a second terminal:

```bash
cd frontend
npm install
npm start
```

The frontend will usually be available at http://localhost:3000.

If the frontend requires a backend API URL, configure it to point to `http://localhost:8000` for local development.

## 🌐 Deployment

- **Live frontend:** [Wind Forecast Monitoring App](https://wind-forecast-frontend-dusky.vercel.app/)
- **Backend API:** [FastAPI service on Render](https://windforecast-d5zn.onrender.com)
- **Backend API documentation:** [Open Swagger UI](https://windforecast-d5zn.onrender.com/docs)

The frontend requires a working connection to the deployed backend for data loading and visualization. The backend may take some time to respond after inactivity on a free hosting plan.

## 📈 Forecast Evaluation

The application is designed to compare published wind forecasts with actual generation data over a selected date range and forecast horizon.

Useful evaluation metrics include:

- **MAE (Mean Absolute Error):** Average absolute difference between forecast and actual generation.
- **RMSE (Root Mean Squared Error):** Penalizes larger forecast errors.
- **MAPE (Mean Absolute Percentage Error):** Percentage-based error measure, where appropriate.

Numerical results should be added after running the analysis against the selected dataset. This application evaluates published forecasts; it should not be described as training its own prediction model unless that functionality is implemented.

## 🎯 Project Objective

The goal is to provide a simple and accessible dashboard for exploring UK wind generation data and assessing how published forecasts compare with actual generation. This can help users understand forecast errors and the challenges involved in renewable energy forecasting.

## 👨‍💻 Author

**Mohith Shuka**

- GitHub: https://github.com/mohithshuka
- Project repository: https://github.com/mohithshuka/windForecast

---

⭐ If you find this project useful, consider starring the repository.
