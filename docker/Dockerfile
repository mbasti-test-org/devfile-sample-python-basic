FROM registry.access.redhat.com/ubi9/python-39:latest

# By default, listen on port 8081
EXPOSE 8081/tcp
ENV FLASK_PORT=8081

LABEL description=yolo
LABEL io_k8s_description=yolo_k8s
LABEL io_k8s_display_name=yolo_display_name
LABEL io_openshift_tags=yolo_tag
LABEL summary=yolo_summary

# Set the working directory in the container
WORKDIR /projects

# Copy the dependencies file to the working directory
COPY requirements.txt .

# Install any dependencies
RUN pip install -r requirements.txt

# Copy the content of the local src directory to the working directory
COPY . .

# Specify the command to run on container start
CMD [ "python", "./app.py" ]
