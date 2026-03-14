# 🌾 Pest Prediction & Management System

> Early pest risk prediction and decision support for informed farm-level action.

> 🏆 Built for **EYIC 2025 Innovation Challenge** — Agriculture Theme

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)

---

## 📌 Overview

A decision support system — not an automated control tool — that helps Indian smallholder farmers predict pest risk before visible crop damage occurs and take timely, informed action.

This system bridges the gap between early detection and profitable decision-making by:
- **Predicting** pest risk early, before damage occurs, using weather, crop health, and historical data
- **Converting** raw ML predictions into clear, IPM-aligned risk levels and actionable guidance
- **Supporting** cost-aware and resistance-conscious decision-making without removing user control
- **Delivering** recommendations in simplified, localized, and multilingual formats

---

## 📊 Problem Context

- India loses ~₹90,000 crore annually due to pest attacks (CARE Report)
- 10–30% of crop production lost yearly to insects, diseases, and weeds
- Maharashtra crops like **Tur (Pigeon Pea)** lose 8.8–13.4% and **Soybean** loses 10.3–13.2% of actual production
- Pest management decisions today are largely **reactive and experience-based** — farmers realize pest attacks only after visible damage, by which time losses are unavoidable
- Farmers lack early, interpretable risk signals for timely action

---

## 🌱 Key Features

- **Predictive (not reactive):** Forecasts pest risk before damage occurs
- **IPM enforcement:** Prioritizes traps → biocontrol → biopesticides → chemical sprays
- **Cost-optimised advisories:** Recommends the cheapest effective intervention
- **Resistance-aware:** Tracks pesticide Mode of Action to prevent resistance build-up
- **Multilingual support:** Recommendations in simplified, localized formats
- **Multi-source intelligence:** Combines weather + historical pest data + location inputs

---

## 🆚 Competitive Advantage

| Feature | Our System | CROPSAP | Plantix | Farmonaut |
|---|---|---|---|---|
| Predictive forecasting | ✅ | ❌ | ❌ | ❌ |
| IPM hierarchy | ✅ | ❌ | ❌ | ❌ |
| Cost optimisation | ✅ | ❌ | ❌ | ❌ |
| Resistance tracking | ✅ | ❌ | ❌ | ❌ |
| Multi-source data | ✅ | Partial | ❌ | Partial |

---

## 🗂️ Repository Structure

```
AI-Pest-Prediction-and-Management/
│
├── Datasets/
│   ├── Cotton_ICAR_Data.xlsx        # ICAR cotton pest dataset
│   ├── RICE.csv                     # Rice pest dataset
│   └── locations.csv                # District/region location reference
│
├── backend/
│   └── main.py                      # FastAPI app — routes, ML inference, decision engine
│
├── frontend/                        # Flutter project (Android + iOS)
│   ├── AppDelegate.swift
│   ├── AppFrameworkInfo.plist
│   ├── Flutter-Debug.xcconfig
│   ├── Flutter-Release.xcconfig
│   ├── Info.plist
│   ├── flutter_export_environment.sh
│   ├── gradlew.bat
│   ├── gradlew.txt
│   ├── pest_dashboard_android.iml
│   └── readme.txt
│
├── LICENSE
├── PestPrediction.ipynb             # ML training notebook
├── cotton_pest_binary_model.pkl     # Trained cotton pest classifier
├── rice_pest_binary_xgb.joblib      # Trained rice pest XGBoost model
├── requirements.txt
└── README.md                        # ← You are here
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Mobile Frontend | Flutter (Dart) — Android & iOS |
| IDE | Android Studio |
| Backend API | FastAPI (Python) |
| ML Library | scikit-learn |
| ML Models | Random Forest, XGBoost |
| Training Data | ICAR Cotton Dataset, Rice Dataset |
| External APIs | AgroWeather API · Pest Forecast API · Map API |

---

## 🚀 Getting Started

### Prerequisites

- Flutter SDK (`>=3.0.0`)
- Android Studio (Hedgehog or later)
- Python `>=3.9`
- pip

---

### Frontend Setup (Flutter + Android Studio)

1. **Clone the repository**
   ```bash
   git clone https://github.com/K-Rudra22/AI-Pest-Prediction-and-Management.git
   cd AI-Pest-Prediction-and-Management/frontend
   ```

2. **Install Flutter dependencies**
   ```bash
   flutter pub get
   ```

3. **Open in Android Studio**
   - Open Android Studio → `File` → `Open` → select the `frontend/` folder
   - Wait for Gradle sync to complete

4. **Configure the API base URL**
   - Navigate to `lib/services/api_service.dart`
   - Update `baseUrl` to your deployed backend URL:
     ```dart
     const String baseUrl = 'https://your-backend-url.com';
     ```

5. **Run the app**
   ```bash
   flutter run
   ```
   Or use the **Run** button in Android Studio with an emulator or physical device connected.

---

### Backend Setup (FastAPI)

1. **Navigate to the backend directory**
   ```bash
   cd AI-Pest-Prediction-and-Management/backend
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate        # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r ../requirements.txt
   ```

4. **Run the FastAPI server**
   ```bash
   uvicorn main:app --reload --host 0.0.0.0 --port 8000
   ```

5. **API Documentation**
   - Swagger UI: `http://localhost:8000/docs`
   - ReDoc: `http://localhost:8000/redoc`

> **Note:** Add `__pycache__/` to your `.gitignore` to keep the repo clean.

---

## 🤖 ML Models

| Model File | Crop | Type |
|---|---|---|
| `cotton_pest_binary_model.pkl` | Cotton | Binary Pest Classifier |
| `rice_pest_binary_xgb.joblib` | Rice | XGBoost Binary Classifier |

Models are trained using **scikit-learn** and **XGBoost** on ICAR-sourced datasets (`Cotton_ICAR_Data.xlsx`, `RICE.csv`). The training process is documented in `PestPrediction.ipynb`. Inputs include:
- Weather parameters (temperature, humidity, rainfall)
- Historical pest incidence records
- Location data (`locations.csv`)

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 👥 Team

> Built as a group project for the **EYIC 2025 Innovation Challenge** under the Agriculture theme, focused on sustainable AgriTech solutions for Indian smallholder farmers.
