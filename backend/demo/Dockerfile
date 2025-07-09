# Stage 1: Build do JAR usando imagem Maven com JDK 17
FROM maven:3.8.7-openjdk-17 AS build
WORKDIR /app

# Copia os arquivos do pom.xml e da pasta src para o container
COPY pom.xml .
COPY src ./src

# Roda o build do Maven pulando os testes (para agilizar)
RUN mvn clean package -DskipTests

# Stage 2: Imagem final para rodar a aplicação com JRE 17 leve
FROM openjdk:17-jdk-slim
WORKDIR /app

# Copia o JAR compilado da etapa anterior para esta imagem final
COPY --from=build /app/target/demo-0.0.1-SNAPSHOT.jar app.jar

# Define o comando para iniciar a aplicação
ENTRYPOINT ["java", "-jar", "/app/app.jar"]

# Expõe a porta 8080 (ajuste se usar outra)
EXPOSE 8080
