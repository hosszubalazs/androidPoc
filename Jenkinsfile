pipeline {
    agent any
    environment {
        GIT_COMMITTER_NAME = "hosszubalazs"
        GIT_COMMITTER_EMAIL = "balazs.hosszu@gmail.com"
    }
    stages {
        stage("Version echo") {
            steps {
                sh 'pwd'
                sh 'ls -halt'
                sh 'gradle --version'
                sh './gradlew --version'
            }
        }
        stage("build") {
            steps {
                sh './gradlew build'
            }
        }
        stage('SonarQube analysis') {
            steps {
                sh './gradlew sonarqube'
            }
        }
    }
}