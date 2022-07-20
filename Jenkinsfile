pipeline{
    agent any
    stages {
        stage('Hello Message') {
                steps {
                        echo 'Hi, this is David Martínez'
			
                }
        }
	stage('Verification Step'){
		steps {
			input('Do you want to proceed?')
        }
	    }
        stage('Branch Verification') {
                when {
                        not {
                                branch "master"
                        }
                }
                steps {
			echo "Hello from the main"
                        }
        }
	stage('Email Notification') {
		steps {
			emailext attachLog: true, body: '$DEFAULT_CONTENT', subject: 'This is test email - $DEFAULT_SUBJECT', to: 'pruebaingresoicare@gmail.com'
		}
        }
        stage('Parallel Step') {
                parallel {
                        stage('Unit Test') {
                                steps{
                                        echo "Running the unit test..."
                                }
                        }
                        stage('Integration test') {
				steps {
					echo 'Running the integration test..'
				}
                               
			}  }
        }
    }
}
