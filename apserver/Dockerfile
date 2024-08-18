# 開発用ステージ
FROM python:3.11.9-slim-bookworm AS developer

ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1

WORKDIR /opt

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    build-essential=12.9 libmariadb-dev=1:10.11.6-0+deb12u1 gcc=4:12.2.0-3 \
    pkg-config=1.8.1-1 \
    && apt-get -y clean \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .
