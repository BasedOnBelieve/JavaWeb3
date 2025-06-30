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
    }
}