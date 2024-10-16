# backend/Dockerfile

# Use an official Python runtime as a base image
FROM python:3.12

# Set the working directory in the container
WORKDIR /backend

# Copy the requirements file into the container
COPY requirements.txt /backend/

# Install any dependencies specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . /backend/

# Set environment variable for Django settings
ENV DJANGO_SETTINGS_MODULE=backend.settings

# Expose the port the app runs on
EXPOSE 8000

# Define the default command to run the Django app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]