# Use an official debian sid as a parent image
FROM debian:sid
# add PSU repository
RUN echo "deb http://mirrors.psu.ac.th/debian/ sid " \
"main contrib non-free" > /etc/apt/sources.list
# Update and Upgrade system then install python3
RUN apt update && apt upgrade -y
RUN apt install -y python3 python3-dev python3-pip python3-venv
# Set the working directory to /app
WORKDIR /app
# Copy the current directory contents into the container at /app
COPY . /app
# Install any needed packages specified in requirements.txt
RUN python3 -m venv /venv
RUN /venv/bin/pip install --trusted-host pypi.python.org -r requirements.txt
# Make port 8000 available to the world outside this container
EXPOSE 8000
# Define environment variable, change it to your infomation
ENV WORLD Docker
ENV STUDENTID "STUDENT_ID"
ENV NAME "STUDENT NAME"
CMD ["/venv/bin/python3", "app.py"]