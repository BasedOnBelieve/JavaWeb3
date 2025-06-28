pipeline {
    agent {label 'build'}

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps { 
                sh 'mvn sonar:sonar \
                    -Dsonar.projectKey=test \
                    -Dsonar.host.url=http://100.26.134.120:9000 \
                    -Dsonar.login=20de32036f4342ea72804edd262706287ead0377'
           }
        }
        /*stage('Deploy') {
            steps {
                sh 'mvn deploy'
            }
        }*/
    }   
}