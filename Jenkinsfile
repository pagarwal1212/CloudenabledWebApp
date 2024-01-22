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
        stage('install maven') {
            steps {
                sh "sudo apt install maven -y"
            }
        }
        stage('Compile & Package') {
            steps {
                sh "mvn compile"
                sh "mvn package"
            }
        }
        stage('Install Tomcat') {
            steps {
               sh "sudo apt install tomcat9 -y"
            }
        }
        stage('Deploy warfile') {
            steps {
               //sh "sudo cp target/CloudenabledWebApp.war /var/lib/tomcat9/webapps"
                sh "sudo cp target/CloudenabledWebApp.war /opt/tomcat/webapps"
            }
        }
    }
}
