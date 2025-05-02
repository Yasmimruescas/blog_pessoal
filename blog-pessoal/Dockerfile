FROM openjdk:17.0.1-jdk-oracle AS build

WORKDIR /app

COPY . .

RUN chmod +x ./mvnw
RUN ./mvnw clean package -DskipTests

FROM openjdk:17.0.1-jdk-oracle

WORKDIR /app

COPY --from=build /app/target/*.jar app.jar

ENTRYPOINT ["java", "-jar", "app.jar"]
