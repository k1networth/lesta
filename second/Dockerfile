FROM python:3.9 as builder

WORKDIR /app

RUN python -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

FROM python:3.9-slim

WORKDIR /app

RUN useradd -m flaskuser

COPY --from=builder /opt/venv /opt/venv
COPY app.py .

ENV PATH="/opt/venv/bin:$PATH"
ENV FLASK_APP=app.py

USER flaskuser

EXPOSE 5000
CMD ["flask", "run", "--host=0.0.0.0"]
