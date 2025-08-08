pipeline {
    agent none
    
    stages {
        stage('Checkout')  {
        agent { label 'build'}
            steps {
                sh '''
                sudo yum -y install maven
                mvn clean test package
                echo 'build complete'
                '''
            }
        }
        stage('Building App') {
            steps {
                echo 'build complete'
            }
        }
    }    
}       