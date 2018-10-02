FROM maven:latest as builder
RUN git clone -b master --single-branch https://github.com/haroonzone/hello-dropwizard.git /temp
WORKDIR /temp
RUN mvn package

FROM openjdk:8-jdk-alpine
COPY --from=builder /temp      /hello-dropwizard
WORKDIR /hello-dropwizard
RUN adduser -D -u 1001 java && chown -R java /hello-dropwizard
USER java
ENTRYPOINT ["/usr/bin/java","-jar","target/hello-dropwizard-1.0-SNAPSHOT.jar","server","example.yaml"]

