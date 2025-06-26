pipeline {
    agent { label 'build-agent'}
    tools {
        maven 'maven'
    }
    stages {
        stage('veryfying maven') {
            steps { sh 'mvn -version'
            }
        }
        stage('build') {
            steps {
                echo 'building the application!'
                sh''' 
                mvn clean package
                '''
            }
        }
        stage('test') {
            steps {
                echo 'testing the application!'
                sh 'mvn test'
            }
        }
        stage('deploy') {
            steps {
                echo 'deploying the application!'
                sh 'mvn deploy'
            }
        }
    }
}
