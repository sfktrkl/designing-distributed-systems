# Use the official Python image to create a build artifact
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file to the container image
COPY requirements.txt ./

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the source code to the container image
COPY main.py ./

# Expose port 8080 to the outside world
EXPOSE 8080

# Run the application
CMD ["python", "main.py"]
