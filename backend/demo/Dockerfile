# Use uma imagem base com Java (ajuste a versão conforme seu projeto)
FROM eclipse-temurin:17-jdk-jammy

# Defina o diretório dentro do container
WORKDIR /app

# Copie o arquivo JAR para dentro do container
COPY target/*.jar app.jar

# Exponha a porta usada pela aplicação (geralmente 8080)
EXPOSE 8080

# Comando para rodar a aplicação
ENTRYPOINT ["java", "-jar", "app.jar"]
