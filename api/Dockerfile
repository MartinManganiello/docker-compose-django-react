FROM python:3.8
ENV PYTHONUNBUFFERED 1

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        postgresql-client \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app/api
COPY requirements.txt /app/api
RUN pip install --upgrade pip -r requirements.txt
COPY . /app/api

EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]