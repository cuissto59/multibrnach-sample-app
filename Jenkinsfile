pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
          stage('Test') {
                    steps {
                        echo 'Testing...'
                        // Add a test step that marks the build as unstable
                        script {
                            def testResult = sh(script: 'exit 1', returnStatus: true)
                            if (testResult != 0) {
                                unstable("Marking build as unstable for testing purposes")
                            }
                        }
                    }
                }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
