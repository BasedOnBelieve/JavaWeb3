pipeline {
    agent {label 'build'}
    tools {
        jdk 'java17'
    }
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
    }
}