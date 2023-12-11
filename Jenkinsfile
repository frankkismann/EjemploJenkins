pipeline {
    agent any

    environment {
        // Define las variables de entorno si es necesario
        MAVEN_HOME = "C:/Users/frank/Downloads/apache-maven-3.9.6"
    }

    stages {
        stage('Checkout') {
            steps {
                // Obtener el código fuente de GitHub
                bat 'git clone https://github.com/frankkismann/EjemploJenkins.git'
            }
        }
        
        stage('Build') {
            steps {
                // Construir el proyecto con Maven
                bat "\"${MAVEN_HOME}\\bin\\mvn\" clean package"
            }
        }

        stage('Code Analysis') {
            steps {
                // Aquí podrías integrar herramientas como SonarQube para el análisis de código
                bat "\"${MAVEN_HOME}\\bin\\mvn\" sonar:sonar"
            }
        }

        stage('Deploy') {
            steps {
                // Pasos para desplegar tu aplicación
                // Esto dependerá de dónde y cómo quieras desplegar tu aplicación
                echo 'Deploying the application...'
                // Puedes ejecutar un script de despliegue de Windows aquí
                // bat 'deploy_script.bat'
            }
        }
    }
}
