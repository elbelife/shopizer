FROM adoptopenjdk/openjdk11-openj9:alpine
RUN mkdir /opt/app
RUN mkdir /files
COPY target/shopizer.jar /opt/app
COPY .mvn/ .mvn
COPY ./mvnw dependency:go-offline
COPY src ./src
RUN ./mvnw package -DskipTests
#COPY SALESMANAGER.h2.db /
COPY ./files /files
CMD ["java", "-jar", "/opt/app/shopizer.jar"]