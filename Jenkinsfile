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
        stage('testing app') {
            steps {
                sh'''
                sonar-scanner \
                -Dsonar.projectKey=test \
                -Dsonar.sources=. \
                -Dsonar.host.url=http://54.159.18.142:9000 \
                -Dsonar.login=d5263dd9f57793acfcc17a72fd52732a370dc11b
                '''
            }
        }    
    }
}