# Use a Python base image
FROM python:3.8-slim

# Install system dependencies
RUN apt-get update && \
    apt-get install -y build-essential libpq-dev

# Set the working directory
WORKDIR /app

# Copy your script into the Docker image
COPY script.sh /usr/local/bin/script.sh


# Copy the Python application files
COPY requirements.txt /app/
COPY . /app/

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Set environment variables for your Python application
ENV DATABASE_NAME='HRMS'
# ... (other environment variables)

# Expose the port that Django will run on
EXPOSE 8000

# Command to run your script and start the Python application
CMD ["/usr/local/bin/script.sh"]
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
