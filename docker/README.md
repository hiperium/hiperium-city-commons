### Native Image Builder.

* **Author**: [Andres Solorzano](https://www.linkedin.com/in/aosolorzano/).
* **Level**: 300 - Senior.
* **Technologies**: Docker.

### What is it?
This is a simple docker project that builds a base image which contains the native-image tool from GraalVM for Java 21. 
This image is used to build native images from Java applications in the Hiperium City project.

### System requirements
All you need to build this project is Docker.

### How to use it?
To build the image, you can run the following command:
```bash
docker build -t hiperium/city-builder:1.0.0 .
docker build -t hiperium/city-lambda:1.0.0 .
```

### How to test it using an interactive terminal?
To enter to running container, you must execute the following command to initialize an interactive terminal:
```bash
docker run -it --rm --entrypoint /bin/bash hiperium/city-builder:1.0.0
docker run -it --rm --entrypoint /bin/bash hiperium/city-lambda:1.0.0
```
There, you can execute the following command to check the native-image version:
```bash
mvn --version
java -version
native-image --version
```

After validations, you can exit the container by typing `exit`.

### How to extend it?
You can extend this image to include in your `Dockerfile` and build a native image from it.

### How to deploy it to Docker Hub?
To deploy the image to Docker Hub, you can run the following commands:
```bash
docker login
docker push hiperium/city-builder:1.0.0

docker tag  hiperium/city-builder:1.0.0 hiperium/city-builder:latest
docker push hiperium/city-builder:latest
```

```bash
docker login
docker push hiperium/city-lambda:1.0.0

docker tag  hiperium/city-lambda:1.0.0 hiperium/city-lambda:latest
docker push hiperium/city-lambda:latest
```
