pipeline{
    agent{
        label 'dotprdwcsjnks01'
    }
    stages{
        stage('checkout-repo'){
            steps{
                sh 'su - jenkins_deploy; echo $USER'
                sh 'echo $USER'
                checkout scm
            }
        }
    }
}