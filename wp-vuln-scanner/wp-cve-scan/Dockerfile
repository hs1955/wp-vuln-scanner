# Use an official Python image
FROM python:3.14.0a7-slim

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the project files into the container
COPY . .

# Install dependencies
# COPY requirements.txt ./
# RUN pip install --no-cache-dir -r requirements.txt

RUN --mount=type=bind,source=requirements.txt,target=/tmp/requirements.txt \
    pip install --requirement /tmp/requirements.txt

# Define environment variable (optional)
# ENV NAME Debug

# Run app.py when the container launches
CMD ["python", "./main.py"]
