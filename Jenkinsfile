pipeline {

        stages {
        stage('init'){
            agent any
            steps{
                sh 'echo this first stage'
            }
        }
        stage('secondstage'){
            agent { label 'master' }
            steps{
                sh 'echo 2nd stage'
            }
        }
        stage('3stage'){
            agent any
            steps{
                sh 'echo this 3rd stage'
            }
        }
    }
}
