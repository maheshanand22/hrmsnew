\# Use a Python base image
FROM python:3.8-slim

# Install system dependencies
RUN apt-get update && \
    apt-get install -y build-essential libpq-dev

# Set the working directory
WORKDIR /app

# Copy your script into the Docker image
COPY /path/to/your/script.sh /usr/local/bin/script.sh

# Copy the Python application files
COPY requirements.txt /app/
COPY . /app/

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Set environment variables for your Python application
ENV DATABASE_NAME='HRMS'
ENV DATABASE_USER='devuser'
ENV DATABASE_PASSWORD='Devuser#123'
ENV DATABASE_HOST='216.48.191.120'
ENV EMAIL_HOST_USER='nihar@marolix.com'
ENV EMAIL_HOST_PASSWORD='C6050425D5DE4D829132626A42EF01D034D0'
ENV SECRET_KEY='django-insecure-#cedo6k@mkcoy%!r2$wy$8h-(9x&ev+v%tvx+-k-o%)2jt$fb^'
ENV EMAIL_BACKEND='django.core.mail.backends.smtp.EmailBackend'
ENV EMAIL_HOST='smtp.elasticemail.com'
ENV EMAIL_PORT=25
ENV EMAIL_USE_TLS=True
ENV EMAIL_USE_SSL=False
ENV DEFAULT_FROM_EMAIL='mailto:nihar@marolix.com'

# Expose the port that Django will run on
EXPOSE 8000

# Command to run your script and start the Python application
CMD ["/usr/local/bin/script.sh"]
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
