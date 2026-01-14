# Real-Time Risk Scoring Lakehouse (Deep Learning + Data Engineering)

Production-style system that ingests transaction events, builds features with online/offline parity, trains a deep tabular model, serves low-latency risk scores, and monitors drift + data quality.

## Architecture (High Level)
Kafka (events) → Streaming ETL → Bronze/Silver/Gold Lakehouse → Feature Pipeline → Model Training (PyTorch) → Model Registry → FastAPI Serving → Monitoring (DQ + Drift + Latency)

## What’s inside
- Streaming ingestion with schema validation + dead-letter handling
- Lakehouse layout (Bronze/Silver/Gold)
- Feature engineering (offline + online parity)
- Deep learning for tabular data (embeddings + attention-based model)
- FastAPI scoring service with p95 latency metrics
- Drift monitoring + data quality checks
- CI (lint/tests) + reproducible runs (Makefile + Docker)

## Quickstart
```bash
make up
make produce-events
make stream
make train
make serve
make score
