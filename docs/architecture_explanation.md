## Architecture

![Real-Time Risk Scoring Architecture](docs/architecture.png)

This system demonstrates a production-style real-time ML scoring platform:

1. Events are ingested via Kafka
2. Streaming ETL performs validation, deduplication, and data quality checks
3. Data is stored in a Lakehouse (Bronze / Silver / Gold)
4. Features are generated with online/offline parity
5. A PyTorch deep learning model is trained on offline features
6. The model is registered and served via FastAPI
7. Monitoring tracks drift, latency, and errors
