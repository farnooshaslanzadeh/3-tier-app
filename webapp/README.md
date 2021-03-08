# Spring Web Application
# We will build an image for a java application. We will do multistage building. We must first create jar file with maven to use then as out application.

# For the first stage Use maven as base image
# Copy pom.xml
# Execute `mvn dependency:resolve` to install java dependencies
# Copy source code
# Execute `mvn package` to generate jar file. The jar will be under "target/" directory and will be called sentiment-analysis-web-0.0.1-SNAPSHOT.jar
# For the second stage use openjdk:8-jdk-alpine as base image
# Define an environment variabile called SA_LOGIC_API_URL and assign "http://localhost:5000" as its value
# Copy the jar generated in the first stage to "/" dir
# Application will expose standard port that Spring framework uses
# At the end container must launch command "java -jar sentiment-analysis-web-0.0.1-SNAPSHOT.jar --sa.logic.api.url=${SA_LOGIC_API_URL"}
# When you launch container you must set environment variable `SA_LOGIC_API_URL` to the "http://logic:5000" (url of logic app)
# When you build image and launch the container, check application logs. If Spring application launched correctly you must see `Started SentimentAnalysisWebApp` message in the logs.
