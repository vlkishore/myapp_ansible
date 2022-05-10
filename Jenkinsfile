pipeline {
    agent any

    stages {
        stage('Ansible SCM checkout') {
            steps {
                git credentialsId: 'f5b5f20b-b48a-439b-93e0-aafd5e6da0c7', url: 'https://github.com/vlkishore/myapp_ansible'
            }
        }
        stage('Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'private-key', disableHostKeyChecking: true, installation: 'ansible', inventory: 'dev.inv', playbook: 'apache.yml'
            }
        }
    }
}