FROM python:3.9.7-slim

ENV FLASK_APP=app.py \
    PYTHONUNBUFFERED=1

WORKDIR /app

COPY requirements.txt ./

RUN pip3 install --no-cache-dir --requirement requirements.txt

COPY . .

RUN useradd --create-home --uid 1001 appuser
USER appuser

EXPOSE 5000

CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]
