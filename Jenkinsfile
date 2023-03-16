pipeline {

    agent any
    stages {
        stage('init'){
            steps{
                timeout(1){
                    script{
                        echo "$script_options"
                        sh 'echo this first stage'
                        sh 'docker login -u $docker_password_USR -p $docker_password_PSW'
                        sh "echo ${params.DEPLOY_ENV}"
                        currentBuild.description = "The branch built + $GIT_BRANCH"
                    }
                }
            }
        }
        stage('secondstage'){

            when{
                environment  name:'GIT_BRANCH', value: 'origin/master'
            }
            agent {
                docker {
                    image 'maven'
                }
            }
            steps{
                sh 'mvn --version'
            }
        }
        stage('3stage'){
            steps{
                sh 'echo this 3rd stage'
                 }
        }
    }
    post{
        always{
            cleanWs()
        }
    }
}