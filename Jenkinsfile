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
                script{
                    def scannerHome = tool 'SonarScanner';
                    withSonarQubeEnv('SonarOwn') {
                    sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}