# Use an official Pyhton 3 as a parent image
FROM python:3-slim

# Set the woking directory to /app 
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Make port 8000 available to the world outside this container
EXPOSE 8000

# Define environment variable 
ENV WORLD Docker
ENV STUDENT_ID "6610110341"
ENV NAME "Suthinan Rongphon"

# Run app.py when the container launches
CMD ["python", "app.py"]