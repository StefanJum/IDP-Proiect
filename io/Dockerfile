# Use an official Python runtime as a parent image
FROM python:3.8.3-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

RUN apt-get update \
    && apt-get -y install libpq-dev gcc \
        && pip install psycopg2

# Install any needed dependencies specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 8080 available to the world outside this container
EXPOSE 8080

# Define environment variable
ENV NAME World

# Run io_service.py when the container launches
CMD ["python", "io_service.py"]
