pipeline {
    agent any
    stages{
        stage('git checknout'){
            steps{
                echo "checkout git repo"
                git url:'https://github.com/Nancy2209/star-agile-health-care/', branch: "master"

            }
        }

        stage('code package'){
            steps{
                echo "packageing the code"
                sh 'mvn clean package'
              
            }
        }
         
        stage('Building docker image'){
            steps{
                echo "docker image is build"
                 sh 'docker build -t Nancy2209/healthcare-nancy_project:v1 .'
                 sh 'docker images'
              
            }
        }
        stage('Running Ansible'){
            steps{
                echo "Envoking Ansible on test server"
               ansiblePlaybook become: true, credentialsId: 'ansible', disableHostKeyChecking: true, installation: 'ansible', inventory: '/etc/ansible/hosts', playbook: 'ansible-playbook.yml', vaultTmpPath: ''
              
            }
        }
}
}