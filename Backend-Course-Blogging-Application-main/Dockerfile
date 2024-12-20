FROM openjdk:17-jdk-slim

WORKDIR /app

COPY target/blog-app-apis-0.0.1-SNAPSHOT.jar blog-app-apis.jar

EXPOSE 9092

CMD ["java", "-jar", "blog-app-apis.jar"]
