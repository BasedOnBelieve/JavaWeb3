pipeline {
    agent {label 'build'}
    /*tools {
        jdk 'java-21'
        maven 'maven'
    }*/
    stages {
        stage('Checkout')  {
            steps {
                echo 'Cloning repo'
            }
        }
        stage('Building App') {
            steps {
                sh'''
                mvn clean package
                '''
            }
        }
        /*stage('testing app') {
            steps {
                sh'''
                sonar-scanner \
                -Dsonar.projectKey=test \
                -Dsonar.sources=. \
                -Dsonar.host.url=http://34.228.160.206:9000 \
                -Dsonar.login=36e47618d8d1cd8c2c907d4834c64b788bf712df
                '''
            }
        } */   
        stage('deploy') {
            steps {
                sh 'mvn deploy'
            }   
        }
    }
}