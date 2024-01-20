pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
             //  bat "rmdir  /s /q TicketBookingServiceJunitTesting"
                git "https://github.com/pagarwal1212/CloudenabledWebApp.git"
               sh "mvn clean"
            }
        }
        stage('install') {
            steps {
                sh "sudo apt install maven -y"
            }
        }
        stage('Test & Compile') {
            steps {
                sh "mvn Compile"
            }
        }
        stage('package') {
            steps {
                sh "mvn package"
            }
        }
    }
}
