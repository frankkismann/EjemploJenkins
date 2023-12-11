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
                git 'https://github.com/frankkismann/EjemploJenkins.git'
            }
        }
        
        stage('Build') {
            steps {
                // Construir el proyecto con Maven
                sh "${MAVEN_HOME}/bin/mvn clean package"
            }
        }

        stage('Code Analysis') {
            steps {
                // Aquí podrías integrar herramientas como SonarQube para el análisis de código
                sh "${MAVEN_HOME}/bin/mvn sonar:sonar"
            }
        }

        stage('Deploy') {
            steps {
                // Pasos para desplegar tu aplicación
                // Esto dependerá de dónde y cómo quieras desplegar tu aplicación
                echo 'Deploying the application...'
                // sh 'deploy_script.sh'
            }
        }
    }
}
