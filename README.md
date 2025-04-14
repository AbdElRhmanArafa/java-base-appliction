# Spring Boot Based Java Web Application

This is a simple Spring Boot-based Java application that can be built using Maven. Spring Boot dependencies are managed using the `pom.xml` file located in the root directory of the repository.

This application follows the MVC architecture, where the controller returns a page with title and message attributes to the view.

## Execute the Application Locally and Access It Using Your Browser

Clone the repository and navigate to the directory:

```bash
git clone https://github.com/iam-veeramalla/Jenkins-Zero-To-Hero/java-maven-sonar-argocd-helm-k8s/spring-boot-app
cd java-maven-sonar-argocd-helm-k8s/spring-boot-app
```

Build the Maven project to generate the artifacts:

```bash
mvn clean package
```

The above Maven command stores the artifacts in the `target` directory. You can either execute the artifact on your local machine or run it as a Docker container.

**Note:** To avoid issues with local setup, Java versions, and other dependencies, it is recommended to use the Docker approach.

### Execute Locally (Java 11 Required) and Access the Application on `http://localhost:8080`

```bash
java -jar target/spring-boot-web.jar
```

### The Docker Way

Build the Docker image:

```bash
docker build -t ultimate-cicd-pipeline:v1 .
```

Run the Docker container:

```bash
docker run -d -p 8010:8080 -t ultimate-cicd-pipeline:v1
```

Hurray! Access the application on `http://<ip-address>:8010`.

## Next Steps

### Configure a SonarQube Server Locally

#### System Requirements:
- **Java 17+** (Oracle JDK, OpenJDK, or AdoptOpenJDK)
- **Hardware Recommendations:**
   - Minimum 2 GB RAM
   - 2 CPU cores

Install dependencies and set up SonarQube:

```bash
sudo apt update && sudo apt install unzip -y
adduser sonarqube
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-10.4.1.88267.zip
unzip sonarqube-10.4.1.88267.zip -d /opt
chown -R sonarqube:sonarqube /opt/sonarqube
chmod -R 775 /opt/sonarqube
cd /opt/sonarqube/bin/linux-x86-64
./sonar.sh start
```

Hurray! Now you can access the SonarQube Server on `http://<ip-address>:9000`.

## References

- This application is a clone of [iam-veeramalla/Jenkins-Zero-To-Hero](https://github.com/iam-veeramalla/Jenkins-Zero-To-Hero).
