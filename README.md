# Bengaluru Home Price Prediction

A machine learning project that predicts real estate house prices in Bengaluru using historical market data and property features.

## Project Overview

This project builds a machine learning model to estimate house prices based on property characteristics like location, size, amenities, and other market factors. It combines data analysis, model training, and a full web interface for predictions.

## Features

- **Price Prediction**: Predict house prices based on property features
- **Web Interface**: User-friendly frontend for making predictions
- **REST API**: Backend server for model inference
- **Data Analysis**: Comprehensive analysis of Bengaluru housing market
- **Model Training**: Machine learning model trained on real estate data

## Project Structure

- `model/` - Trained ML model and configuration
- `server/` - Flask backend API for predictions
- `client/` - HTML/CSS/JavaScript frontend
- `Datasets/` - Training and test datasets
- `bengaluru_house_prices.csv` - Main dataset file

## Getting Started

### Prerequisites
- Python 3.x
- Flask
- scikit-learn (or relevant ML libraries)

### Installation

```bash
pip install flask scikit-learn pandas numpy
```

## Running the Web Application

### Quick Start (Windows)

**1. Start the Backend Server**
```bash
cd "c:\Users\ASWIN BINOY\Desktop\projects\Machine learning\real estate"
python server\server.py
```

Wait for: `* Running on http://127.0.0.1:5000`

**2. Open the Frontend**
- Double-click `client\app.html`, OR
- Run: `start client\app.html`

**3. Make a Prediction**
1. Enter **Area (Square Feet)** - e.g., `1200`
2. Select **BHK** - e.g., `2`
3. Select **Bathrooms** - e.g., `2`
4. Choose **Location** from dropdown
5. Click **"Estimate Price"**

### Running on Linux/Mac

```bash
# Terminal 1 - Start server
cd path/to/real-estate
python server/server.py

# Terminal 2 - Open frontend
open client/app.html  # Mac
xdg-open client/app.html  # Linux
```

## Manual Testing (Command Line)

Test predictions directly without the web interface:

```bash
cd server
python util.py
```

This loads the model and runs 4 test predictions automatically.

## How It Works

1. **Data**: Uses historical Bengaluru house price data with features like location, size, price, etc.
2. **Model**: Trains a machine learning model to predict prices based on property features
3. **API**: Exposes predictions through a REST API endpoint
4. **UI**: Web interface allows users to input property details and get price predictions

### API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/get_location_names` | GET | Returns list of all available locations |
| `/predict_home_price` | POST | Returns predicted price for given property details |

### Example API Request

```bash
curl -X POST http://127.0.0.1:5000/predict_home_price \
  -d "total_sqft=1200" \
  -d "bhk=2" \
  -d "bath=2" \
  -d "location=Electronic City"
```

Response:
```json
{ "estimated_price": 78.5 }
```

## Technologies Used

- **Backend**: Flask, Python
- **Frontend**: HTML, CSS, JavaScript, jQuery
- **ML**: scikit-learn, pandas, numpy
- **Model**: Linear Regression with One-Hot Encoding

## License

Open source
