FROM maven:3-openjdk-11-slim as development
RUN mkdir /app
WORKDIR /app
ENTRYPOINT ["mvn","spring-boot:run"]


FROM development as build
COPY . .
CMD ["mvn","package"]

FROM development as production
COPY --from=build /app/target/spring-boot-0.0.1-SNAPSHOT.jar .
ENTRYPOINT ["java", "-jar", "spring-boot-0.0.1-SNAPSHOT.jar"]
