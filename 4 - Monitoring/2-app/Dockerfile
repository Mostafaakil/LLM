FROM python:3.9-slim

RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    libffi-dev \
    tzdata \
    && rm -rf /var/lib/apt/lists/*
ENV PYTHONUNBUFFERED=1

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip setuptools wheel \ 
    &&pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["streamlit", "run", "app.py"]