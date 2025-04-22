# Understanding Docker: Deploying a Python “Hello World” Application

## Introduction
Docker simplifies software deployment and management by packaging applications into standardised, portable units called containers. Containers include all necessary dependencies, ensuring consistency across different environments. As a result, Docker resolves the common problem of "the code works on my machine but doesn't run on yours," by creating an identical environment that runs your code consistently on any computer.

## What is Docker?
Docker is a tool that enables developers to package, ship, and run applications efficiently, isolated from the host system. It functions similarly to a lightweight virtual machine but operates faster and uses resources more efficiently.

## Why Use Docker?
- **Consistency**: Ensures applications run identically in all environments.
- **Portability**: Applications can be easily moved between development, testing, and production.
- **Isolation**: Containers run independently, avoiding interference with each other.
- **Scalability**: Additional containers can be quickly deployed as needed.

## Docker "Hello World" Example with Python
Below is an example of creating a Docker container that runs a Python "Hello World" application.

### Step 1: Create the Hello World Python Script
Create a new file named `app.py`:
```python
# app.py
print("Hello, Docker World!")
```

### Step 2: Create the Dockerfile
A Dockerfile defines the application's environment:
```dockerfile
# Dockerfile
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Copy Python script into container
COPY app.py .

# Command to run the script
CMD ["python", "app.py"]
```

### Step 3: Build the Docker Image
Execute the following command to build the Docker image named `hello-docker`:
```shell
docker build -t hello-docker .
```

### Step 4: Run the Docker Container
Run the container using this command:
```shell
docker run hello-docker
```

The following output should appear:
```
Hello, Docker World!
```

Here it is, you can now deploy your Hello World program to be run on any other computer with Docker. If you would like to know more how you can apply docker on your project, Research IT provides [Introduction to Docker](http://app.manchester.ac.uk/RDOCKER) course and the course notes in detail can be found [here](https://uomresearchit.github.io/docker-introduction/). You can find the docker course and any other courses offered by us [here](https://www.staffnet.manchester.ac.uk/talent-development/learning-pathways/professional-and-technical-development/digital-skills/research-computing/).