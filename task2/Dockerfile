# Use the latest official Ubuntu image
FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

# Update and install necessary packages
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y python3 python3-pip curl && \
    rm -f /usr/lib/python*/EXTERNALLY-MANAGED && \
    pip3 install --break-system-packages flask

# Set working directory
WORKDIR /app

# Copy Flask app
COPY ./api.py /app/api.py

# Expose Flask port
EXPOSE 5252

# Run the Flask app
CMD ["python3", "api.py"]
