pipeline {
    agent any

    tools {
        jdk 'Java 17'
        maven 'Maven 3.9.6'
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/OoONANCY/spring-petclinic.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t spring-petclinic .'
            }
        }
    }
}
