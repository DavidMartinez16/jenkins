pipeline{
    agent any
    stages {
        stage('Hello Message') {
                steps {
                        echo 'Hi, this is Juan David Martínez'
			
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
