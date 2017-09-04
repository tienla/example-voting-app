# Using official python runtime base image
FROM python:2.7-slim

# Set the application directory
WORKDIR /vote/app

# Install our requirements.txt
ADD /vote/requirements.txt /app/requirements.txt
RUN pip install -r /vote/requirements.txt

# Copy our code from the current folder to /app inside the container
ADD /vote/. /vote/app

# Make port 80 available for links and/or publish
EXPOSE 80

# Define our command to be run when launching the container
CMD ["gunicorn", "app:app", "-b", "0.0.0.0:80", "--log-file", "-", "--access-logfile", "-", "--workers", "4", "--keep-alive", "0"]
