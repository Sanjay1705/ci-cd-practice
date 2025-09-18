FROM python:3.10-slim

WORKDIR /app

COPY app.py .

CMD ["python", "app.py"]

FROM jenkins/jenkins:lts

USER root

RUN apt-get update && \
    apt-get install -y docker.io && \
    apt-get clean

RUN apt-get install -y git

USER jenkins