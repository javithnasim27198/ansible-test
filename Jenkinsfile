pipeline{
    agent{
        label 'dotprdwcsjnks01'
    }
    stages{
        stage('checkout-repo'){
            steps{
                sh 'sudo su jenkins_deploy'
                sh 'echo $USER'
                checkout scm
            }
        }
    }
}