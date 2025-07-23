FROM python:3.11-slim
RUN sed -i 's|http://deb.debian.org/debian|https://mirror.yandex.ru/debian|g' /etc/apt/sources.list && \
    sed -i 's|http://security.debian.org/debian-security|https://mirror.yandex.ru/debian-security|g' /etc/apt/sources.list && \
    apt-get update && apt-get install -y --no-install-recommends \
        python3-requests python3-yaml ca-certificates && \
    rm -rf /var/lib/apt/lists/*
WORKDIR /app
COPY bridge.py .
ENTRYPOINT ["python","-u","/app/bridge.py"]
