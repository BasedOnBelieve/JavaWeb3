pipeline {
    agent none
    
    stages {
        stage('Checkout')  {
        agent { label 'build'}
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