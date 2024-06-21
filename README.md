## Tourism Recommendation System Model

This model is a tourism recommendation model built with FastAPI and TensorFlow. It provides personalized recommendations of tourism places based on user ratings.

### Features

-   Loads a pre-trained recommendation model.
-   Recommends tourism places for users based on their past ratings.
-   Provides detailed information about recommended places.

### Requirements

-   Python 3.11
-   Docker
-   Tensorflow
-   FastAPI
-   Numpy
-   Uvicorn
-   Pandas
-   Pydantic

### Setup and Installation

### Clone the Repository

```bash
git clone https://github.com/Toursantara/model-deployment
cd model-deployment
```

### Docker Setup

1. **Build the Docker Image**

    ```bash
    docker build -t tourism-recommender .
    ```

2. **Run the Docker Container**

    ```bash
    docker run -p 8080:8080 tourism-recommender
    ```

### Local Setup (Without Docker)

1. **Install Dependencies**

    Ensure you have Python 3.11 installed. Then, install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

2. **Download Model and Data**

    Download the necessary data and model files:

    ```bash
    mkdir -p temp && cd temp
    curl -o tourism_rating.csv https://your-storage.googleapis.com/
    curl -o tourism_with_id.csv https://your-storage.googleapis.com/
    curl -o model.zip https://your-storage.googleapis.com/toursantara/model-recommendation/model_recommender.zip
    unzip model.zip -d model
    rm model.zip
    cd ..
    ```

3. **Run the FastAPI Application**

    ```bash
    uvicorn app:app --host 0.0.0.0 --port 8080
    ```

## API Endpoints

### Recommend Places

-   **URL:** `/recommend/`
-   **Method:** `POST`
-   **Request Body:**

    ```json
    {
        "user_id": 123
    }
    ```

-   **Response:**

    ```json
    {
        "status": "success",
        "data": [
            {
                "id": 1,
                "name": "Place Name",
                "category": "Category",
                "description": "Description",
                "city": "City",
                "city_category": "City - Category",
                "rating": 4.5,
                "lat": 12.34,
                "long": 56.78
            },
            ...
        ]
    }
    ```




<br>

> Acknowledgments : Credit to m1kael1 

