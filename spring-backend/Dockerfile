FROM maven:3-openjdk-11-slim as development
RUN mkdir /app
WORKDIR /app
ENTRYPOINT ["mvn","spring-boot:run"]



FROM development as production
COPY . .
RUN mvn package
ENTRYPOINT ["java", "-jar", "/app/target/spring-boot-0.0.1-SNAPSHOT.jar"]
