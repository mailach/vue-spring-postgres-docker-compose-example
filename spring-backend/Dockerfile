FROM maven:3-openjdk-11-slim AS development
RUN mkdir /app
WORKDIR /app
ENTRYPOINT ["mvn","spring-boot:run"]