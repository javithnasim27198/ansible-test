pipeline{
    agent{
        label 'dotprdwcsjnks01'
    }
    stages{
        stage('checkout-repo'){
            steps{
                cleanWs()
                sh 'echo $USER'
                checkout scm
                sh 'pwd; ls -lrt;'
            }
        }
    }
    post {
        // Clean after build
        always {
            cleanWs(cleanWhenNotBuilt: false,
                    deleteDirs: true,
                    disableDeferredWipeout: true,
                    notFailBuild: true,
                    patterns: [[pattern: '.gitignore', type: 'INCLUDE'],
                               [pattern: '.propsfile', type: 'EXCLUDE']])
        }
    }
}