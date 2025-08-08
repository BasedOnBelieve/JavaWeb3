pipeline {
    agent none
    
    stages {
        stage('Checkout')  {
        agent { label 'build'}
            steps {
                sh '''
                sudo yum -y install git
                sudo yum -y install maven
                mvn clean test package
                echo 'build complete'
                '''
            }
        }
        stage('Building App') {
            steps {
               mvn sonar:sonar \
                -Dsonar.projectKey=test \
                -Dsonar.host.url=http://54.91.122.194:9000 \
                -Dsonar.login=921e3ed5ffb5007f99ec2acdbdfb4f1bb6151572
            }
        }
    }    
}       