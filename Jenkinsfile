pipeline {
    agent any

    stages {
        stage('Terraform Init') {
            steps {
                dir('terraform') {
                    sh 'terraform init'
                }
            }
        }
        stage('Terraform Apply') {
            steps {
                dir('terraform') {
                    sh 'terraform apply -auto-approve'
                }
            }
        }
        stage('Ansible Provision') {
            steps {
                dir('ansible') {
                    sh 'ansible-playbook -i inventory.ini install_web.yml'
                }
            }
        }
    }
}
