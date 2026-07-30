FROM ubuntu:latest

# Install Python and Flask dependencies
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y python3 python3-pip

# Remove the EXTERNALLY-MANAGED file to allow pip installations
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Install Flask using pip3
RUN pip3 install flask

# Create the application directory
WORKDIR /app

# Copy the API script into the container
COPY api.py /app/api.py

# Expose the port that the Flask app will run on
EXPOSE 5252

# Set the command to run the Flask application
CMD ["python3", "api.py"]
