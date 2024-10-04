FROM ubuntu:20.04

# Set environment variable to avoid any user interaction in installation
ENV DEBIAN_FRONTEND=noninteractive

# Set the working directory
WORKDIR /app

# Copy the necessary files
COPY requirements.txt /app
COPY devops /app/devops

# Install Python and dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip3 install --no-cache-dir -r requirements.txt

# Expose the port on which the app will run
EXPOSE 8000

# Set the entry point for the Django app
ENTRYPOINT ["python3", "/app/devops/manage.py"]

# Run the Django development server
CMD ["runserver", "0.0.0.0:8000"]





