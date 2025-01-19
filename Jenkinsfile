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

         stage('Build docker image'){
            steps{
                script{
                     echo "docker image is build"
                    sh 'docker build -t Nancy2209/star-agile-banking-finance_project:v1 .'
                    sh 'docker images'
                }
            }
        }
         
        stage('Building docker image'){
            steps{
                echo "docker image is build"
                 sh 'docker build -t Nancy2209/healthcare-nancy_project:v1 .'
                 sh 'docker images'
              
            }
        }
         stage('Docker Login'){
            steps{
               sh 'docker push Nancy2209/healthcare-nancy:v1'
              }
            }
        
}
}