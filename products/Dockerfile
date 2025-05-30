FROM maven:3.8.5-openjdk-17 AS build
COPY . /app
RUN mvn clean package -DskipTests

FROM openjdk:17.0.1-jdk-slim
COPY --from=build /target/products-0.0.1-SNAPSHOT.jar products.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","products.jar"]
