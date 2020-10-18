FROM java:8-jdk-alpine
COPY ./build/libs/kcw.war /usr/app/
WORKDIR /usr/app
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "kcw.war"]