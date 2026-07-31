FROM python:3.9-slim-bookworm

WORKDIR /app

# Install build tools needed for packages like psutil that compile C extensions
RUN apt-get update && apt-get install -y --no-install-recommends \
    gcc \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt

COPY run.py .
COPY app/ ./app

EXPOSE 5000

CMD ["python", "run.py"]
