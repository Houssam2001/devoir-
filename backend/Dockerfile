# Dockerfile del backend
FROM gradle:jdk17 AS builder
COPY backend/ /app/backend
WORKDIR /app/backend
RUN gradle build -x test  

FROM openjdk:17
COPY --from=builder /app/backend/build/libs/*.jar app.jar
CMD ["java", "-jar", "app.jar"]