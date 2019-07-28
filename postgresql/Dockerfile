# Pull base image
FROM python:3.7-slim

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set working directory
WORKDIR /code

# Install dependencies
# - COPY the Pipfile and Pipfile.lock which contain the dependencies
# - RUN
#   1 install pipenv
#   2 use pipenv to install dependencies in Pipfile.lock
#      --system tells pipenv to not look for a virtual environment since in Docker
COPY Pipfile Pipfile.lock /code/
RUN pip install pipenv && pipenv install --system

# Copy project
# - copy over the rest of our local code
COPY . /code/
