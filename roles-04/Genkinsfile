pipeline {
    agent {label 'deploy'}

    stages {
       /* stage('Clone Code') {
       //     agent { label 'build' }
            steps {
                git branch: 'master', url: 'https://github.com/BasedOnBelieve/ecomm-3.git'
            }
        }*/

        stage('Run Ansible Playbook') {
            agent { label 'ansible' }
                steps {
                git branch: 'main', url: 'https://github.com/BasedOnBelieve/ansible.git'
                
                ansiblePlaybook(
                    credentialsId: 'bc12a530-cdb9-438a-b6c9-03920e67ab04', 
                installation: 'ansible', inventory: '/home/ec2-user/workspace/others/hosts.ini', playbook: 
                '/home/ec2-user/workspace/ansible-pipe/03-role-playbook.yml'
                )
            }
        }
    }
}