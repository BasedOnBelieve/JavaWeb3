pipeline {
    agent {label 'build'}

    stages {
        stage( Build) {
            steps {
                sh 'mvn package'
            }
        }
        stage( Test ) {
            steps {
                sh 'mvn test'
           }
        }
        stage( Delopy ) {
            steps {
                sh 'mvn deploy'
            }
        }
    }   
}