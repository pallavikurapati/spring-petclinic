pipeline {
    agent{label 'JDK17'}
    stages { 
        stage('source code') {
            steps {
                git branch: 'main', url: 'https://github.com/pallavikurapati/spring-petclinic.git'
            }
        }
        stage ('build the code') {
            steps {
                sh 'mvn compile'
            }
        }
        stage ('reporting') {
            steps {
                junit '**/surefire-report/*.xml'
            }
        }
        stage ('test results') {
            steps {
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false

            }
        }
    }
}