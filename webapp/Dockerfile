FROM maven:3.6.3-openjdk-16 as target
COPY pom.xml .
RUN mvn dependency:go-offline
COPY ./src /usr/src/app
RUN ./target/webapp-sentiment-analysis-web-0.0.1-SNAPSHOT.jar

FROM openjdk:8-jdk-alpine
ENV SA_LOGIC_API_URL=http://localhost:5000
COPY --from=target /usr/src/webapp/target/sentiment-analysis-web-0.0.1-SNAPSHOT.jar
RUN java -jar sentiment-analysis-web-0.0.1-SNAPSHOT.jar --sa.logic.api.url=${SA_LOGIC_API_URL"}


