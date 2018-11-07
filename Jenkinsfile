pipeline {
    agent any

    stages {
        stage ('Clone'){
            steps {
                echo 'Clone repo'
                sh '''
                 git clone https://github.com/tiana480/Jenkins-ansible.git
                ls 
                '''
            }
        }
        stage ('Deploy to Test'){
            steps {
                echo 'Deploy to test enviornment'
                sh '''
                ansible-playbook Playbooks/winplay2.yml -i inventory/ec2.py
                '''
            }
        }
        post{
            cleanup {
                sh 'rm -r jenkins-ansible.git'
            }
        }
    }
}







