# Deep Learning Virtual Lab: Time-Series Forecasting using LSTM

An academic-style virtual laboratory for exploring Long Short-Term Memory (LSTM) neural networks through time-series sequence prediction. This project contrasts highly volatile financial data with cyclical meteorological data and adheres to the IIT/VESIT Virtual Lab UI pattern, providing a structured educational experience.

![VESIT Logo](frontend/public/vesit-logo.png)

## 🚀 Features

- **Dual Data Paradigms**: Seamlessly switch between predicting chaotic, volatile data (Google/Tesla Stocks) and predictable, cyclical data (Historical Mumbai Temperatures).
- **Interactive Hyperparameter Tuning**: Dynamically adjust the model's architecture and memory:
  - Sequence Length (Sliding Window Size)
  - Number of Stacked LSTM Layers (1 to 3)
- **Interactive Visualizers**: A custom UI component that visually demonstrates the "Sliding Window" technique, highlighting features ($X$) and targets ($y$).
- **Comprehensive Evaluation**:
  - Live Model Convergence charts tracking Mean Squared Error (MSE) loss.
  - Interactive Actual vs. Predicted time-series charts using Plotly.js to demonstrate temporal lag and trend tracking.
  - Automatic calculation of Root Mean Squared Error (RMSE).
- **Academic Content**: Integrated pedagogical sections for Aim, Learning Outcomes, Theory, Procedure, Observation, Quiz, and References.

## 🛠️ Tech Stack

- **Frontend**: Next.js, React, Tailwind CSS, Plotly.js.
- **Backend**: FastAPI (Python), Uvicorn.
- **Machine Learning**: PyTorch (LSTM Engine), scikit-learn (MinMaxScaler).
- **Data Pipeline**: yfinance API (Stocks) and Open-Meteo Archive API (Weather).

## 📂 Project Structure

```text
.
├── backend/            # FastAPI Server & PyTorch Logic
│   ├── main.py         # API Endpoints (/api/simulate)
│   ├── ml_model.py     # LSTM Training, preprocessing, and data fetching
│   └── requirements.txt
├── frontend/           # Next.js Application
│   ├── src/
│   │   ├── app/        # 8-tab routing (aim, theory, simulation, etc.)
│   │   └── components/ # Simulation Dashboard, Header, Sidebar
│   └── public/         # Assets (VESIT Logo)
└── README.md           # Project Documentation
````

## ⚙️ Setup & Installation

### Prerequisites

  - Python 3.10+
  - Node.js 18+
  - npm

### 1\. Backend Setup (The ML Engine)

Open a terminal and start the PyTorch/FastAPI server:

```bash
cd backend
python -m venv venv
# Windows:
.\venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

pip install -r requirements.txt
python -m uvicorn main:app --reload --port 8000
```

### 2\. Frontend Setup (The User Interface)

Open a **new** terminal window and start the Next.js application:

```bash
cd frontend
npm install
npm run dev
```

Open [http://localhost:3000](https://www.google.com/search?q=http://localhost:3000) in your browser to view the lab.

## 💡 Usage Guide

1.  **Information Tabs**: Read through the **Aim** and **Theory** to understand the vanishing gradient problem and how LSTM gates solve it.
2.  **Simulation**:
      - Navigate to the **Simulation** tab.
      - Select your **Dataset** (e.g., Mumbai Weather or Tesla Stock).
      - Adjust the **Window Size** to define how many past days the model should memorize.
      - Select the number of **LSTM Layers**.
      - Click **RUN SIMULATION**.
3.  **Analysis**:
      - Monitor the **Model Convergence** graph to ensure the Adam optimizer successfully minimizes the MSE loss without exploding gradients.
      - Analyze the **Prediction Graph** to see if the model successfully mapped the seasonal weather curves or if it suffered from "moving average lag" on the volatile stock data.
4.  **Assessment**: Take the **Quiz** to verify your understanding of sequence prediction concepts.

## 🤝 Credits

Developed for the **Department of Computer Engineering, VESIT**. This lab follows the standard Virtual Lab guidelines to provide students with a high-fidelity learning environment for Deep Learning.

-----

*Created for academic and research purposes.*

```
```
