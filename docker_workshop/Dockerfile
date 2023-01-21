FROM python:3.8.3-slim

WORKDIR /app
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
COPY . .

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

# Create image - sudo docker build -t <your-prefered-image-name>
# Run container - sudo docker run --publish 8000:8000 <image-nae-or-id>