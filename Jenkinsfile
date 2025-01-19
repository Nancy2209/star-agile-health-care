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
                sh 'docker build -t Nancy2209/healthcare-nancy:v1'
              
            }
        }
         stage('Docker Login'){
            steps{
               withCredentials([string(credentialsId: 'dockerhubpass', variable: 'dockerhubpass')]) {
               sh 'docker login -u Nancy2209 -p ${dockerhubpass}'
               sh 'docker push Nancy2209/healthcare-nancy:v1'
}
            }
        }
}
}