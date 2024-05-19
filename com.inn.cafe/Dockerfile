# Utiliser une image de base qui contient OpenJDK 17 + Maven
FROM maven:3.8.4-openjdk-17 AS build

# Utiliser /app comme dossier principale de l'application
WORKDIR /app

# Copier les fichiers source code
COPY /target/com.inn.cafe-0.0.1-SNAPSHOT.jar .

# L'application est accessible sur le port 8081
EXPOSE 8081

# Lancer le fichier JAR créé dans ./target
CMD ["java", "-jar", "com.inn.cafe-0.0.1-SNAPSHOT.jar"]
