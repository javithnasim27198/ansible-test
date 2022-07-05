pipeline{
    agent{
        label 'dotprdwcsjnks01'
    }
    stages{
        stage('checkout-repo'){
            sh "sudo -u jenkins_deploy checkout scm"
        }
    }
}