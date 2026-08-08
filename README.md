# IAPTMS-Integrated-Agricultural-Production-and-Transport-Management-System-
Global food security is heavily reliant on the efficiency of agricultural supply chains. Traditionally, agricultural production planning and transportation logistics operate as isolated systems. This information asymmetry leads to significant post-harvest losses, inflated fuel emissions, and sub-optimal fleet utilization.



Running and Using Your Application In Real-Time
Step A: Boot Up the Platform
Open your terminal inside the iaptms-project/ folder and run the server:
bash
uvicorn main:app --reload

Use code with caution.
Open your browser and navigate to http://127.0.0.1:8000. You will see the empty dashboard waiting for live data stream events.
Step B: Simulate Live IoT Hardware / User Ingestion Requests
To simulate edge devices (sensors or mobile app data entries) updating the system dynamically, open a separate terminal window and execute this curl command to post data into the pipeline:
bash
curl -X POST "http://127.0.0" \
     -H "Content-Type: application/json" \
     -d '{"farm_id": "Zone-A_BerryFarm", "soil_moisture": 42.5, "temperature": 34.2, "humidity": 60.0}'

textiaptms-project/
│
├── main.py            # FastAPI Backend (IoT Ingestion, ML & VRPTW Engine)
└── templates/
    └── index.html     # Frontend Live-Monitoring Dashboard
