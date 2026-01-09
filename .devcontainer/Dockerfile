# Dockerfile for development container

FROM ubuntu:20.04

# Install necessary packages
RUN apt-get update && \
    apt-get install -y \
    build-essential \
    python3 \
    python3-pip \
    git \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /workspaces/reconpoint

# Copy requirements file
COPY web/requirements.txt .

# Install Python dependencies
RUN pip3 install -r requirements.txt

# Expose any ports if necessary
# EXPOSE 8000

# Command to run the application
CMD ["bash"]