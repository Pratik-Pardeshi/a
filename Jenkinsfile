pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'git@github.com:your-repo.git'
            }
        }

        stage('Transfer Files to Ansible') {
            steps {
                sh 'scp index.html playbook.yml ansible_user@ansible_server:/home/ansible/deployment/'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh 'ssh ansible_user@ansible_server "ansible-playbook /home/ansible/deployment/playbook.yml"'
            }
        }
    }
}
