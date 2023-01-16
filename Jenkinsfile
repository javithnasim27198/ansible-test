pipeline{
    agent{
        label 'dotprdwcsjnks01'
    }
    options { skipDefaultCheckout() }
    stages{
        stage('checkout-repo'){
            steps{
                cleanWs()
                sh 'echo $USER'
                //checkout scm
                sh '''
                if [[ ${RP} == ~ ['!@#$%^&*()-+'] ]]
				  then
				    echo "Eneterd RP name contains special character, Please eneter valid RP name!!!" 
                    exit 1
				fi 
                 '''
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
