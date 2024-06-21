# Use a base image with Python pre-installed
FROM python:3.12

# Set the working directory inside the container
WORKDIR /app

# Copy requirements.txt and devops directory to /app
COPY requirements.txt /app
COPY devops /app/devops

# Create a virtual environment and activate it
RUN python3 -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# Upgrade pip and install dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Change directory to /app/devops (if needed)
WORKDIR /app/devops

# Set the entry point and default command
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]




