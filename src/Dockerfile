FROM python:3-slim-buster

# Install dos2unix utility
RUN apt-get update && apt-get install -y dos2unix

WORKDIR /usr/src/app

# Copy requirements and entry point script
COPY requirements.txt ./
COPY entry_point.sh /usr/local/bin/

# Install Python dependencies
RUN pip install -r requirements.txt

# Copy the rest of the application code
COPY . .

# Change line endings of the entry point script to Unix format
RUN dos2unix /usr/local/bin/entry_point.sh

# Make the entry point script executable
RUN chmod +x /usr/local/bin/entry_point.sh

# Set the entry point for the container
CMD [ "/usr/local/bin/entry_point.sh" ]
