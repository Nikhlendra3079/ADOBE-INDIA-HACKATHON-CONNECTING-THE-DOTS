FROM --platform=linux/amd64 python:3.10-slim

WORKDIR /app

COPY requirements.txt .

RUN apt-get update && \
    apt-get install -y --no-install-recommends libglib2.0-0 libsm6 libxrender1 libxext6 && \
    pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt && \
    apt-get purge -y --auto-remove && \
    rm -rf /var/lib/apt/lists/*

COPY ./models ./models
COPY main.py .
COPY input ./input

RUN mkdir -p /app/output

CMD ["python", "main.py"]
