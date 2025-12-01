FROM python:3.10-slim
ENV PYTHONUNBUFFERED=1

RUN apt-get update \
    && apt-get install -y --no-install-recommends build-essential gcc ca-certificates curl \
    && rm -rf /var/lib/apt/lists/*

RUN python -m pip install --upgrade pip

RUN useradd --create-home appuser && mkdir /app && chown appuser /app
WORKDIR /app
USER appuser

CMD ["python3"]
