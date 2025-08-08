pipeline {
    agent none
    
environment {
    Sonar_Key = 'test'
    Sonar_Host = 'http://54.91.122.194:9000'
    Sonar_token = '921e3ed5ffb5007f99ec2acdbdfb4f1bb6151572'
}

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
        agent { label 'build'}
            steps {
               sh '''mvn sonar:sonar \
                -Dsonar.projectKey=${Sonar_Key} \
                -Dsonar.host.url=${Sonar_Host} \
                -Dsonar.login=${Sonar_token}
                '''
            }
        }
    }    
}       