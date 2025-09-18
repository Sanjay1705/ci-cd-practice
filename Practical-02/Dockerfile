FROM python:3.11-slim AS builder
WORKDIR /app
COPY requirements.txt .
RUN python -m pip install --upgrade pip \
 && pip install --no-cache-dir --target=/app/deps -r requirements.txt


FROM python:3.11-slim
WORKDIR /app
COPY --from=builder /app/deps /app/deps
COPY app.py .
ENV PYTHONPATH=/app/deps
EXPOSE 5000
CMD ["python", "app.py"]
