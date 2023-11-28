pipeline {
    agent any  // may run on any Jenkins node
    stages {
        stage ('Build') {
            steps {
                echo "Hello World! Let's build something great ..."
            }
        }
        stage ('Zip') {
            steps {
                // sh 'echo "Hello World!" > generatedFile.txt'
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
