# California House Price Prediction

This project aims to predict house prices in California using machine learning techniques. The application is built using Flask for the backend and deployed using Docker for containerization.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Model Training](#model-training)
- [API Endpoints](#api-endpoints)
- [Docker Deployment](#docker-deployment)
- [Contributing](#contributing)

## Overview
This project involves building a machine learning model to predict house prices in California based on various features such as location, number of rooms, and other relevant attributes. The model is then deployed as a RESTful API using Flask, and Docker is used to containerize the application for easy deployment.

## Features
- Predict house prices based on input features.
- RESTful API built with Flask.
- Dockerized application for easy deployment.
- Linear Regression machine learning model for predictions.

## Installation
To set up the project locally, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/california-house-price-prediction.git
    cd california-house-price-prediction
    ```

2. Create and activate a virtual environment:
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Run the Flask application:
    ```bash
    flask run
    ```

## Usage
After setting up the project, you can use the API to predict house prices. The API accepts POST requests with the required features and returns the predicted price.

Example request:
```bash
curl -X POST http://localhost:5000/predict \
     -H "Content-Type: application/json" \
     -d '{
           "longitude": -122.23,
           "latitude": 37.88,
           "housing_median_age": 41,
           "total_rooms": 880,
           "total_bedrooms": 129,
           "population": 322,
           "households": 126,
           "median_income": 8.3252
         }'
```

## Model Training
To train the model, follow these steps:

1. Prepare the dataset (you can use the California housing dataset).
2. Train the model using the provided Jupyter notebooks or scripts in the `model_training` directory.
3. Save the trained model to the `models` directory.


## API Endpoints
- `POST /predict`: Predict the house price based on input features.

Request body:
```json
{
  "longitude": -122.23,
  "latitude": 37.88,
  "housing_median_age": 41,
  "total_rooms": 880,
  "total_bedrooms": 129,
  "population": 322,
  "households": 126,
  "median_income": 8.3252
}
```

Response:
```json
{
  "predicted_price": 452600
}
```

## Docker Deployment
To deploy the application using Docker, follow these steps:

1. Build the Docker image:
    ```bash
    docker build -t california-house-price-prediction .
    ```

2. Run the Docker container:
    ```bash
    docker run -p 5000:5000 california-house-price-prediction
    ```

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
