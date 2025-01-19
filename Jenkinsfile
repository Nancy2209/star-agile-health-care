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
                sh 'docker build -t healthcare-nancy .'
              
            }
        }
}
}