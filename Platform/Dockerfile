# Etapa 1: Compilar
FROM maven:3.9.4-eclipse-temurin-21 AS builder
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Etapa 2: Ejecutar
FROM eclipse-temurin:21-jdk
WORKDIR /app
COPY --from=builder /app/target/time-table-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
