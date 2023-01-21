pipeline {

    agent {
            docker {
                image 'maven'
            }
        }
    agent any
    stages {

        stage('init'){
            steps{
                sh 'echo this first stage'
            }
        }
        stage('secondstage'){
            steps{
                sh 'mvn --version'
                sh 'echo 2nd stage'
            }
        }
        stage('3stage'){
            steps{
                sh 'echo this 3rd stage'
            }
        }
    }
}
