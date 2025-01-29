pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Pratik-Pardeshi/a.git'
            }
        }

        stage('Transfer Files to Ansible') {
            steps {
                sh 'scp index.html playbook.yml ansible_user@172.31.34.144:/home/ansible/deployment/'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh 'ssh ansible_user@172.31.34.144 "ansible-playbook /home/ansible/deployment/playbook.yml"'
            }
        }
    }
}
