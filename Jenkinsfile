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
                if [[ ${RP} =~ ['!@#$%^&*()+'] ]]
	          then
		    echo "Enter valid RP name, It should not contain any special characters like !@#$%^&*()+" 
                    exit 1
		elif [[ ${RP} == '']]
		  then
		    echo "Enter valid RP name, It should not be empty"
		else
		  echo "restore point name : ${RP}"
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
