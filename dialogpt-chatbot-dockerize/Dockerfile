# Download Python from DockerHub
FROM python:3.8.10

# Set working directory in the Docker container
WORKDIR /code

# Copy the requirements file to the working directory
COPY requirements.txt .

# Install the dependencies from the requirements document
RUN pip install -r requirements.txt

# Copy the Flask app code to the working directory
COPY src/ .

# Expose ports
EXPOSE 8080

# Call application
CMD ["python3", "app.py", "serve"]