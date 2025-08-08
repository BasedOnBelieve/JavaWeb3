pipeline {
    agent none
    
    stages {
        stage('Checkout')  {
        agent { label 'build'}
            steps {
                sh '''mvn clean test package'''
            }
        }
        stage('Building App') {
            steps {
                echo 'build complete'
            }
        }
    }    
}       