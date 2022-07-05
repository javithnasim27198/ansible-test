pipeline{
    agent{
        label 'dotprdwcsjnks01'
    }
    stages{
        stage('checkout-repo'){
            steps{
                sh 'sudo -u jenkins_deploy checkout scm'
            }
        }
    }
}