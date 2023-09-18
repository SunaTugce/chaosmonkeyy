FROM python:3.8-slim-buster

# Copy the local package files to the container's workspace.
ADD . /creativityday
RUN apt-get update
COPY requirements.txt requirements.txt
ENV PYTHONPATH "${PYTHONPATH}:/creativityday/creativityday_api_handler/"

# execute
CMD ["python3", "creativityday/main.py"]
