# Use an appropriate Python version, for example, python:3.11-slim
FROM python:3.11-slim

ENV APP_HOME /code
ENV PYTHONPATH $APP_HOME
ENV PYTHONUNBUFFERED 1
ENV ENV_CONFIG 1

RUN mkdir $APP_HOME
WORKDIR $APP_HOME

# Install system dependencies
RUN apt-get update && apt-get install -y gcc

# Copy the requirements file and install dependencies
COPY ./requirements.txt $APP_HOME/requirements.txt
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Copy the rest of your Django project files
COPY ./ $APP_HOME

# Expose the port that the application listens on.
EXPOSE 8000 8001

# Migration
RUN python manage.py migrate

# # Run the application using Daphne.
# CMD daphne config.asgi:application -p 8001 -b 0.0.0.0

# # Run the application using Gunicorn.
# CMD gunicorn 'config.wsgi' --bind=0.0.0.0:8000
