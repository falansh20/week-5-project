**Tech Stack**

Platform: Google Colab (Jupyter-based environment)

Language: Python

Libraries Used:

pandas – for data cleaning, transformation, and feature engineering

google.colab.files – for downloading files from the Colab environment

Data Source: dataset.csv (includes timestamp, traffic, vehicle type, occupancy, etc.)

Output Format: parking_stream_model2.csv (preprocessed data for further modeling or real-time stream)

**ARCHITECTURAL FLOW**

📥 Input:
  └── dataset.csv
        ├── LastUpdatedDate
        ├── LastUpdatedTime
        ├── Occupancy
        ├── Capacity
        ├── QueueLength
        ├── TrafficConditionNearby
        ├── VehicleType
        └── IsSpecialDay

🔄 Data Preprocessing (Python):
  ├── Combine date and time → Timestamp
  ├── Map traffic levels: low/medium/high → 1/2/3
  ├── Map vehicle types: bike/car/truck → 0.5/1.0/1.5
  ├── Select relevant columns for model
  └── Rename mapped features

📤 Output:
  └── parking_stream_model2.csv
        ├── Timestamp
        ├── Occupancy
        ├── Capacity
        ├── QueueLength
        ├── TrafficConditionNearby (mapped as score)
        ├── VehicleType (mapped as weight)
        └── IsSpecialDay
