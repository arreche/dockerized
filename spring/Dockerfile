FROM maven:alpine AS build
COPY pom.xml .
RUN mvn dependency:go-offline -B
COPY ./src ./src
RUN mvn package -DskipTests=true

FROM openjdk:8-jre-alpine
WORKDIR /app
COPY --from=build target/*.jar ./app.jar
ENV JAVA_OPTS="-Xmx200m"
ENTRYPOINT java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar ./app.jar

