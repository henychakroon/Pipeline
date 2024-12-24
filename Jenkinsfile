pipeline {
    agent any
    tools {
        jdk 'JDK17' // Assurez-vous que JDK17 est configuré dans Jenkins
        maven 'Maven3.9.9' // Assurez-vous que Maven3.9.9 est configuré dans Jenkins
    }
    environment { 
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17' // Chemin Java pour Windows
    }
    stages {
        stage('Compile Stage') {
            steps {
                withMaven(maven: 'Maven3.9.9') {
                    bat 'mvn clean compile'
                }
            }
        }
        stage('Testing Stage') {
            steps {
                withMaven(maven: 'Maven3.9.9') {
                    bat 'mvn test'
                }
            }
        }
        stage('Install Stage') {
            steps {
                withMaven(maven: 'Maven3.9.9') {
                    bat 'mvn install -Dmaven.test.skip=true'
                }
            }
        }
    }
}
