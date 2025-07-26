FROM --platform=linux/amd64 python:3.9-slim

WORKDIR /app

# Install dependencies first to leverage caching
RUN pip install --no-cache-dir pymupdf

# Copy the script
COPY extract_outline.py .

CMD ["python", "extract_outline.py"]
