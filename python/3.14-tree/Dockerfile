FROM python:3.14-slim
ENV PYTHONUNBUFFERED=1

# Install minimal runtime deps and the `tree` utility
RUN apt-get update \
    && apt-get install -y --no-install-recommends ca-certificates curl tree \
    && rm -rf /var/lib/apt/lists/*

# Upgrade pip (optional)
RUN python -m pip install --upgrade pip

# non-root user and working dir
RUN useradd --create-home appuser && mkdir /app && chown appuser /app
WORKDIR /app
USER appuser

# default command: start an interactive python
CMD ["python3"]
