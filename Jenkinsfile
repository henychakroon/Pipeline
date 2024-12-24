pipeline {
    agent any
    tools{ jdk 'JDK17' }
    environment { JAVA_HOME = '/usr/lib/jvm/java-17-openjdk-amd64/' }
    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'Maven3.9.9') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'Maven3.9.9') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Install Stage') {
            steps {
                withMaven(maven : 'Maven3.9.9') {
                    sh 'mvn install -Dmaven.test.skip=true'
                } 
            } 
        } 
    }
}
