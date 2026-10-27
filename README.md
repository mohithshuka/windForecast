
# 🌬️ Wind Forecast Monitoring App

A full-stack wind energy forecasting dashboard built with **React**, **Python FastAPI**, and the **Elexon BMRS API**. The application compares forecasted wind generation with actual generation to help monitor forecast performance and support day-ahead electricity purchasing decisions.

## ✨ Features

- 📊 Interactive dashboard for wind generation monitoring
- 📅 Select a date range to explore generation data
- ⏱️ Configure the available forecast horizon
- 🌬️ Retrieve wind generation and forecast data from Elexon
- 📈 Visualize actual versus forecast generation
- ⚡ Python FastAPI backend for data processing
- ⚛️ React frontend for interactive visualization
- ☁️ Deployment-ready frontend and backend structure

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Frontend | React, JavaScript, CSS |
| Backend | Python, FastAPI |
| API | Elexon BMRS API |
| Server | Uvicorn |
| Frontend Hosting | Vercel |
| Backend Hosting | Render |
| Version Control | Git, GitHub |

## 🏗️ Architecture

```text
User / Browser
      |
      v
React Frontend (Vercel)
      |
      | HTTP API Requests
      v
Python FastAPI Backend (Render)
      |
      v
Elexon BMRS API
      |
      +-- Actual Wind Generation
      +-- Wind Generation Forecasts
```

## 📁 Project Structure

```text
windForecast/
├── analysis/
│   └── forecast_analysis.ipynb
├── backend/
│   ├── main.py
│   ├── data_fetcher.py
│   ├── forecast_selector.py
│   └── requirements.txt
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── App.js
│   │   ├── App.css
│   │   ├── index.css
│   │   └── index.js
│   ├── package.json
│   └── package-lock.json
├── .gitignore
├── LICENSE
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Python
- Node.js and npm
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/mohithshuka/windForecast.git
cd windForecast
```

### 2. Run the Backend

Open a terminal in the project root:

```bash
cd backend
python -m venv venv
```

Activate the virtual environment.

**Windows PowerShell:**

```powershell
.\venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the API server:

```bash
uvicorn main:app --reload --port 8000
```

Backend URL: `http://127.0.0.1:8000`

API documentation: `http://127.0.0.1:8000/docs`

### 3. Run the Frontend

Open a second terminal:

```bash
cd frontend
npm install
npm start
```

Frontend URL: `http://localhost:3000`

Keep both servers running while testing the application locally.

## 🔗 Data Sources

The application uses the Elexon Balancing Mechanism Reporting Service (BMRS).

- [Elexon BMRS API Documentation](https://bmrs.elexon.co.uk/api-documentation)
- [FUELHH — Generation by Fuel Type](https://bmrs.elexon.co.uk/api-documentation/endpoint/datasets/FUELHH/stream)
- [WINDFOR — Wind Forecast Data](https://bmrs.elexon.co.uk/api-documentation/endpoint/datasets/WINDFOR/stream)

Forecast and actual generation should be aligned to the appropriate settlement periods before accuracy is calculated.

## ☁️ Deployment

### Backend — Render

1. Connect the GitHub repository to Render.
2. Create a Web Service.
3. Set the root directory to `backend`.
4. Set the build command:

   `pip install -r requirements.txt`

5. Set the start command:

   `uvicorn main:app --host 0.0.0.0 --port $PORT`

6. Deploy and test the API using the deployed `/docs` URL.

### Frontend — Vercel

1. Import the GitHub repository into Vercel.
2. Set the root directory to `frontend`.
3. Set the build command to `npm run build`.
4. Set the output directory to `build`.
5. Add an environment variable named `REACT_APP_API_URL` with the deployed Render backend URL.
6. Ensure the frontend uses this variable for API requests.
7. Configure backend CORS to allow requests from the deployed frontend domain.
8. Redeploy and test the application.

## 📈 Forecast Accuracy

Forecast performance can be evaluated using:

- **MAE (Mean Absolute Error):** Measures the average absolute difference between actual and forecast values.
- **RMSE (Root Mean Squared Error):** Penalizes larger forecast errors more heavily.
- **MBE (Mean Bias Error):** Measures the average signed forecast error.

These metrics should be calculated using aligned forecast and actual generation records before reporting numerical results.

## 🔮 Future Improvements

- Add forecast accuracy metrics to the dashboard.
- Improve day-ahead forecast selection using publication timestamps.
- Add unit and integration tests.
- Improve handling of API failures and missing data.
- Add Docker and Docker Compose support.
- Improve mobile responsiveness and accessibility.

## 🤝 Contributing

Contributions are welcome.

1. Fork this repository.
2. Create a feature branch.
3. Commit your changes.
4. Open a pull request with a description of the changes.

## 📄 License

See the [LICENSE](LICENSE) file for license details.

---

**Built with React, Python, FastAPI, and Elexon BMRS data.**
