pipeline {
    agent any

    tools {
        maven 'Maven_3_6_3'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    bat 'mvn clean install -DskipTests'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    bat 'mvn test'
                }
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}