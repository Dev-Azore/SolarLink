# STAGE 1: Build
FROM python:3.11-slim AS builder

WORKDIR /app

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential gcc libpq-dev && \
    rm -rf /var/lib/apt/lists/*

# Create a virtual environment
RUN python -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

COPY requirements.txt .
RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# STAGE 2: Runner
FROM python:3.11-slim AS runner

WORKDIR /app

# Ensure the runner uses the virtual environment from the builder
ENV PATH="/opt/venv/bin:$PATH"
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

RUN apt-get update && apt-get install -y libpq-dev && \
    rm -rf /var/lib/apt/lists/*

# Copy the entire virtual environment
COPY --from=builder /opt/venv /opt/venv
COPY . .

RUN addgroup --system django && adduser --system --group django && \
    chown -R django:django /app

USER django
EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]