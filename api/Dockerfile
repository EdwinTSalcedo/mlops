# Revisar el siguiente link para mas información sobre la creación automatica de Dockerfiles 
# en Visual studio code https://aka.ms/vscode-docker-python
FROM python:3.9-slim

EXPOSE 5002

WORKDIR /app
COPY . /app

# Instalar dependencias
COPY requirements.txt .
RUN apt-get update && apt-get install ffmpeg libsm6 libxext6  -y
RUN pip install -r requirements.txt


# Inicializar el servidor
CMD ["gunicorn", "--bind", "0.0.0.0:5002", "app:app"]
