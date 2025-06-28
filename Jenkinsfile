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
        stage('Deploy') {
            steps {
                sh 'mvn deploy'
            }
        }
        stage('deploy to web') {
            steps {
                sh '''
                wget --user admin --password admin123 http://3.93.200.202:8081/repository/maven-releases/com/web/cal/WebAppCal/0.0.7/WebAppCal-0.0.7.war
                mv WebAppCal-0.0.7.war apache-tomcat-9.0.106/webapps/
                '''
            }
        }
    }   
}