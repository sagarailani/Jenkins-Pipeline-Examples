pipeline {
    agent {
    	docker { 
    		image 'node:6.3'
    	}
    }
    stages {
        stage('build') {
            steps {
                sh 'npm --version'
            }
        }
    }
    post {
    	always {
    		echo "This will always be executed"
    	}
    	success {
    		echo "Build Successful"
    		mail to: 'sagar.ailani@somaiya.edu',
    		     subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
    		     body: "Something is wrong with ${env.BUILD_URL}"
    	}
    	failure {
    		echo "Build Failed"
    	}
    }
}