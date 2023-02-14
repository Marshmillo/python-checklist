pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('SCM') {
            steps {
                checkout scm
            }
        }
        stage('SonarQube Analysis') {
            steps {
                def scannerHome = tool 'SonarScanner';
                withSonarQubeEnv() {
                sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}