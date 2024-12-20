# Stage 1: Build the application using a Maven image 

FROM maven:3.8.5-openjdk-17-slim AS build


WORKDIR /app


COPY pom.xml .


RUN mvn dependency:go-offline


COPY src /app/src


RUN mvn clean package -DskipTests

#Stage 2
FROM openjdk:17-jdk-slim


WORKDIR /app


RUN useradd -m appuser
USER appuser


COPY --from=build /app/target/blog-app-apis-0.0.1-SNAPSHOT.jar blog-app-apis.jar


EXPOSE 9092


ENV JAVA_OPTS="-Xms512m -Xmx1g"

CMD ["java", "$JAVA_OPTS", "-jar", "blog-app-apis.jar"]
