FROM maven:3.6.0-jdk-11-slim
RUN mkdir -p /usr/src/app
COPY pom.xml /usr/src/app
WORKDIR /usr/src/app 
RUN mvn dependency:resolve
COPY src /usr/src/app/src
RUN ls /usr/src/app 
RUN mvn -f pom.xml clean package
        

FROM openjdk:8-jdk-alpine
ENV SA_LOGIC_API_URL=http://localhost:5000
COPY --from=0 /usr/src/app/target/sentiment-analysis-web-0.0.1-SNAPSHOT.jar /usr/src/app
CMD [ "java","-jar","/usr/src/app/sentiment-analysis-web-0.0.1-SNAPSHOT.jar","--sa.logic.api.url=${SA_LOGIC_API_URL}" ] 



