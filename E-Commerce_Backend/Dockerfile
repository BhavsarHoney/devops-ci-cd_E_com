FROM openjdk:28-ea-oraclelinux9

WORKDIR /app

COPY  .mvn/ .mvn    
COPY  mvnw .
COPY  pom.xml . 

RUN ./mvnw dependency:go-offline

COPY src ./src

RUN ./mvnw package -DskipTests

RUN mv target/*.jar app.jar

CMD ["java", "-jar", "app.jar"]