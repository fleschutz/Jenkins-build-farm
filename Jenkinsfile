pipeline {
    agent any  // may run on any Jenkins node
    stages {
        stage ('Build') {
            steps {
                echo "Hello World! Let's build something great..."
                script {
                    currentBuild.displayName = "My sample Pipeline"
                    currentBuild.description = "This is my first sample Pipeline."
                }
            }
        }
        stage ('Test') {
            steps {
                echo "Our build needs to be tested..."
            }
        }
        stage ('Zip') {
            steps {
                sh 'zip -r sample-build.zip .'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'sample-build.zip', fingerprint: true, onlyIfSuccessful: true
        }
    }
}
