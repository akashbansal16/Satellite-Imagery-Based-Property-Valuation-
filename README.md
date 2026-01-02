# Satellite-Imagery-Based-Property-Valuation-
This project predicts house prices using both:

- **Tabular data** (area, rooms, location, etc.)
- **Satellite images** of the property surroundings

The project uses **machine learning and deep learning** and compares:

- Tabular data only
- Satellite images only
- A fusion of both

```
project/
│
├── data_fetcher.py                # Script to download satellite images
│
├── preprocessing.ipynb            # Data cleaning and feature engineering
├── model_training.ipynb           # Model evaluation and fusion analysis
├── test_data.ipynb                # Final prediction on test data
│
└── models/                        # Saved trained models
    ├── cnn_inceptionv3_model.keras
    ├── xgboost_model.pkl
    ├── fusion_model.pkl
    └── tabular_scaler.pkl
```
## Setup Instructions

### Download Satellite Images 
If you want to download satellite images yourself:

1. Open `data_fetcher.py`
2. Add your **Google Maps Static API key**
3. Run the script:

```bash
python data_fetcher.py
```
This will download satellite images and save them in:

- `images_train/`
- `images_test/`


## How to Run the Project (Step by Step)

### Step 1: Data Preprocessing

Open and run:
```bash
preprocessing.ipynb
```

This notebook:
- Cleans the data
- Performs basic feature engineering


### Step 2: Model Evaluation and Fusion

Open and run:
```bash
model_training.ipynb
```

This notebook:
- Train the models
- Evaluates tabular, image, and fusion models
- Compares performance
- Generates explainability using Grad-CAM

### Step 3: Generate Final Predictions

Open and run:
```bash
test_data.ipynb
```

This notebook:
- Loads the final selected model
- Predicts house prices on `test.csv`
- Generates the final submission CSV file

---

## Models Used

- **XGBoost** → Tabular data model (best performing)
- **InceptionV3 + MLP** → Satellite image model
- **Fusion Model** → Combines both outputs


