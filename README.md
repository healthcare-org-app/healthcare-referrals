# referrals-service

referrals-service — domain: ehr

- **Port:** 8310
- **Language:** Python 3.11 + Flask
- **Database:** `ehr` (Postgres, table `referrals`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/referrals/`          |
| POST      | `/api/referrals/`          |
| GET       | `/api/referrals/<id>`      |
| PUT/PATCH | `/api/referrals/<id>`      |
| DELETE    | `/api/referrals/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `providers-service`
- `patients-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
