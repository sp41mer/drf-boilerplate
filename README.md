# Django REST Framework — project boilerplate

The skeleton I start DRF lecture projects from (see `drf-orm-extended`,
`drf-test-examples`, `drf-gql-example` — all grew out of this).

## Includes

1. `conf/settings.py` with logging, DRF renderer config and a local
   database, overridable via `local_settings.py`
2. `Dockerfile` + `docker-compose.yml` with a Postgres health-check
3. Kubernetes manifests (`kubernetes/`): Django deployment + service,
   Postgres deployment/service/storage/configmap
4. flake8 config
5. Docs example under `docs/`

## Run

```bash
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
# or:
docker-compose up
```

## Kubernetes

```bash
kubectl apply -f kubernetes/
```

Build and push the image referenced in
`kubernetes/django-deployment.yaml` first.

Pinned to Django 2.1 — the stack matches the lecture repos it was written
for; bump the pins if you use it as a real starting point.
